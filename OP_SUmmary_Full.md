## What are optimistic rollups?

‍**Optimistic rollups are a layer 2 (L2) construction that improves throughput and latency on Ethereum’s base layer by moving computation and data storage off-chain.** An optimistic rollup processes transactions outside of Ethereum Mainnet, reducing congestion on the base layer and improving scalability. 

The “optimistic” label points to a distinctive feature of optimistic rollups: they publish little information about transactions on-chain and automatically assume _all_ transactions are valid. They are called “rollups” because they aggregate (“roll up”) thousands of transactions into batches before submitting them on Mainnet. 

### The architecture of an optimistic rollup 

#### 1. Entering the optimistic rollup

Optimistic rollups use smart contracts deployed on Ethereum to manage the interaction between the L2 chain and the L1 blockchain (Ethereum). Rollup users must deposit funds into one of these smart contracts before getting an equivalent amount unlocked on the rollup. 

A third party, known as a _sequencer_, credits the user with funds on the rollup after receiving proof of the latter’s deposit in the rollup contract. The user is then free to transact freely on the rollup until they exhaust their balance. 

![A diagram showing how users move funds from Ethereum Mainnet to an Optimistic rollup. ](https://assets-global.website-files.com/5f973c97cf5aea614f93a26c/629e623f961a6066a825ad30_g_f22-GepwmRf0v8mweT0AXFkIjBOLmZTXNKRKJY7rq9Bc9SEZETOk93gzuIckJ_S7N5bFpimrixsQda6d-2Mm-tbLWOuK0R66GScTu7baQDQUhVVKfGCh-zmXCtj7kL1vzNwu__NLHB6RW4uQ.png)

[_Source_](https://medium.com/privacy-scaling-explorations/an-introduction-to-optimisms-optimistic-rollup-8450f22629e8)

#### 2. Using the optimistic rollup

On the rollup, users sign transactions and submit them to the sequencer who’s responsible for ordering and executing transactions. The sequencer verifies transactions, compresses the data into a block, and submits the batch to Ethereum as a single transaction.

This is another area where the rollup contract comes into the picture. The on-chain contract stores a “state root”, which is a Merkle root of the rollup’s state. Let’s break this down further:

##### **State**

_State_ is a concept referring to the available information about a network at a specific point in time. The “rollup’s state” describes the L2 chain’s present condition and specifies details, like existing accounts, balances, smart contracts, and so on. 

Every transaction performed on the rollup causes a change in its state—for example, Alice’s balances will decrease after she sends 5 ETH to Bob. Thus, transactions are called _state transitions_ since the rollup moves from an old state to a new state after executing a transaction.

##### Merkle root

A [Merkle root](https://docs.alchemy.com/alchemy/resources/web3-glossary#merkle-patricia-tree-or-trie) enables users to encode large amounts of information using cryptographic hashes. Merkle roots also make it easier to check if a piece of data (e.g., a transaction) is part of a larger dataset (e.g., a batch of transactions). 

Therefore, the “state root” stored in the rollup contract is a cryptographic commitment verifying the rollup’s status at different points in time. When a sequencer submits a batch of transactions to the rollup contract, it must include a _pre_-state root and a _post_-state root. 

1. **Pre-state root**: The _old_ state root, which describes the rollup’s condition _before_ the submitted transactions were executed. 

2. **Post-state root**: The _new_ state root, which describes the rollup’s condition _after_ the submitted transactions were executed. 

Once the sequencer submits the batch, the contract verifies that the _pre_-state root matches the existing state root. If the two match, the contract discards the old state root and stores the new state root proposed by the sequencer. 

This means transactions referenced in the _post_-state root have become final and cannot be reversed. Note that the sequencer doesn't have to submit proof of the validity of batched transactions. 

The only time a proof is required is if a verifier reports a fraudulent rollup transaction using a fraud proof. We’ll explain the mechanics of a fraud proof in a later section of this article. 

![A diagram showing the architecture of the optimistic rollup contract on the L1 blockchain. [](https://assets-global.website-files.com/5f973c97cf5aea614f93a26c/629e623fc30281c993b297c6_J00-_uw-59puy9rvPfUyjdx_O4IYTr-73mEEpUm5X15eOHL7SIcvHoaQx-yQBhq8o0PpbQ6O4d0s1EoqzGthuKVzFzJDjo1tDwAgEKDMfn_c5mBeBZsFNdmwXlA8Pg7ipZwmI_ZQxMDgcrbCWA.png)

[_Source_](https://vitalik.ca/general/2021/01/05/rollup.html)

#### 3. Exiting the optimistic rollup 

Say Alice (the user) has had enough of this rollup business and wants to withdraw her funds from the rollup contract on Ethereum Mainnet. To do this, she needs a Merkle proof that—yes, you guessed it—proves her transaction included in the rollup’s state root. 

Constructing the Merkle proof requires having access to the initial transaction data, which the sequencer is expected to provide. If all goes well, Alice gets the data, creates the Merkle proof, and submits to the rollup contract. 

But relying on the sequencer to provide transaction data introduces trust assumptions. A sequencer could go rogue, execute a transaction transferring Alice’s token to their wallet, and deny her the data she needs to prove ownership of the funds. Even something less malicious, like a sequencer going offline, can still threaten the decentralization and security of optimistic roll-ups. 

Optimistic rollups solve this problem by requiring sequencers to post the full transaction data on the main Ethereum execution layer. This information is published on Ethereum Mainnet as "calldata," which is cheaper than storing it in the [Ethereum Virtual Machine](https://www.alchemy.com/overviews/what-is-the-ethereum-virtual-machine-evm)'s memory or storage (further reducing rollup fees).

**This achieves two objectives:**

1. If a sequencer goes offline, another sequencer can use the transaction data to reconstruct the rollup’s state and continue producing blocks. 

2. Alice (the user) can download the data herself and use it to create a Merkle proof. 

The use of on-chain data availability is what makes optimistic rollups considerably more secure than other scaling solutions. With transaction data stored on Ethereum, user funds are always safe—so long as Ethereum remains operational. 

So, one way or the other, Alice manages to create a Merkle proof to prove ownership of funds. However, she must wait for the _dispute period_ to elapse before withdrawing her funds. In optimistic rollups, the dispute period is a 1-2 week interval between submitting a withdrawal request and getting the requested funds. 

During this period, anyone can publish a fraud proof claiming a particular transaction, or batch of transactions, is invalid. If the fraud proof succeeds, the sequencer’s bond (provided as a guarantee of honest behavior) is slashed, Alice’s “funds” are reverted, and the “whistleblower” (called a _verifier_) is rewarded for their efforts. 

If no one challenges Alice’s withdrawal request, then she can get her funds from the rollup contract after 1-2 weeks. 

### What is a fraud proof?

**A fraud proof is a claim that a state transition (i.e., transaction) is invalid and the entire batch should be reverted as a result.** Although complex, fraud proofs heavily rely on state roots (mentioned earlier) to work. 

The process starts when a party (verifier) detects a mismatch between the rollup state referenced in the state root on the L1 chain and the actual state of the rollup chain. 

An example would be the sequencer submitting a post-state root that reduces Alice’s balances by 5 ETH and increases Bob’s balance by the same amount, even though Alice never performed a transfer. 

The verifier can “challenge” this state transition and prove its invalidity. This is possible because the verifier downloads data for every transaction, applies it to their copy of the rollup state, and computes the post-state root. 

If the sequencer’s post-state root matches the verifier’s, nothing happens. If, however, the sequencer’s post-state root is different—likely because it includes a false transaction, such as the one described in Alice’s case—then the verifier can trigger a fraud proof computation. 

![An image showing how optimistic rollups use fraud proofs to detect invalid transactions.](https://assets-global.website-files.com/5f973c97cf5aea614f93a26c/629e623f57f8cd8134c73465_XGzSlkM0DNGEU8pG2ydg7Wlgq5q1qjeSfGQGEQfqyWjI4k8ZW1VZIyFOFqYhkZnjeIgYN4QQXqimrVINEfGJycI4d4vRAWoZtRFramfqnsdDCMbsL-2oo1uBzGieQVPquXdWNA0ou5-vkpPHsQ.png)

[_Source_](https://ethereum.org/en/developers/docs/scaling/optimistic-rollups/#disputing-transactions)

### How do fraud proofs work?

Here’s a high-level description of the fraud proof process:

1. The verifier initiates a challenge and provides the following information:

                  a. Disputed state transition

                  b. The pre-state root

                  c. Rollup state data

                  d. Their version of the post-state root.  
  

       2. The transaction is replayed in a sandboxed environment on the L1 chain using, among other things, information provided by the challenger.

This “sandboxed environment” is a smart contract running on Ethereum, which doubles as a virtual machine (VM). 

       3. If the computation results in a post-state root matching the challenger’s, then we know the sequencer indeed published a batch with an invalid state transition.  
  
The invalid batch (and others) published afterward will be reverted, restoring the rollup to its earlier state. 

We should note that the fraud proof mechanism is more complicated than described here. 

This article on [fraud proofs in rollups](https://medium.com/@cpbuckland88/fraud-proofs-and-virtual-machines-2826a3412099) may provide some additional context. 

### What is the difference between fraud proofs and validity proofs?

A fraud proof is different from a validity proof mainly because it is computed on-chain. Validity proofs (also called zero-knowledge proofs) are computed off-chain (i.e., on the rollup) and verified on Ethereum. 

As explained in our article comparing different [types of zero-knowledge proofs](https://www.alchemy.com/overviews/snarks-vs-starks), a validity proof, such as a SNARK or STARK, is used to prove the validity of transactions performed off-chain. This is the foundation of a [zero-knowledge rollup](https://alchemy.com/blog/zero-knowledge-rollups).

In a ZK-rollup, a validity proof is produced for every batch using the transaction data as inputs. This validity proof is submitted along with the batch to Ethereum Mainnet and verified by an on-chain contract. This means transactions can be declared valid immediately, without waiting for a challenge (as with optimistic rollups). 

Another difference between fraud proofs and ZK proofs is that the latter is somewhat easier to verify on-chain. All the smart contract needs to do is run the validity proof to determine the validity of batched transactions. With a fraud proof, the entire state transition must be replayed before completing the fraud proof computation. 

## What are the differences between optimistic rollups and zk rollups?

**The major difference between optimistic rollups and ZK rollups comes from the former's support for smart contracts, delayed withdrawals, reliance on cryptoeconomic incentives, and security properties.** 

Here's a detailed comparison of optimistic rollups and ZK rollups:

**Features**

**Optimistic rollup** 

**ZK-rollup** 

**Proof**

Uses fraud proofs to prove transaction validity. 

Uses validity (zero-knowledge) proofs to prove transaction validity. 

**Capital efficiency**

Requires waiting through a 1-week delay (dispute period) before withdrawing funds. 

Users can withdraw funds immediately because validity proofs provide incontrovertible evidence of the authenticity of off-chain transactions. 

**Data compression**

Publishes full transaction data as calldata to Ethereum Mainnet, which increases rollup costs. 

Doesn't need to publish transaction data on Ethereum because ZK-SNARKs and ZK-STARKs already guarantee the accuracy of the rollup state. 

**EVM compatibility**

Uses a simulation of the Ethereum Virtual Machine (EVM), which allows it to run arbitrary logic and support smart contracts. 

Doesn't widely support EVM computation, although a few EVM-compatible ZK-rollups have appeared. 

**Rollup costs**

Reduces costs since it publishes minimal data on Ethereum and doesn't have to post proofs for transactions, except in special circumstances. 

Faces higher overhead from costs involved in generating and verifying proofs for every transaction block. ZK proofs require specialized, expensive hardware to create and have high on-chain verification costs. 

**Trust assumptions**

Doesn't require a trusted setup. 

Requires a trusted setup to work. 

**Liveness requirements**

Verifiers are needed to keep tabs on the actual rollup state and the one referenced in the state root to detect fraud. 

Users don't need someone to watch the L2 chain to detect fraud. 

**Security properties** 

Relies on cryptoeconomic incentives to assure users of rollup security. 

Relies on cryptographic guarantees for security. 

## What are the top optimistic rollup blockchains?

**The top optimistic rollup blockchains are Arbitrum, Optimism, Metis Andromeda, and Boba Network in terms of Total Value Locked (TVL).** Below is an overview of the different optimistic rollups (ORUs):

### 1. Arbitrum

[Arbitrum](https://www.alchemy.com/layer2/arbitrum/?a=39dca3d5aa) is an optimistic rollup project designed to improve Ethereum’s user costs and transaction speed by moving computation and data storage off-chain. The Arbitrum Virtual Machine (AVM) supports EVM-compatible smart contracts, allowing users to use favorite dApps for a fraction of Ethereum’s costs. 

### 2. Optimism

[Optimism](https://www.alchemy.com/layer2/optimism/?a=39dca3d5aa) is an EVM-compatible, optimistic rollup chain leveraging Ethereum’s security guarantees. Optimism uses an optimistic rollup (OR) construction to roll up thousands of off-chain transactions and save users on gas fees.

### 3. Metis Andromeda

Metis Andromeda is a scalable, low-cost, and functional L2 protocol based on optimistic rollups. Metis Andromeda’s unique stack can be applied to different use-cases, including dApps, DAOs, and DeFi.

### 4. Boba Network

Boba Network is an Ethereum L2 scaling throughput with optimistic rollup designs. Boba Network offers a Liquidity Provider (LP) service that allows users to withdraw funds immediately without waiting for a seven-day challenge period to elapse.

### What optimistic blockchains or projects have tokens?

The following optimistic rollup projects have tokens:

- Optimism (OP)
- Boba Network (BOBA)
- Metis Andromeda (METIS)

## Optimistic rollup tools

Optimistic rollups are useful solutions for scaling dApps and interacting with smart contracts in a more cost-effective and efficient manner. But first, you'll need various tools to use optimistic rollups easily _and_ safely. 

Here are various optimistic rollup tools for developers and end-users:

### Cross-chain bridges to optimistic layer 2 blockchains

While optimistic rollups are built on top of Ethereum’s base layer, assets on both chains are not natively compatible. However, you can transfer funds from an L1 chain, like Ethereum, to an optimistic rollup [using cross-chain bridges](https://www.alchemy.com/overviews/cross-chain-bridges):

Here are examples of bridges connecting L1 chains and different L2 rollups:

### Bridges to and from Arbitrum

- Arbitrum Token Bridge
- cBridge
- Hop Protocol
- Synapse Protocol
- Anyway Bridge
- DeGate Bridge

### Bridges to and from Optimism

- Connext
- Celer Bridge
- Li.Fi
- Optimism Bridge
- Poly Network
- Via Protocol
- Synapse Protocol
- Across

### Bridges from and to Metis Andromeda

- Metis Bridge
- cBridge
- AnySwap
- Synapse Protocol

### Bridges from and to Boba Network

- Across
- Boba Standard Token Bridge/Fast Token Bridge
- cBridge
- Synapse Protocol

### Optimistic rollup testnets 

A [testnet](https://www.alchemy.com/overviews/what-are-testnets) is a public blockchain network that simulates the behavior of an associated main network (Mainnet). Testnets don't use real funds, unlike a real blockchain, allowing developers to deploy and test smart contracts with minimal risk. 

Some optimistic rollups have versions of Ethereum testnets, like [Rinkeby](https://www.alchemy.com/overviews/rinkeby-testnet), which can use for testing your dApp:  

#### 1. Optimism Ethereum Kovan Testnet 

The Optimistic Ethereum Kovan Testnet is an EVM-compatible optimistic rollup chain designed for testing purposes. Like Optimism on Ethereum Mainnet, the Optimistic Ethereum Kovan Testnet is designed for faster and cheaper transactions than obtainable on L1s. 

#### 2. Arbitrum Rinkeby Testnet

Offchain Labs, the team behind Arbitrum, launched an EVM-equivalent rollup chain on the Rinkeby network. The Arbitrum Rinkeby testnet allows developers to deploy Solidity smart contracts on the Arbitrum rollup without downloading software. It also comes with a blockchain explorer and a bridge for moving ERC-20/ERC-721 tokens. 

#### 3. Boba Network Rinkeby Testnet 

Boba Network is another project with an EVM-compatible rollup chain on the Rinkeby testnet. You can request testnet ETH with Alchemy's [Rinkeby faucet](https://rinkebyfaucet.com) to create or test your smart contracts. 

## Conclusion

Optimistic rollups are a major part of efforts to scale Ethereum using layer 2 architecture. Optimistic rollups build on Ethereum's security and decentralization while offering cheaper fees and faster transactions. 

Alchemy supports two leading projects based on optimistic rollups, Arbitrum and Optimism. [Sign up for free today](https://www.alchemy.com/?a=39dca3d5aa) and see how you can scale your dApp with Ethereum-based optimistic rollups. 

Start building  
on Alchemy.