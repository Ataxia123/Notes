Once considered a fringe idea, Ethereum—the world’s first smart contracts platform—has grown considerably over the years, and now hosts nearly 3,000 decentralized applications (dApps), 4,000+ smart contracts, and over 90,000 transactions daily. 

But the increased activity on Ethereum has come with a cost: scalability.

Limits on block sizes and block times, although necessary for decentralization and security, reduce Ethereum’s capacity to scale and accept more users. The end result is a collection of problems most Ethereum users are familiar with—namely, high gas fees and slow transactions. 

[Scaling Ethereum](https://www.alchemy.com/overviews/ethereum-scaling-solutions) _safely_ requires increasing its ability to scale network throughput and latency without introducing trust assumptions. This is what several scaling solutions such as [Layer 2 rollups and sidechains](https://www.alchemy.com/overviews/sidechains-vs-layer2s) attempt to do. 

This article explores Optimistic Rollups (ORUs), a class of L2 rollup solutions designed to make using Ethereum cheaper and faster. 

## What are optimistic rollups?

‍**Optimistic rollups are a layer 2 (L2) construction that improves throughput and latency on Ethereum’s base layer by moving computation and data storage off-chain.** An optimistic rollup processes transactions outside of Ethereum Mainnet, reducing congestion on the base layer and improving scalability. 

The “optimistic” label points to a distinctive feature of optimistic rollups: they publish little information about transactions on-chain and automatically assume _all_ transactions are valid. They are called “rollups” because they aggregate (“roll up”) thousands of transactions into batches before submitting them on Mainnet. 
