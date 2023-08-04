---
slug: perpetual-motion
title: Building a Crypto Perpetual Motion Machine
authors:
  name: At0x
  title: chief nerd
tags: [strudel, bitcoin]
---

# Building a Crypto Perpetual Motion Machine

![](https://i.imgur.com/0PBLeYw.jpg)

***"Oh ye seekers after perpetual motion, how many vain chimeras have you pursued? Go and take your place with the alchemists."*** 

— Leonardo da Vinci, 1494

Perpetual motion is the motion of bodies that ***continues forever in an unperturbed system. A perpetual motion machine is a hypothetical machine that can do work infinitely without an external energy source.*** This kind of machine is impossible, as it would violate either the first or second law of thermodynamics or both.

Luckily for us we're dealing with the laws of crypto economics, not thermodynamics. The behavior of monetary systems can in fact be modeled using Physic's first principles and the inmaterial nature of it allows for the creation of systems that go beyon the constraints of the phisical world. However, the laws of thermodiamics offer a glimpse of what is required to create an infinitely sustainable monetary system, which in fact is a perpetual motion machine.

<!--truncate-->

***The first law*** describes the of conservation of energy states postulating that the total energy of any isolated system (for which energy and matter transfer through the system boundary are not possible) is constant; energy can be transformed from one form to another, but can be neither created nor destroyed.

***The second law*** may be formulated by the observation that the entropy of isolated systems left to spontaneous evolution cannot decrease, as they always arrive at a state of thermodynamic equilibrium where the entropy is highest at the given internal energy




## Money is a form of Energy

In physics, ***energy*** is the quantitative property that is transferred to a body or to a physical system, recognizable in the performance of work. Energy is a conserved quantity; the law of conservation of energy states that energy can be converted in form, but not created or destroyed. Money is any item or verifiable record that is generally accepted as payment for goods and services and repayment of debts, such as taxes. In other words, both money and energy can be described as a quantitative property that is transfered in exchange for work. Unlike energy however, money can in fact be created and destroyed. Which is the first key we need to create a perpetual motion machine

## Can Entropy be Reduced?

***“THERE IS AS YET INSUFFICIENT DATA FOR A MEANINGFUL ANSWER.”***

-Multivac, 2061

***Entropy*** is a scientific concept as well as a measurable physical property that is most commonly associated with a state of disorder, randomness, or uncertainty. In the phisical world the overall entropy always increases: things tend to go from a state of order to disorder if left unchecked. Although the total entropy of the universe cannot ever decrease energy (read: money) can be spent to fight off entropy locally. Thats why we eat food in order and reduce our body entropy by repairing and replacing cells. Ultimately however, in the physical world entropy always wins. 

## Entropy Reduction = Value Creation

Imagine you could deploy custom laws of physics. Thats what solidity is like. If entropy is a measure of unceartanty smart contracts are anti-entropy devices for they describe deterministic functions that organize energy(read: money). For example; The UniSwap smart contracts organize thousands of pairs from houndreds of thousands of users in order to allow atomic swaps between any asset pair. The fact that UniSwap is deployed in the network reduces the total entropy and increased the value of everything within.

In the case of StrudelDAO our source of entropy is the vBTC peg. Our protocol aims to reduce this entropy by deploying incentive structures that produce energy (read: money) in order to incentivize actions that achieve this goal. Once we manage to achieve the peg we know that value will have ben created for the protocol which we can compound on by offering a product that can be built upon by other protocols which are also creating on chain value. 

![](https://i.imgur.com/X0iDfFy.png)
![](https://i.imgur.com/ycdmrfp.png)


## the Strudel Bitcoin Metabolism

![](https://i.imgur.com/yoDN0iB.png)

The above graphic is a schematic of an enzimatic pathway. In Biological systems enzimatic pathways are a series of chemical reactions that transform a molecule for a specific purpose. Aditionally, enzimes are interoperable and often have multiple uses throughout the body. Furthermore, enzimatic processes often trigger multiple other processes downstream to create complex behaviours found throughout nature.

The Strudel Protocol employs a similar approach to the design of the incentive scheme for the vBTC peg. In order to produce a pegged Bitcoin asset the protocol employs multiple incentive mechanisms in multiple chains to create complex arbitrage patterns that peg vBTC to the Bitcoin price. 

![](https://i.imgur.com/9z9ZRlc.png)

### Entering the Strudel
The strudel protocol creates an incentive for users to bridge BTC into the ethereum network due to an arbitrage between the vBTC price and BTC price. The price of vBTC is determined by the existing liquidity. Whenever vBTC is above the peg new coins are minted to close the arbitrage. Once inside the ETH network users can use their vBTC in a variety of yield farming oppportunities to earn $TRDL tokens. 


The current deployed components of the protocol interacting with vBTC are:

* ETH
    * Strudel Protocol
        * Bridge Contracts
        * MasterChef yield farm
* Bridge
    * Multichain.xyz
        * ETH<->FTM bridge
* FTM
    * ORKAN
        * Bonds
            * vBTC
            * $M
    * MitiCushqui
        * Stablecoin
            * $M

### Orkanization

In the FTM network, ORKAN offers perpetual bonds offering Orkan tokens for vBTC and $M which generate consistent buying pressure for vBTC which pulls tokens from the Ethereum network into Fantom. Orkan aims to create the largest on chain BTC repository and removes vBTC from circulation, reducing the floating circulating supply and increasing the mainnet vBTC price. At the same time, the reserves acquired will be deployed in order to obtain interest bearing opportunities for $M and vBTC holders throughout the FTM DeFi ecosystem

### Back to Basics: BTC Backed Reserve Currency

The last piece of the puzzle is our stablecoin issuing procotol: [mitiCushqui🏦💰💵](https://y.at/🏦💰💵). This protocol issues a stablecoin backed by USDC and vBTC. We created an oracle that pegs vBTC to the BTC price effectively creating an arbitrage that will mint $M at a discount and redeem for $USDC as long as vBTC is under the peg.  Once the arbitrage is closed $M issuance will serve as a backstop to preserve the vBTC peg as the BTC price varies. 

### Perpetual Motion

The incentive structures decribed above should generate perpetual motion by creating a system which tends to return equilibrium point where vBTC is pegged to the BTC price.  If such state of homeostasis is achieved the system would go on forever mantaining a stable peg for a growing vBTC market. The implications of this scenario for the Strudel Protocol are inmense: 
* Strudel could secure a significant portion of the BTC network for the DeFi ecosystem forever. Merging BTC and DeFI irreversively.  
* ORKAN would become the biggest on chain decentralized repository of BTC. 
* $M would become one of the most reliable reserve currencies in DeFi, serving as a base asset for many other community specific stable assets.




    



