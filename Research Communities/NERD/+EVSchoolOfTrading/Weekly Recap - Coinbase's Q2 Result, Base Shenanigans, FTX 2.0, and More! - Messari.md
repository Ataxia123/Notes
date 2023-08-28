---
tags: Messari, JMPlusEV
---
# Weekly Recap - Coinbase's Q2 Result, Base Shenanigans, FTX 2.0, and More!

## Coinbase Announces Q2 2023 Result

- Kunal Goel ([@kunalgoel](https://twitter.com/kunalgoel))

![](https://cdn.sanity.io/images/2bt0j8lu/production/f97767ea09a1fe2a45497d44156785272a6af73e-2667x2200.png?w=714&fit=max&auto=format&dpr=3 "View full size")

On Thursday, Aug. 4, 2023, Coinbase announced its Q2 2023 result. The day before the result, we published our [earnings preview](/report/spoiler-alert-coinbase-q2-revenue-estimates) with the help of publicly available data and our assumptions. Coinbase’s net revenue of $663 million beat Wall Street estimates and was in line with our own.

Coinbase saw a 37% quarterly decline in trading volume, gaining market share as industry volumes were down 48%. An increasing share of “simple trades” helped margins, with transaction revenue falling only 13%. Coinbase’s key strength has always been its ability to effectively monetize its large retail base.

As we had estimated, subscription and services revenue overtook transaction revenue for the first time in Coinbase’s history. Blockchain rewards saw meaningful growth of 19%, helped by higher ETH prices and MEV rewards. Interest income fell by 16% as USDC supply fell sharply after the depegging event in March 2023.

Coinbase had a second quarter in a row of positive adjusted-EBITDA. The company is focused on building volume share from pro users, and its recently launched [international derivatives exchange](https://www.coinbase.com/blog/introducing-coinbase-international-exchange) will help it in that regard. The quarter’s results demonstrate Coinbase’s resilience and strength of execution as it has effectively transitioned away from purely trading fees as a revenue driver.

## Base Chain Shenanigans

- Chase Devens ([@chasedevens](https://twitter.com/chasedevens))

On July 13th, Coinbase [announced](https://base.mirror.xyz/hwNwqXHVoLlO8s4DZppog4DfGvM34tigaDjOWuEJQfY) that its Base Layer-2 mainnet was open to developers. As part of the guarded rollout, Coinbase purposefully chose to not feature a public bridge UI. Instead, Coinbase created a portal proxy contract that would allow builders to bridge ETH into the rollup and test their contracts. However, this was a one-way path and was not designed to allow ETH to exit Base.

All went according to plan for roughly two weeks… until someone decided to launch a meme coin. $[BALD](https://twitter.com/BaldBaseBald) was created on July 29th as a reference to the bald head of Coinbase CEO Brian Armstrong. As the token deployer slowly added a large amount of liquidity to the LeetSwap DEX pool, crypto Twitter caught wind. Over the ensuing 48 hours, 40,000+ ETH was bridged into Base chain to speculate on $BALD. This pushed the market cap of the token past $80 million before the original deployer removed their ETH liquidity from the DEX pool, causing a 95% price crash.

![](https://cdn.sanity.io/images/2bt0j8lu/production/0823476ede76bd8b4c036bf022e7b1a6c1fc3f64-1600x900.jpg?w=714&fit=max&auto=format&dpr=3 "View full size")

Early speculators that took profit on $BALD had no exit due to the design of Base’s one-way bridge. Rather than wait patiently for an exit, a large amount of this newfound ETH-based wealth was recycled back into other freshly launched meme coins. The hysteria lasted until July 31st when LeetSwap, the DEX that supported the liquidity for all these new meme coins, was hit by an exploit where attackers were able to drain various liquidity pools. LeetSwap paused trading functionality on their contracts which marked a temporary end to Base’s speculative mania.

On August 3rd, Base [released](https://twitter.com/BuildOnBase/status/1687089210216595456?s=20) a public bridge UI that now provides an easy way to bridge in and out of Base mainnet from Ethereum. Whether this leads to a flight of capital from the ecosystem or another leg of speculative buying is something to look for in the days to come.

All in all, the events provide a few notable takeaways:

- Testing and investing in production has its consequences. Coinbase’s attempt to roll the Base mainnet out to builders was intended to provide a developer sandbox. However, it quickly turned into a playground for degens and resulted a hack that may have been prevented had LeetSwap had more time to properly roll out its codebase.
- This is further proof that if there is an incentive offered in crypto, capital will find a way to quickly take advantage of the opportunity. Meme coins may just be the fastest way to bootstrap a new ecosystem and could become a strategic offering for new ecosystems moving forward.

  

## Curve TLDR

- Thomas Bautista ([_ThePinkyToe](https://twitter.com/_ThePinkyToe))

The genesis of the Curve debacle starts with Michael Egorov, the founder of Curve. Owning roughly 50% of CRV’s [float](https://platform.arkhamintelligence.com/explorer/address/0x7a16fF8270133F063aAb6C9977183D9e72835428), Egorov loaned out as much as 460 million CRV tokens across 3 protocols, AAVE, Fraxlend, and Abracadabra. Through holding the majority of CRV liquidity via collateral, a drop in the price of CRV might not only lead to a liquidation of Egorov’s positions but kickstart a liquidation cascade throughout DeFi.  
  
His positions were largely ignored until last weekend when a blockchain security company tweeted a potential exploit in a CRV [pool](https://twitter.com/peckshield/status/1685645064364822530?utm_source=substack&utm_medium=email). Shortly after, three other Curve factory pools were drained: CRV/ETH, alETH/ETH (Alchemix Finance), and msETH/ETH (Metronome). This revealed a reentry vulnerability from an older version of a Vyper compiler (an alternative to Solidity that turns programming code into EVM smart contract code). The Curve code itself was not [compromised](https://twitter.com/CurveFinance/status/1685925429041917952?utm_source=substack&utm_medium=email), it only affected pools that utilized the affected version of Vyper. Around $50M was drained, but some portion was returned by white-hat MEV bots.

The panic quickly spread, causing a sharp drop in $CRV price from around $.73 to lows of $.50. Total value locked also dropped 50% as users took their assets off of Curve.

![](https://cdn.sanity.io/images/2bt0j8lu/production/a507a424db6b9e07b56476c9c9c437402ca5e9f3-2667x1500.png?w=714&fit=max&auto=format&dpr=3 "View full size")

While the extent of Curve risk was limited to those four pools, Egorov’s loans remained in the crosshairs. His largest one is a $63M loan from AAVE (using 300 million CRV as [collateral](https://finance.yahoo.com/news/curve-exploit-curve-founder-michael-081342185.html)) with liquidation starting at $.3767 CRV/USDT, This would only require a 33% drop in CRV price.

His riskiest loan, however, is a $15.8M loan against 59M Curve on Frax Finance. Fraxlend isolates borrowing pairs, meaning if there's bad debt on one pair (ie. CRV/ETH), it only affects that pair and not the rest of the platform. Frax’s Time-Weighted Variable Interest Rate facilitates this. Interest rates are implemented based on the usage rates on Frax; rates increase significantly on heavy pool utilization.

On July 31st, the pool reached 100% utilization, meaning his interest rate would double every 12 hours. To combat the massive rates, Egorov created a new Curve pool by incentivizing users to withdraw Frax LP tokens from Fraxlend into the Curve pool, thus lowering the utilization. This strategy seems to be working, as the current utilization rate sits at 41.73%.

![](https://cdn.sanity.io/images/2bt0j8lu/production/0d261f3d925df9bd1b5ddfc247e2225a0a8b3792-1368x675.jpg?w=714&fit=max&auto=format&dpr=3 "View full size")

Because of Frax’s interest rate mechanism and the magnitude of his AAVE loan, Egorov was incentivized to maintain those loans first. Abracadabra, the final counterparty, responded with a governance proposal of their own. First, their governance community proposed a new mechanism for CRV [loans](https://forum.abracadabra.money/t/aip-13-5-interest-rate-adjustment-for-the-crv-cauldrons/4320), doubling the interest rate for loans >10M, and 25xing that rate if the LTV exceeded 70%. It got rejected but was immediately reproposed with different parameters. The new proposal is expected to be approved by [August 5th](https://snapshot.org/#/abracadabrabymerlinthemagician.eth/proposal/0x49753e11f62c79e12ab53de007558cb0acd055ed23302865ba3464dd40099344).

How does Egorov respond? While the state of his personal finances is widely [speculated](https://www.theblock.co/post/232464/curve-finance-ceo-michael-egorov-wife-mansions-australia), he has conducted massive OTC deals to generate liquidity. Totaling around 60M [CRV](https://twitter.com/sandraaleow/status/1686876643099611136) (rumored at $0.40), it appears that he has succeeded at pooling potential liquidity to support his loans. However, if CRV’s price continues to waver, it is worth monitoring his [activity](https://platform.arkhamintelligence.com/explorer/address/0x7a16fF8270133F063aAb6C9977183D9e72835428).

## FTX 2.0

- Kel ([@kelxyz_](https://twitter.com/kelxyz_))

Approximately ten months after the exchange's collapse, FTX's current CEO, John J. Ray III, has unveiled a restructuring plan to bring the exchange back to life as FTX 2.0.

The core of the restructuring plan involves dividing users and former FTX lenders into distinct classes of creditors. For international exchange creditors, a unique opportunity arises - they can choose to pool their funds and participate in the revival of the exchange. In return, these creditors would relinquish any cash payouts and instead receive a stake in the newly minted FTX 2.0.

The response from creditors has been polarized, leading to a fierce debate. On one hand, there are those who oppose the idea of restarting the exchange. They argue that any potential payout from the revitalized FTX might take an extended period to materialize, if it ever does. They advocate for certainty, preferring to liquidate all assets as swiftly as possible and return the value to creditors in cash.

Conversely, supporters of the restructuring plan recognize the remarkable profitability FTX enjoyed before its collapse. They argue that breathing new life into the exchange could offer significant upside potential, enabling them to fully recoup or even profit on their creditor claims. In contrast, liquidating assets guarantees a substantial haircut, likely amounting to 50% or more of their obligations.

The debate gained further attention when Jesse Powell, the CEO of fellow crypto exchange Kraken, weighed in with a dissenting view. He pointed out the challenges that lie ahead for FTX 2.0, stating that the exchange currently lacks a team, technological infrastructure, licenses, and banking relationships. Furthermore, the brand's reputation remains tarnished, making it difficult to rebuild trust with the crypto community and attract customers.

The final decision rests with the international exchange creditors themselves. They must weigh the potential risks and rewards of participating in FTX 2.0's revival. Time will be the ultimate arbiter, revealing whether these creditors choose to take a chance on the new venture or opt for the certainty of a cash liquidation. As the crypto world closely observes the outcome, FTX's resurrection journey holds significant implications for the future of cryptocurrency exchanges and the handling of similar crises within the industry.

