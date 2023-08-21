**This achieves two objectives:**

1. If a sequencer goes offline, another sequencer can use the transaction data to reconstruct the rollup’s state and continue producing blocks. 

2. Alice (the user) can download the data herself and use it to create a Merkle proof. 

The use of on-chain data availability is what makes optimistic rollups considerably more secure than other scaling solutions. With transaction data stored on Ethereum, user funds are always safe—so long as Ethereum remains operational. 

So, one way or the other, Alice manages to create a Merkle proof to prove ownership of funds. However, she must wait for the _dispute period_ to elapse before withdrawing her funds. In optimistic rollups, the dispute period is a 1-2 week interval between submitting a withdrawal request and getting the requested funds. 

During this period, anyone can publish a fraud proof claiming a particular transaction, or batch of transactions, is invalid. If the fraud proof succeeds, the sequencer’s bond (provided as a guarantee of honest behavior) is slashed, Alice’s “funds” are reverted, and the “whistleblower” (called a _verifier_) is rewarded for their efforts.  If no one challenges Alice’s withdrawal request, then she can get her funds from the rollup contract after 1-2 weeks. 
