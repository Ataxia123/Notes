# Rollups: A Guide You Can Actually Understand

![Chaskin OnChain](https://mirror-media.imgix.net/publication-images/e5FB0R5s9aSvt-LzqTz3y.png?h=1000&w=1000)

[Chaskin OnChain](https://mirror.xyz/0x218932707a30bE62Ef8559d32d954863933b412f)
[source](https://mirror.xyz/0x218932707a30bE62Ef8559d32d954863933b412f)


Rollups this, rollups that – you've probably know that they're a way to scale Ethereum, but what exactly is a rollup? How does it work in a technical sense that's still accessible to understand? That's what this post aims to explain.

### **Overview of Rollups**

Ethereum currently allows a maximum of 30M gas per block, which comes out to around 25 transactions per second. In essence, rollups enable more transactions to fit into an Ethereum block without increasing the gas limit. They achieve this by allowing computation (actually executing the transaction, which is very gas expensive) to occur offchain.

To understand how rollups work, imagine that there are two rollup transactions in a batch of 50 that get sent to a L1 smart contract. In the first transaction, address 0x123 calls a Uniswap contract with 10 ETH as the input. In the second transaction, address 0x456 calls an Aave smart contract with 100 DAI as the input. If these transactions were to occur directly on L1, the validators on the network would need to run these transactions through the EVM (Ethereum Virtual Machine) to get the output. This process of running transactions through the EVM is highly resource intensive, and it's one of the reasons why Ethereum blocks can only contain a limited number of transactions.

Rollups process these transactions through a virtual machine (not necessarily the EVM) off L1 and then summarize the results in a compact form. For example, they would post to their L1 smart contract something like: '0x123 calls a Uniswap contract with 10 ETH as the input and the output is 100 USDC to 0x123,’ and '0x456 calls an Aave smart contract with 100 DAI as the input and the output is 50 LINK to 0x456.’ These summaries are presented as blobs of data. In theory, if you are someone simply observing their smart contract and seeing this data blob come in, you wouldn't know whether that's the correct output. Rollups then use proofs, either fraud or optimistic, to ensure that the execution of the transactions was done correctly.

In a rollup, several transactions are bundled and compressed into one single transaction on Ethereum Mainnet (for example, '0x789 calls a Compound contract with 20 ETH as the input and the output is 200 DAI to 0x789,' '0x321 calls a Sushiswap contract with 50 ETH as the input and the output is 500 LINK to 0x321,' '0x654 calls a MakerDAO contract with 30 DAI as the input and the output is 5 ETH to 0x654', …). This single L1 transaction contains all the necessary information about the multiple offchain transactions, including a summary of the current state of the rollup as a merkle root. A merkle root is a cryptographic way to keep track of the current state of something in a condensed form, encapsulating large amounts of data into a single hash. All rollups use one smart contract on Ethereum Mainnet to maintain the rollup state, hold the ETH sent to bridge to the rollup, and allow for an emergency escape from the smart contract, which I will explain later.

The calldata of the smart contract is where they post the compressed transactions and state roots. In a normal smart contract, the calldata is a specific area used to indicate which function you want to call and with what arguments, essentially conveying the details of the interaction with the smart contract. However, rollups use the calldata in their Ethereum L1 smart contracts differently. They utilize it as a data blob to post their transactions and state roots, enabling a more compact and efficient representation of offchain activities.

To interact with a rollup, a user sends a transaction to the rollup's sequencer node. The transaction is then placed in the sequencer's mempool, where it waits to be executed, ordered with other transactions, and summarized before being sent to L1. To update the rollup state as transactions are made, the sequencer sends details about all their transactions to their L1 smart contract. This includes transaction information you’d find on Etherscan, such as the sender, recipient, value, outcome, etc., along with an updated state root. Since all the transaction information needed to update the new state is posted to L1, in theory, anyone watching the smart contract could execute the transactions themselves and recompute the state. By performing much of the computation offchain and then posting the results to the Ethereum Mainnet, rollups greatly enhance scalability and efficiency, enabling more robust and responsive decentralized applications.

### **Verifying Correctness: Fraud Proofs**

Since computation is done offchain by the rollup, verification of correctness becomes crucial. The system must ensure that the rollup nodes process transactions correctly and can't include fake ones. This is where fraud proofs come into play.

**ZK Proofs:** These are straightforward. When a ZK rollup sends a transaction to its L1 smart contract, it includes the compressed multiple transactions information, the new state root, and a zk-proof. The zk-proof verifies the handling of the transactions and confirms the updated state is valid.

**Optimistic Fraud Proofs:** This involves economic games. Optimistic rollup nodes need to stake some ETH, essentially saying, "If I'm lying and you prove it, you get my stake." It relies on people examining the L1 smart contract and recreating the state's transition. If fraud is found, they can initiate a fraud proof game by also staking some ETH. If the rollup is found to be lying, the accuser receives the rollups stake, and if wrong, they lose their posted stake. Optimistic rollups depend on at least one person checking the chain, and transactions are not considered final until a week has passed, allowing time for the fraud-checking game.

You may have heard the term 'Data Availability' before. Essentially, this means that the complete transaction information and state roots need to be posted and visible for a sufficient amount of time, allowing people to recreate the state if necessary. This requirement is an essential aspect of both ZK rollups and optimistic rollups, ensuring that the information is accessible and transparent for validation purposes.

### **Upgradable Multisig Contracts and Associated Risks**

For most rollups, the L1 smart contract is currently an upgradable multisig contract. This presents an obvious risk, as changes to the contract could potentially lead to unintended consequences or vulnerabilities within the rollup. Teams are actively working to mitigate this risk, with various strategies being employed to ensure that the contract remains secure and functions as intended. One of the most popular methods currently in use involves allowing token holders to vote on changes to the smart contract. By incorporating a governance mechanism where token holders have a say, it brings a degree of decentralization and community oversight to the process. Decisions are not made unilaterally but must pass through a democratic process, where token holders' voices are heard.

Furthermore, to add an additional layer of safety, many projects implement a time delay on decisions. If a change to the smart contract is approved, it does not take effect immediately. This delay provides a window of opportunity for those who disagree with the decision to exit the system. If you are against a decision, you have the time to withdraw your funds and disengage from the rollup, reducing your exposure to any potential negative impact from the change. This approach to governance and the implementation of time delays are seen as robust safeguards, balancing the need for flexibility and upgradability in the smart contract with the necessity to protect users and maintain trust in the rollup system.

### **Sequencer Decentralization**

The discussion around decentralizing the sequencer is gaining momentum. Sequencer decentralization is vital for censorship resistance. Currently, if a sole sequencer ignores your transaction, you can submit a request back to L1 using a merkle proof. What this entails is providing proof to the smart contract that you possess ETH within the rollup and that you want it sent back to your EOA (Ethereum Address) on L1. While this option is positive, the objective in decentralizing the sequencer is to minimize its power to censor transactions.

Fraud proofs already ensure that there are no invalid state transitions, so rollups don't require thousands of nodes like Ethereum Mainnet does. The goal is to have the minimum amount of nodes (sequencers) necessary to prevent transaction censorship. By keeping this number low, the UX of the rollup can remain high, the whole purpose they exist in the first place. A small number of trusted, whitelisted sequencers, approved by token holders may be an acceptable compromise to keep costs low, given the security benefits from the L1. While anyone can be a validator on Ethereum Mainnet, rollups need not follow the same model. Some rollup teams might be awaiting EIP 4844, an improvement to Ethereum that is likely to be implemented later this year or early next. Which will allow for more space for rollups to post data, potentially increasing scalability by 10x and mitigating the effects of additional sequencers.

### **Conclusion**

Rollups have emerged as an exciting and innovative solution to some of Ethereum's most pressing challenges. By enabling offchain computation, they significantly increase the network's efficiency and scalability, making decentralized applications more robust and responsive. The integration of mechanisms like fraud proofs, governance strategies, and sequencer decentralization ensures that the system maintains a high level of trust, transparency, and community oversight. As the technology continues to evolve, rollups may very well become a fundamental aspect of Ethereum's growth and success. By understanding the intricacies of how they function, we can better appreciate the remarkable strides being made in the world of decentralized finance and blockchain technology.

### **Glossary**

- **Rollup**: A Layer 2 scaling solution that enables more transactions on Ethereum by performing computation offchain and then posting the results to the Ethereum Mainnet.
    
- **Gas**: A measure of computational work on Ethereum, required to process transactions.
    
- **EVM**: Short for Ethereum Virtual Machine, a decentralized computer that runs on the Ethereum network, executing smart contracts and processing transactions.
    
- **Merkle Root**: A hash that summarizes a large set of data, allowing for efficient and secure verification of contents within that data set.
    
- **Calldata**: A specific area in a smart contract that typically indicates the function being called and its arguments. In the context of rollups, this area is used to post transaction data, the state root, and, in the case of ZK rollups, the accompanying zk-proof.
    
- **Sequencer**: In the context of rollups, a node that orders and transactions and sends compressed details to the L1 smart contract.
    
- **ZK Proofs**: Short for Zero-Knowledge Proofs, a cryptographic method that verifies the validity of a transaction without revealing any information about the transaction itself. In the context of zk-rollups, ZK Proofs are used to post a concise proof that all the transactions and the new state transition are valid.
    
- **Optimistic Fraud Proofs**: A system of checks and incentives to ensure that rollup nodes process transactions correctly and honestly.
    
- **Data Availability**: The requirement that complete transaction information and state roots are posted and visible for a sufficient amount of time for validation purposes.
    
- **Multisig Contract**: A smart contract that requires multiple signatories to approve changes or transactions.
    
- **EOA**: Externally Owned Account, an account controlled by a private key on Ethereum.
    
- **EIP 4844**: A proposed Ethereum Improvement Proposal that will have an impact on rollup scalability.