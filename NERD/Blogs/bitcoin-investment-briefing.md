---
slug: strudel-briefing
title: Strudel Bitcoin Investment Briefing
authors:
  name: At0x
  title: chief nerd
tags: [strudel, bitcoin]
---


## The Strudel Bridge

![](https://i.imgur.com/xKZ9G1Z.png)

**By eliminating the need for custodial control of assets** that come with typical wrappers, the Strudel protocol trades off counter-party risk for market risk while using **market dynamics, crypto-economic incentives, and cross-chain capabilities** to maintain a pegged, scalable, and capital-efficient ecosystem. This one-of-a-kind economic approach offers average users and big money investors numerous options for monetary growth and grants more diversity and security to DeFi.

<!--truncate-->

# Problem Statement

**Bitcoin**  is poorly incorporated into web3. The existing landscape relies mainly on wBTC, a trusted bridge operated primarily by funds such as 3AC, which have the exclusive right to mint and burn wBTC, therefore cornering the benefit of the arbitrage between on-chain BTC and legacy markets.

Vitalik [has stated](https://twitter.com/VitalikButerin/status/1295252403558559746?s=20&t=UvAU_6bfaNeaIVcafixefg) that trusted BTC bridges pose a systemic risk to the DeFi ecosystem. I would go even further and say that DeFi cannot grow until its intimately integrated with BTC and we capture a significant % of the BTC network on-chain. To achieve this goal, we must find a robust solution to bridge many BTC into the Web3 economy.


 
## The On Chain Bitcoin Landscape

[Updated Dashboard](https://dune.com/eliasimos/btc-on-ethereum_1)
![](https://i.imgur.com/AyKNaM9.png)
![](https://i.imgur.com/vYAyc5x.png)



**Key Takeaways**

- Less than 1.5% of the BTC supply is currently bridged on-chain.
- On-chain, BTC balances are very stable compared to price volatility.
- Trusted bridges (wBTC+hBTC) represent over 90% of all the BTC bridged on-chain.
- Decentralized alternatives have not found strong PmF: RenBTC only has 4,000 BTC bridged. Hardly 2% of the total on-chain BTC


## Strudel Bridge Architecture

When BTC is requested to be transferred using the Strudel dApp, a transaction output with the transfer amount and the receiving Ethereum wallet address is created. This output is handed to the user’s Bitcoin wallet through the QR code. When a user signs a transfer, the resulting transaction might look like this.

![](https://i.imgur.com/eGRRlhh.png)

Next, the header of the Bitcoin block containing the transaction needs to be registered in the relayer contract on Ethereum, where its proof-of-work is verified, and the canonical chain is extended. Simple payment verification (SPV), a protocol used by Bitcoin light clients and wallets, prevents invalid blocks from entering the relayer.
Once the transaction containing the burn has been buried under enough proof of work (6 blocks), an inclusion proof is relayed onto Ethereum. The proof is verified by the Strudel contract, which mints vBTC in a ratio of 1:1 to the designated Ethereum address. The protocol strictly mints one vBTC for one burned BTC, not taking any fees for bridge crossings.

## Strudel Bitcoin

Token Address: 0xe1406825186d63980fd6e2ec61888f7b91c4bae4

Current vBTC Supply: 23.27238764 

Token Distribution:

Hodlers: 461 

Total Liquidity: ~120,000 USD combined

Market Cap: 230,000 USD


![](https://i.imgur.com/llQkTCg.png)



Once BTC crosses the bridge using the Strudel Protocol its issued as Strudel Bitcoin (vBTC) on the Ethereum network. vBTC is **fully erc20 compliant** with 18 decimals and flash loan capabilities. 

https://etherscan.io/token/0xe1406825186d63980fd6e2ec61888f7b91c4bae4
https://ftmscan.com/token/0x9049198f6b21acf1e050cfcf36a6879a07b0bbe4

### Historic Performance

![](https://i.imgur.com/vVcjWIe.png)
![](https://i.imgur.com/c5Jhu6c.png)



- vBTC has outperformed both ETH (+86%) and BTC (+53%) YTD
- The Strudel Protocol controls > 50% of vBTC, which are acquired through Orkan.Finance bond issuance and MitiCushqui stablecoin issuance.



### Liquidity landscape

Strudel utilizes a [mandate based approach](https://app.gitbook.com/o/V40TVngLYntzpq24zWhI/s/9QESb5e46FBDH1t8kShd/monetary-policy/mandates) to guide the development of the protocol

**Mandate #1 - Achieve true decentralization of BTC on DeFi
Mandate #2  - Design incentive structures that issue and manage reserve backed currencies**

By utilizing vBTC as a reserve asset, we reduce the floating supply and therefore provide price stability when interacting with demand driven by incentives to provide liquidity for vBTC

**Liquidity Incentives**

The first stop for vBTC once bridged is the strudel. Finance farms. The protocol utilizes a sushi-style LP farm to issue 1 $TRDL per block split evenly among the following positions:

- $TRDL:ETH(Pool0) (320%APY)
- vBTC:$TRDL (73.51%APY)
- vBTC:ETH (14.96%APY)
- vNFT::vBTC:PUNK:CC:BAYC (NA* APY)

*have to develop code to calculate price on multi asset pool to use in APY formula. 

**Reserve Backed Currencies**

**Orkan.finance**

**$vBTC's peg through The Orkan** 
- When $vBTC gets under the peg, $ORK bonds are issued to increase the treasury supply and therefore remove $vBTC from circulation
- When $vBTC gets above the peg, previously acquired $vBTC is exchanged by the protocol for other assets to diversify the treasury basket or to buy back and burn $ORK.

![](https://i.imgur.com/b2V7Yoo.png)

**vBTC as a Store of Value**

The Orkan treasury has managed to retain most of the value issued for the purchase of vBTC even though the market has gone through a significant downturn. ORK is trading at .40c, whereas the backing per token is 1.22c.

**🏦💰💵MitiCushqui🏦💰💵**

![](https://i.imgur.com/axrQqVG.png)


We recently deployed MitiCushqui, a [stablecoin issuing protocol](https://y.at/🏦💰💵). This protocol can be used to deploy redeemable stablecoins backed by a fixed ratio of a base stablecoin and any other asset. 

The protocol oracles the BTC price and therefore creates an arbitrage where users can mint $Miti  at a discount and redeem for USDC. The vault keeps vBTC out of circulation therefore reducing the supply and increasing the price until the arbitrage is closed and the peg is met. 

![](https://i.imgur.com/UC5UXFw.png)

## The Future of Bitcoin is on-chain and the on-chain future is Bitcoin.

To make the web3 ecosystem more robust, we need to onboard a more significant percentage of BTC on-chain. A way to achieve reliable yields is to incentivize the flow of BTC into Web3. This capital can finance projects that generate value for the entire space. This makes BTC more useful, which is vital For it to gain mainstream adoption.

The future of BTC cannot depend on any one group of developers or caretakers. To realize its potential, we must find ways to bridge it into the Web3 ecosystem by utilizing as many techniques as possible and later building tools to create an interoperable interface



Learn More:

Strudel Twitter: @EnterTheStrudel
At0x Twitter: @At0xNQ
Nerd Chat: https://y.at/🤓✉️🤓
Strudel Landing: https://y.at/🌪🌪👀
MitiCushqui: https://y.at/🏦💰💵
