---
tags: Messari, JMPlusEV
---
# Infra Brief: Rethinking the 'Build It and They'll Come' Approach

## Key Narrative

The "build it and they'll come" approach has been a prevalent narrative in the crypto space, particularly in the context of Decentralized Physical Infrastructure Networks ([DePINs](/report/navigating-the-depin-domain)). The prevailing belief was that once the supply side was built, the demand side would naturally follow. However, this assumption hasn’t proven true. While DePINs have been remarkably effective at drawing supply-side participation, they have struggled to attract demand-side usage.

![](https://cdn.sanity.io/images/2bt0j8lu/production/122c9d7e37bda6dc2875c5f20e9b6db1ea0da59c-3840x2160.png?w=714&fit=max&auto=format&dpr=3 "View full size")

A significant factor contributing to the cost-effectiveness of DePINs is their capacity to reduce operational expenditures by doing away with traditional roles such as sales, business development, and customer service. However, the lack of these dedicated teams can also pose difficulties. In particular, attracting users has proven challenging for DePINs that target traditional Web2 customers, and even for those targeting Web3 projects.

### Bridging the Web2/Web3 Gap with Gateway Companies

While transformative innovations are unfolding in Web3, the majority of users and workloads are still entrenched in Web2. This disconnect necessitates the emergence of Web3 gateway companies - entities that operate with a Web2 frontend for user interface, yet harness Web3 backend technologies.

Interacting directly with DePINs presents a steep learning curve, and the requirement to acquire a token introduces an additional obstacle. Moreover, for accounting and compliance reasons, many businesses find themselves unable to hold tokens on their balance sheet. Web3 gateway companies step into this gap, enabling fiat payments, simplifying the onboarding process for businesses and individuals, abstracting away the complexities, and providing customer support.

Take [Filebase](https://filebase.com/) as an example - a Web3 gateway company that facilitates enterprise adoption of decentralized storage technologies. By providing a browser-based dashboard and an AWS S3-compatible API, Filebase eases the deployment, access, and management of data across decentralized storage networks, while also selecting the optimal storage network based on specific user requirements.

#### Web2 User Interfaces

Recognizing the need for Web2 interfaces to streamline user interaction and expedite market penetration, many DePIN operating companies and foundations have begun developing user-friendly frontends. A few noteworthy examples include:

- **[Livepeer Studio](https://livepeer.studio/) –** This comprehensive dashboard allows users to manage livestreams, video uploads, API keys, network usage, billing, and more using the Livepeer Protocol.
- [**1663**](https://1663.io/) **–** Offering tools, resources, and support for IoT deployments, it acts as an onboarding ramp to Helium’s IoT network.
- **[AkashAI](https://twitter.com/akashnetAI)** and **[Cloudmos](https://cloudmos.io/) –** Abstract complexity of utilizing Akash’s GPU marketplace for machine learning engineers and users.
- **[Storj Labs Satellite](https://www.storj.io/pricing) –** A hosted service that manages storage nodes, billing, SLAs, and onboarding of clients.
- **[Estuary](https://estuary.tech/) –** Designed to simplify the usage of Filecoin for non-technical users without crypto knowledge.

While these platforms are managed by a protocol's operating company or foundation, any entity can create its own, competing for users on the basis of UX, customer service, and other factors.

Given that over [90%](/report/state-of-livepeer-q4-2022) of Livepeer’s network usage stems from Livepeer Studio, it’s clear that such gateways will play a crucial role in driving general crypto adoption.

## Key Events

_Power by Messari [Intel](/intel)_

### Chainlink Expands into Interoperability with CCIP Launch

_By: [Chase Devens](https://twitter.com/chasedevens)_

After multiple years of teasing, Chainlink launched its [Cross-Chain Interoperability Protocol](https://chain.link/cross-chain) (CCIP). The protocol allows applications to use Chainlink’s Decentralized Oracle Networks (DONs) as facilitators for cross-chain message transfers. These messages are nothing more than arbitrary data but can be used to construct complex logic and standards such as smart contract calls, governance votes, and token transfers.

![](https://cdn.sanity.io/images/2bt0j8lu/production/3b341e5979f310c761d08e54c3e898fa0d45d90d-1920x1080.png?w=714&fit=max&auto=format&dpr=3 "View full size")

_Source:_ Chainlink

Chainlink has placed an early emphasis on token bridging by developing a plug-and-play Simplified Token Transfers module. These contracts handle the complexities involved in burning, minting, locking, and unlocking tokens across chains. Additionally, the module can be complimented by additional message instructions that can be executed atomically when tokens are moved across chains.

CCIP is being debuted with two high-profile launch partners: Synthetix and Aave. Synthetix uses CCIP to burn and mint sUSD, which represents liquidity for the protocol’s Synths, across chains through a mechanism called the Synth Teleporter. By employing a burn-and-mint design, Synthetix can avoid relying on wrapped asset liquidity pools and make its liquidity more efficient. Aave will be using CCIP to facilitate its cross-chain governance efforts.

The move into the interoperability landscape presents Chainlink with a new revenue stream for its oracle providers. CCIP charges applications with a flat service fee as well as a destination gas fee. These fees can be paid for in any token, but if applications choose to pay in tokens other than LINK, they will receive a 10% surcharge. This makes it easier for applications to integrate and pay for cross-chain communications while adding to oracle provider’s top-line revenues.

Chainlink already has integrations with over 1,800 projects from its existing offerings. These include services such as price feeds, off-chain functions, and verifiable random number generation. With CCIP, Chainlink can leverage this distribution channel and brand recognition to unify its network of customers that exist across siloed ecosystems (both on-chain and off-chain). Applications that already trust Chainlink for its other services will not need to make additional trust assumptions to use CCIP.

### The Graph Introduces Substreams

The Graph has introduced its newest data transformation layer, [Substreams-powered subgraphs](https://thegraph.com/blog/substreams-powered-subgraphs/), a significant upgrade that enhances the syncing and indexing performance of subgraphs. Substreams incorporate the Firehose technology, a high-performance method of ingesting blockchain data that replaces the traditional linear indexing model. This improves the speed of syncing and indexing. To illustrate, the Uniswap-V3 subgraph previously took two months to sync. However, with a Substreams-powered subgraph, the sync was accomplished in just 20 hours.

Additionally, Substreams facilitate massively parallelized streaming data. With Substreams-powered subgraphs, users can stack Substream modules in a similar fashion to LEGO blocks, enhancing both the composability and performance within the subgraph ecosystem.

Substream's improved performance could address the [performance issues](https://docs.lens.xyz/docs/why-our-own-indexer) that led protocols such as Lens to develop their own indexers rather than utilizing The Graph. As a result, more applications might be encouraged to employ subgraphs. Furthermore, [Messari](https://thegraph.com/blog/substreams-powered-subgraphs/#:~:text=of%20both%20worlds.%E2%80%9D-,%E2%80%9CFor%20our%20team%2C%20Substreams%20has%20been%20a%20game%2Dchanger%20in%20radically%20improving%20the%20indexing%20speed%20and%20composability%20of%20subgraphs.%20It%E2%80%99s%20given%20us%20much%20faster%20development%20velocity%20and%20shorter%20iteration%20cycles.%E2%80%9D,-%2DVincent%20Wen%2C%20Engineering) is already reaping the benefits of Substreams-based subgraphs, experiencing increased development velocity and shorter iteration cycles.

### Render: From GPU Rendering to Cloud Computing Provider

The initial focus of the Render Network has been on serving users who require GPU-accelerated rendering jobs. However, due to the recent surge in demand for compute power for machine learning tasks, the network has introduced [RNP-004](https://github.com/rndr-network/RNPs/blob/main/Implemented/RNP-000.md) to cater to this demand.

The RNP proposes the implementation of a network API that allows external clients to access the Render Network's GPU resources. Alongside the public release of the RNP, [ANTBIT.IO](https://twitter.com/ANTBIT_OFFICIAL) has launched as a distributed machine learning compute protocol on Solana which will serve as an alpha test case, utilizing Render's GPUs. By implementing an API that enables other compute protocols to access Render's GPU resources, Render effectively becomes a provider of accelerated cloud computing.

This proposal holds significant value for the Render Foundation and its community, as it eliminates the need for them to acquire expertise in building distributed training or inference protocols to enter the market. They can now rely on [ANTBIT.IO](http://antbit.io/) to tap into the network's GPUs, allowing the Render community to focus on their core competencies while still benefiting from the demand for ML compute.

Once the new burn-and-mint equilibrium token model is implemented, the usage of Render’s GPUs will drive an increase in the increased burning of RNDR, benefiting token holders. Additionally, the proposal will further strengthen Render's position in the market as the largest distributed GPU network.

### Arweave Universal Data License

With the recent introduction of Arweave's [Universal Data License](https://mirror.xyz/0x64eA438bd2784F2C52a9095Ec0F6158f847182d9/AjNBmiD4A4Sw-ouV9YtCO6RCq0uXXcGwVJMB5cdfbhE) (UDL), users and creators now have the ability to define their own terms and conditions for content uploaded to the permaweb. The UDL offers a programmable and legally enforceable framework that enables creators to monetize their content and enables developers to seamlessly license that data for use in their applications.

![](https://cdn.sanity.io/images/2bt0j8lu/production/e4adf378d93a09c546843124e7d2814c75abb5cf-865x523.png?w=714&fit=max&auto=format&dpr=3 "View full size")

_Source_: [Forward Research](https://mirror.xyz/0x64eA438bd2784F2C52a9095Ec0F6158f847182d9/AjNBmiD4A4Sw-ouV9YtCO6RCq0uXXcGwVJMB5cdfbhE)

The license provides customizable parameters for monetization, including the duration of the license, preferred currency for payments, and the revenue share fee. Additionally, creators have the [flexibility](https://arwiki.wiki/#/en/Universal-Data-License-How-to-use-it#toc_License_Parameter_Tags) to allow for derivations or commercial usage of their content. An exciting aspect of the UDL is its versatility, as it can be applied to other protocols that crowdsource and sell data. For instance, [WeatherXM](https://twitter.com/nikil511/status/1674676524883034122?s=20), a DePIN specializing in weather data collection, has expressed interest in leveraging the UDL for data purchases with specific time constraints.

## Key Raises

_Powered by Messari [Fundraising Data](/fundraising-data)_

#### RISC Zero – $40 Million Series A

[RISC Zero](https://www.prnewswire.com/news-releases/risc-zero-raises-40m-in-series-a-to-bring-its-leading-zero-knowledge-technology-to-web3--enterprise-301880520.html) completed a $40 million Series A funding round led by Blockchain Capital and Bain Capital Crypto, along with other participants. The company brings zero-knowledge technology to Web3 and enterprises, providing cryptographic tools for trustless, scalable, and decentralized computation both on and off-chain. Developers can use RISC Zero's ZK Virtual Machine to build ZK-powered apps using conventional programming languages. The new funding will enable RISC Zero to launch its computing platform, Bonsai, which will offer parallel ZK-proving functionality to developers across any language and any blockchain.

#### Futureverse – $54 million Series A

[Futureverse](https://www.prnewswire.com/news-releases/futureverse-raises-54-million-series-a-to-scale-metaverse-infrastructure-and-introduce-ai-to-the-metaverse-301879447.html) completed a $54 million Series A funding round with participation from 10T Holdings and Ripple. The company's mission is to empower developers and users to engage with metaverse content and applications. Futureverse leverages proprietary AI content generation tools to offer AI generative music, object, character, and animation tools essential for building metaverse applications.

#### Giza – $3 Million Pre-Seed

[Giza](https://www.businesswire.com/news/home/20230711269424/en/Giza-Raises-3M-Pre-Seed-Led-by-CoinFund-to-Bring-Artificial-Intelligence-to-Web3-Smart-Contracts), an AI platform for smart contracts and Web3 protocols, completed a $3 million pre-seed round led by Coinfund, with participation from Arrington Capital, StarkWare, and TA Ventures. Giza aims to enable trustless interaction between smart contracts and machine learning models using zero-knowledge proofs, improving capabilities and intelligence in the smart contract design space.

#### Geodnet – $1.5 Million Funding

[Geodnet](https://www.businesswire.com/news/home/20230706322004/en/Borderless-Capital-Leads-1.5M-Investment-into-the-GEODNET-Foundation-to-Support-a-Precise-and-Trusted-Decentralized-Location-Service) secured $1.5 million in funding for its DePIN network focused on high-precision location services, catering to applications like drones, robotic vehicles, augmented reality, construction, and IoT devices. The token sale, led by Borderless Capital, will pave the way for a broader developer ecosystem in both enterprise and consumer applications.

#### Wynd – $1 Million Pre-Seed

[Wynd Network](https://twitter.com/WyndNetwork/status/1676300634054889473?s=20) raised $1 million in a pre-seed round led by No Limit Holdings and with participation from Big Brain Holdings, Builder Capital, Cogitent Ventures, and angel investors. Wynd's product, Grass, a web proxy with web scraping tools, incentivizes users to contribute their idle bandwidth. The network plans to build a data pipeline for transforming unstructured data into seamless integration with models and analytics.

#### SuperSight – $1 Million Pre-Seed

[SuperSight](https://twitter.com/supersightxyz/status/1678768714408402945) raised $1 million in a pre-seed round from Blockchain Founders Fund, Animoca Brands, Druid Ventures, Emurgo, Next Gen We 3, Vayner Fund, and others. SuperSight combines on-chain and off-chain data sources to enhance search experience in the crypto space. It introduces real-time alerts, trend predictions, and trade capabilities for making more informed decisions.

#### Mind Network – $1 Million Pre-Seed

[Mind Network](https://mindnetwork.medium.com/mind-network-secures-2-5-million-in-seed-funding-from-binance-labs-and-other-prominent-vcs-6e6fff8c0221) has raised $2.5 million in seed funding from investors such as Binance Labs, Comma3 Ventures, SevenX Ventures, HashKey Capital, Big Brain Holdings, Arweave SCP Ventures, Mandala Capital, and others. It focuses on resolving crucial Web3 security challenges by providing solutions for protocol data, smart contracts, and AI. The network offers products like encrypted data lakes and Zero Trust AI, which enables complete data privacy for AI model training and inference.

## Chart Book

![](https://cdn.sanity.io/images/2bt0j8lu/production/014335524686368b9b1ebc7f2a8af8d56176f2a3-1600x900.png?w=714&fit=max&auto=format&dpr=3 "View full size")

The aggregate market capitalization of leading DePINs rebounded to $11.8B, approaching May levels after a dip in June. The wireless network sector has been the primary contributor to the growth, increasing by 37% from the previous month, mainly driven by Helium's surge following its listing on Coinbase.

![](https://cdn.sanity.io/images/2bt0j8lu/production/62f56fe2a0deed24cdb7922d5cb57559298d2999-1600x900.png?w=714&fit=max&auto=format&dpr=3 "View full size")

The compute sector experienced the worst performance during the same period, despite being the best-performing sector in May and early June. The decline in the AI narrative, which previously boosted projects like RNDR, AKT, and FLUX, could be the contributing factor to this underperformance.

![](https://cdn.sanity.io/images/2bt0j8lu/production/218df4977daa44c93338b24fe49a80ed32497247-1600x900.png?w=714&fit=max&auto=format&dpr=3 "View full size")

While the overall market cap has been recovering, revenues from usage across DePINs continue to decline, primarily due to a decrease in revenue from Storj, which previously held the largest share. However, Helium and Livepeer have been generating more revenue and increasing their market shares.

![](https://cdn.sanity.io/images/2bt0j8lu/production/271b815a45511286f61112b14df00278c600d4b6-1600x900.png?w=714&fit=max&auto=format&dpr=3 "View full size")

Within DePIN, Chainlink stands out as the top performer, with its success largely attributed to the timely release of the CCIP bridge, ahead of expectations.

