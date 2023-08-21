### What is a fraud proof?

**A fraud proof is a claim that a state transition (i.e., transaction) is invalid and the entire batch should be reverted as a result.** Although complex, fraud proofs heavily rely on state roots (mentioned earlier) to work. 

The process starts when a party (verifier) detects a mismatch between the rollup state referenced in the state root on the L1 chain and the actual state of the rollup chain. 

An example would be the sequencer submitting a post-state root that reduces Alice’s balances by 5 ETH and increases Bob’s balance by the same amount, even though Alice never performed a transfer. 

The verifier can “challenge” this state transition and prove its invalidity. This is possible because the verifier downloads data for every transaction, applies it to their copy of the rollup state, and computes the post-state root. 

If the sequencer’s post-state root matches the verifier’s, nothing happens. If, however, the sequencer’s post-state root is different—likely because it includes a false transaction, such as the one described in Alice’s case—then the verifier can trigger a fraud proof computation. 

![An image showing how optimistic rollups use fraud proofs to detect invalid transactions.](https://assets-global.website-files.com/5f973c97cf5aea614f93a26c/629e623f57f8cd8134c73465_XGzSlkM0DNGEU8pG2ydg7Wlgq5q1qjeSfGQGEQfqyWjI4k8ZW1VZIyFOFqYhkZnjeIgYN4QQXqimrVINEfGJycI4d4vRAWoZtRFramfqnsdDCMbsL-2oo1uBzGieQVPquXdWNA0ou5-vkpPHsQ.png)

[_Source_](https://ethereum.org/en/developers/docs/scaling/optimistic-rollups/#disputing-transactions)