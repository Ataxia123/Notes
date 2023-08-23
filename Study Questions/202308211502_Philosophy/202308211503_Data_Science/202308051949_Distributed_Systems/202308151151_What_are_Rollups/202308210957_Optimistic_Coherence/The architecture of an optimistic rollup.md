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

![[Benefits_OP_Arch]]