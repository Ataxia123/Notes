### What is the difference between fraud proofs and validity proofs?

A fraud proof is different from a validity proof mainly because it is computed on-chain. Validity proofs (also called zero-knowledge proofs) are computed off-chain (i.e., on the rollup) and verified on Ethereum. 

As explained in our article comparing different [types of zero-knowledge proofs](https://www.alchemy.com/overviews/snarks-vs-starks), a validity proof, such as a SNARK or STARK, is used to prove the validity of transactions performed off-chain. This is the foundation of a [zero-knowledge rollup](https://alchemy.com/blog/zero-knowledge-rollups).

In a ZK-rollup, a validity proof is produced for every batch using the transaction data as inputs. This validity proof is submitted along with the batch to Ethereum Mainnet and verified by an on-chain contract. This means transactions can be declared valid immediately, without waiting for a challenge (as with optimistic rollups). 

Another difference between fraud proofs and ZK proofs is that the latter is somewhat easier to verify on-chain. All the smart contract needs to do is run the validity proof to determine the validity of batched transactions. With a fraud proof, the entire state transition must be replayed before completing the fraud proof computation. 
