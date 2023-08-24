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