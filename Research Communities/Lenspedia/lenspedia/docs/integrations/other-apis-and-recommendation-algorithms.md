# Other APIs and Recommendation Algorithms

## Other APIs and Recommendation Algorithms

One of the powerful things about web3 social protocols like Lens is that, because all of the data and interaction history is public, developers and teams can build their own custom recommendation and ranking algorithms based on on-chain data.

While Lens offers an array of APIs through the Lens GraphQL API, there are also other options that you can choose to incorporate in your application.

### Karma3

Karma3 is an open protocol that enables developers to curate ranking and recommendation systems for their apps based on on-chain data. This can power personalized search, discovery and recommendation for Lens apps.

[Karma3 Lens Documentation](https://docs.karma3labs.com/decentralized-social/lens-protocol)

[Karma3 API Explorer](https://openapi.lens.k3l.io/)

#### Profile APIs

All profiles in the Lens ecosystem are scored and ranked every hour. The scores and rankings are then made available through different APIs that clients can call depending on their use case.

These APIs are based on 4 different scoring strategies.

[Followship](https://docs.karma3labs.com/developers/lens-protocol/profile-reputations#strategy-followship) - This strategy emphasizes on social engagements as attestations, combining follows, mirrors and comments. The more engagements a profile receives for their posts and profiles, this will result in higher profile scores.

[Engagement](https://docs.karma3labs.com/developers/lens-protocol/profile-reputations#strategy-engagement) - This strategy emphasizes on social engagements as attestations, combining follows, mirrors and comments. The more engagements a profile receives for their posts and profiles, this will result in higher profile scores.

[Influencer](https://docs.karma3labs.com/developers/lens-protocol/profile-reputations#strategy-influencer) - Similar to the engagement strategy, combining follows, mirrors and comments interactions (or attestations) between profiles, but adds another datapoint where posts can be turned into NFT collections by influencers. When these NFTs are collected by others, these are strong signals of a reputable profile.

[Creator](https://docs.karma3labs.com/developers/lens-protocol/profile-reputations#strategy-creator) - Similar to the influencer strategy, we add another datapoint where NFT collections that carry a price tag. These become another strong indicator where an influencer has gained a strong following that NFT mints of posts reflect popular amongst a fan base in a creator economy.

The available Profile APIs are available [here](https://docs.karma3labs.com/developers/lens-protocol/profile-apis).

#### Content APIs

There are also a collection of **feed** algorithms which are designed to provide users with relevant and personalized content suggestions. You can choose the algorithms that best fit your needs and audience.

There are two types of feed algorithms:

**Global Feed**

Retrieve general purpose global content feed, using several strategies

* `/feed/recent` to choose the [Recent](https://docs.karma3labs.com/developers/lens-protocol/content-recommendations#1.-recent) algorithm.
* `/feed/popular` to explicitly choose the [Popular](https://docs.karma3labs.com/developers/lens-protocol/content-recommendations#2.-popular) algorithm.
* `/feed/recommended` to choose the [Recommended](https://docs.karma3labs.com/developers/lens-protocol/content-recommendations#3.-recommended) algorithm.
* `/feed/crowdsourced` to choose the [Crowdsourced](https://docs.karma3labs.com/developers/lens-protocol/content-recommendations#4.-crowdsourced) algorithm.

**Personalized Feed**

Personalized content feed algorithms are meant to generate lists of posts that are most relevant to each user. These algorithms crawl a user's social graph and activity when recommending posts. There's a time decay element in this as well.

* `/feed/personal/{profile}/` following which uses the [Following](https://karma3labs.notion.site/Content-Discovery-on-Lens-Protocol-e13aae4dcfc64532af32d74a521dbca8#76a8be9c6cea4c7d924ae3be58dfc9a3) algorithm.

The available content APIs are available [here](https://docs.karma3labs.com/developers/lens-protocol/profile-apis).

### MadFi

Based on their ML tagging, get a list of recommended profiles for the given profile to follow.

> To use the MadFi API, you must first get and API key. You also must include the api key in the header for `x-api-key`

#### APIs

[Suggested Follows API](https://docs.madfinance.xyz/api/suggested-follows). For a given `profileId`, return a list of recommended profiles that have the same ML tags.

* `https://api.madfinance.xyz/suggested_follows?profileId=0x123`

#### MadFI API Key

For an API key, email them at `contact@madfinance.xyz`

### Airstack

Airstack is an API provider for blockchain and web3 applications.

With Airstack you can access things like general on-chain transactions, dapp-specific events, and NFT marketplace data as well as simultaneously query and combine on-chain and off-chain data.

Airstack leverages GraphQL which allows you to get only the data you require in single query vs traditional REST endpoints which return a predefined set of data.

Developers can get started with Airstack by following the quickstart guide [here](https://docs.airstack.xyz/airstack-docs-and-faqs/\~/changes/RCZ9VCCIc7gOrsTvT2BI/quick-start-and-sdks).

> To use the Airstack API, you must first get and API key. You also mush include the api key in the header for `authorization`. You can view your Airstack API key [here](https://app.airstack.xyz/profile-settings/api-keys).

#### APIs

**Universal Resolver**

The Airstack [Universal Resolver](https://docs.airstack.xyz/airstack-docs-and-faqs/use-cases/universal-resolver/lens) allows you to universally resolve and reverse resolve Lens Profiles to other web3 identities (Farcaster, ENS, Ethereum address). For instance, you can get Lens Profiles from a given user, or get the Ethereum address, Farcaster, and ENS from a given Lens profile.

**Identity API**

The Airstack [Identity API](https://docs.airstack.xyz/airstack-docs-and-faqs/reference/api-reference/airstack-identity-api) allows you to use a Lens profile to query for on-chain data, aggregations, and transactions.
