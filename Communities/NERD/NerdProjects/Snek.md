
-> Project description: 

**Trustless backend for blockend execution.**

#FetchAI #Vault #DeFi #AI 

[[FetchAI telegram Bot|FetchAI telegram Bot]]

[[Drawing 2023-07-28 21.52.28.excalidraw]]

Telegram bots are a strong trend in the market. The general arquitecture of these bots involve creating a node backend that hosts user private keys. The bot essentially acts as a front end for a hot wallet exchange that swaps using arbitrary logic. 

## The issue with telegram bots.

The users have to trust the developers not to take the private keys which must be hosted on their server. However, compared to fully custodial services If the service goes down the users can still get their funds back as they are on chain.

This setup is sufficient for small 🦐 volume trading, but in order to properly scale up a trustless architecture where the developers have a smaller attack surface is required.

## Agent based Architecture 

Current working theory:

Alice and Bob pair of agents. Alice is a fund manager and runs a query at an interval where it will decide if it should take a trade action.

Eth side:

Ideally Instadapp based as it provides granular control.

[[yearnVault]] based approach




Github: [link](https://GitHub.com/Ataxia123/snek)

Knowledge Base:

- [[yearnVault]]
- [[python]]
- [[1690603664-soliditydev|solidityDev]]
- [[1689435709-scaffold-eth|Scaffold-ETH]]
- [[LangChain]]
- [[FetchAI telegram Bot|FetchAI]]
- [[instadapp]]


