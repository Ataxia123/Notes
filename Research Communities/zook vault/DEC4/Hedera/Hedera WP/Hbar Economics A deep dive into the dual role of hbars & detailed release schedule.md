```
V3 | LAST UPDATED JUNE 3, 2020
HEDERA HASHGRAPH, LLC
```

# Hbar Economics

## A deep dive into the dual

## role of hbars & detailed

## release schedule

## 01. Overview PAGE 4

### Hbars as “fuel” to pay for

### network services and incentivize

## node participation PAGE 6

### Hbars protect the network

### through coin-weighted,

## proof-of-stake consensus PAGE 10

### Treasury Management

## & Distribution Schedule PAGE 14

**02.**

**03.**

**04.**

### TABLE OF CONTENTS

##### Hedera Hashgraph is a public distributed ledger technology (DLT) network that

##### enables people to interact and transact online efficiently and securely without

##### the need for third-party companies, which often collect and sell their users’

##### personal information.

##### The purpose of Hedera is to provide a stable, trustworthy network for a

##### wide variety of decentralized, enterprise-grade applications, not to provide

##### a cryptocurrency. Like all public DLT networks, however, Hedera needs a

##### cryptocurrency to function. Hbar is the native cryptocurrency of the Hedera

##### network. Hbars are used to power decentralized applications, build peer-to-peer

##### transactional models, and protect the network from malicious actors.

##### Hbars serve two main functions:

##### 1. Network Fuel - Hbars serve as a “fuel” to pay for network services and

##### incentivize nodes to contribute computing resources to the network.

##### 2. Network Security - As Hedera moves along the path to permissionless nodes,

##### hbars will protect the network against cyberattacks through the network’s

##### forthcoming coin-weighted, proof-of-stake consensus mechanism.

This paper describes how hbars are used on the Hedera network, their role in achieving consensus

on and securing transactions, and the expected distribution of Hedera’s fixed supply of 50 billion

hbars. The information presented herein is provided for informational and illustrative purposes

only and remains subject to change.

_NOTE: This version (v3) of the Hbar Economics whitepaper was updated on June 3, 2020.  
The previous version (v2) of this whitepaper was published on October 9, 2019  
and can be downloaded here:_

https://www.hedera.com/hh-hbar-coin-economics-paper-100919-v2.pdf

**01.**

## Overview

**HEDERA TECHNOLOGY**

The Hedera network works through a groundbreaking form of distributed consensus technology—the hashgraph  
consensus algorithm. Like blockchains and other DLTs, Hedera allows online communities to create a shared,  
trustworthy database without the need for a third-party middleman. Other DLT networks face trade-offs between  
performance and security (if they are faster, they are less secure; if they are more secure, they are forced to slow down).  
In contrast, hashgraph technology provides superior levels of performance and security. With hashgraph, transactions  
are processed at speeds that are orders of magnitude faster than proof-of-work blockchains, and the hashgraph  
algorithm has been proven mathematically to offer the highest level of security for distributed networks.

Because the Hedera technology is dramatically faster and more secure than blockchain-based networks, it enables a  
whole range of new applications, use cases, and business models not currently possible on other DLT networks.

Developers and enterprises can use Hedera’s network services (cryptocurrency, smart contracts, file, and Hedera  
Consensus Service) to create applications that run on top of the network. The network supports the potential for an  
exceptionally wide range of applications — from music-streaming services to pharmaceutical supply chain management  
to energy microgrids to multi-player online games.

**HEDERA GOVERNING COUNCIL**

The Hedera network is governed by the Hedera Governing Council, a rotating group of high-profile, leading global  
organizations that span across multiple industries and geographies. The primary responsibilities of Council members  
are to (i) participate in the governance of the Hedera network and (ii) host and maintain a node on the Hedera  
network. Council members contribute their expertise and experience in Council deliberations and decision-making  
relating to software updates, Hedera Treasury management, network pricing, regulatory compliance, and other key  
governance matters.

Each Council member holds an equal ownership interest in Hedera and has equal voting rights on governance matters.  
Council membership does not confer any economic interest in Hedera, such as rights to dividends or a share of profits. **¹**  
Other than Swirlds, Inc. (which has a permanent Council seat), each Council member is term-limited to two consecutive  
three-year terms, and members will accordingly rotate on and off the Council.

In these ways, the Governing Council is structured to ensure decentralized, transparent, stable, and effective  
governance on behalf of the long-term interests of the network. In contrast to other blockchain networks, Hedera is  
not governed by small and/or relatively unknown groups of miners and developers. This enterprise-led structure greatly  
reduces the risk of ideological or personal disputes that have affected governance of other public DLT networks.

In short, Hedera’s technology and governance make it scalable and well-suited to become the first public DLT network to  
achieve widespread acceptance and adoption, particularly by enterprises.

**1** (^) Council members are entitled to node fees and node reward payments that they earn as node hosts in order to offset the costs of running a node.

**HEDERA’S “HBAR” CRYPTOCURRENCY**

The Hedera network was launched in August 2018. At that time, the network’s total fixed supply of hbars—  
billion hbars—was minted and placed into a Hedera Treasury account. The Hedera Treasury will consist of multiple  
cryptographically secure, multi-signature accounts. Hbars can be transferred out of a Treasury account only after  
a transaction is cryptographically signed by a majority of the Governing Council members. This ensures that control  
over the network’s cryptocurrency remains decentralized and vested in large, trustworthy entities.

For more than a year after the network launched, almost all hbars remained in the Hedera Treasury account, aside  
from a small amount of hbars (6.7 million hbars) to early users to test the network as part of its community testing  
program. Then, after more than a year of testing, the Hedera network opened to the public on September 16, 2019,  
so that anyone could create an account on the Hedera network, and any developer could build and deploy applications  
on the network. A few hours after that transition to “open access,” the Hedera Treasury began distributing hbars to  
SAFT holders, with some additional hbars distributed to employees, advisors, vendors, and others in the subsequent  
days. Additionally, hbars appeared on exchanges, so developers and users could begin purchasing them to use on  
the network.

Hedera’s hbar release plan calls for a slow, measured release of hbars out of the Hedera Treasury. Only ~4% of the  
total hbar supply were circulating at the start of 2020 and less than 31% are expected to be circulating by the end  
of 2025. This release schedule is one of the mechanisms that will ensure that no would-be attackers will be able to  
disrupt the network. It also will ensure that the price of hbars is determined primarily through market forces, rather  
than by the Hedera Council.

## Hbars as “fuel” to pay for network services and

## incentivize node participation

```
All public DLTs need computers to serve as nodes in the decentralized network. These nodes serve two purposes:
```

1. Shared Ledger: Each node maintains a copy of the ledger of the balances in each network user’s account.
2. Execute Transactions: Nodes verify and execute new transactions and place those transactions into  
    consensus order, so that user account balances are updated on an ongoing basis.

```
Each node must provide computing power to run the network’s consensus algorithm and process transactions. To
incentivize nodes to participate—as computing power is not free—public DLTs typically compensate nodes with payment,
often in the network’s native cryptocurrency.
```

```
On the Hedera network, hbars are used as a “fuel” to pay for network services (i.e., to submit transactions, run smart
contracts, store files, use the Hedera Consensus Service) and to reward nodes for providing their computing resources
(bandwidth, processing power, memory) to the network. The fees per transaction are very low, requiring the ability to
make micropayments in a form—an hbar—that is divisible to less than a penny. For example, transactions using the
cryptocurrency service or Hedera Consensus Service are expected to cost ~US$0.0001 (one one-hundredth of a cent).
```

```
The economics of a Hedera transaction have been designed to balance these costs and incentives to create an efficient
flow of funds. This flow consists of:
```

1. Transaction fees paid by end users (or third-party applications as end users) into a Hedera account, and
2. Reward payments paid out of a Hedera-controlled account as (a) node reward payments to node hosts  
    and (b) eventually, proxy-staking reward payments to hbar owners who proxy-stake their hbars to nodes. **²**

```
For example, if Alice sends 5 hbars to Bob, those 5 hbars are sent directly from Alice’s account to Bob’s account—the
5 hbars do not pass through a Hedera-controlled account—but Alice pays a node fee, a network fee, and a service fee,
the latter two collected by a Hedera-controlled account.
```

**02.**

**2** For more on proxy-staking, see Part 3. Node reward payments and proxy-staking payments are not yet being made. Proxy-staking  
payments are expected to be de minimis.

**TRANSACTION FEES**

End users pay fees to use the network. Fees are incurred, for example, when hbars are transferred or data is added  
to the Hedera hashgraph ledger. The fees for a particular action will depend on the type of network services used  
(cryptocurrency, smart contracts, file service, Hedera Consensus Service) and the degree and duration of network  
resources consumed in processing the transaction. The overall fee for an action on the network is called a Transaction  
Fee, which is composed of three distinct fees—a Node Fee, a Network Fee, and a Service Fee. Each of these fees relate  
to how the transaction is submitted to and validated by the network, and the amounts of these fees are set by the  
Hedera Council. In addition, developers offering applications on the Hedera network may also charge their users an  
Application Fee.

Although a network user pays an aggregate Transaction Fee, below is additional detail on the three Transaction Fee  
components and the optional Application Fee:

**1. NODE FEE:** A user or application seeking to complete a transaction on the network will send that transaction to  
a single node, which will then submit that transaction to the network. In doing so, that node will expend resources  
and energy (albeit a small amount). Node Fees compensate nodes for those resources and incentivize nodes to  
take on this critical role. Node Ffees are paid from the end user’s account directly to the account associated with  
the node that submits the user’s transaction to the network.  
**2. NETWORK FEE:** After a transaction is submitted to the network, it is communicated to nodes that validate  
digital signatures, further communicate the transaction to other nodes, and temporarily store it in their memory  
while the network reaches consensus. Users pay a Network Fee that compensates all participating nodes for  
calculating consensus on the user’s transaction. The computing resources consumed by this process can vary  
based on the file size of the transaction and the number of digital signatures. Network Fees are paid by users into  
a Hedera-controlled account that collects all Network Fees and Service Fees (defined below).

```
TRANSACTION FEES
```

```
APPLI C ATION F E E ( IF ANY)
```

```
N O D E ACCOUNT
```

```
T R E A SURY ACCOUNT
```

```
N O D E FEE
```

```
N ET WORK FEE
```

```
SERV ICE FEE
```

```
E N D U S E R AC O UNT
```

```
TRAN S AC T ION F E E
```

**3. SERVICE FEE:** Service Fees are paid by an end user to compensate the network for the services associated with  
the transaction (e.g., a cryptocurrency transfer, smart contract processing, file storage, or message ordering).  
For example, for a file service transaction, the network will charge a Service Fee corresponding to the amount of  
energy and memory needed to store a file based on its size and the requested duration of time it will be stored on  
the network. For a smart contract transaction, the Service Fee will be based on the processing power required by  
network nodes to perform the computation required by the smart contract. Service Fees are paid by users to a  
Hedera-controlled account that collects all Network Fees and Service Fees.  
**4. APPLICATION FEES (OPTIONAL):** Developers who build applications on top of the Hedera network may want  
to monetize those applications to compensate themselves for the value they provide to the end users. A wallet  
application, for example, may choose to charge a small percentage of each deposit or withdrawal. A ridesharing  
dapp that connects drivers to passengers with no intermediary may choose to take a fee calculated as a small  
percentage of each ride completed and paid. Like many existing applications, some Hedera-based applications  
may offer both free services and paid services. A third-party developer will determine the amount of Application  
Fee she wishes to charge, and these fees will be paid by end users directly to the developer’s account.

```
For more information on fees, visit https://www.hedera.com/fees.
```

```
NODE REWARD PAYMENTS
```

```
A distributed network needs to incentivize nodes to contribute computing resources to validate transactions and
maintain the shared ledger. Like most DLT networks, Hedera will reward nodes by paying them in the network’s native
cryptocurrency.³
```

```
When node reward payments are implemented, it is expected that, every 24 hours, a Hedera-controlled account will
automatically distribute hbars as node reward payments to all the nodes that were online and participated in validating
transactions during that period. After the node software provides the ability to proxy-stake coins to node accounts,
node reward payments will be distributed to nodes in proportion to the amount of hbars staked and proxy-staked to
such node’s account. (Proxy-staking is explained in Part 3)
```

```
This node incentive system is far more efficient than proof-of-work, “winner-take-all” networks. In those networks,
mining nodes expend energy to try to solve the cryptographic puzzle, but only the winner receives a payment. All the
energy consumed by the other nodes is wasted. On the Hedera network, no energy is wasted, as nodes do not expend
energy on useless math problems, but directly on communicating, validating, and supporting transactions.
```

**3** During the initial period of the Hedera network, Hedera is not making node reward payments as described herein.

```
Node
```

```
3 rd Party Applications
```

```
Transaction
Fees
```

```
Node Reward Payments
```

```
End Users
```

```
Exchange
```

```
Hedera Network
```

```
Node Node
```

```
dapp dapp dapp
```

```
Proxy
Staking
Payments
```

```
StakProxyers
```

```
LIFECYLE OF COINS
```

```
DUAL ROLE OF HEDERA COINS
```

```
NETWORK “FUEL” NETWORK PROTECTION
Any distributed ledger can be attacked if a
malicious actor controls 1/3 of voting power
Hedera’s proof-of-stake system uses
coins to weight the votes, making it diicult
and expensive for a bad actor to gain control
of 1/3 of the voting power, i.e., 1/3 of
the coin supply
```

```
Coins are used to pay for network services
(i.e. submit transactions, run smart
contracts, store iles)
Coins are used to reward nodes for providing
services to the network
Coins enable micropayments (< $0.01)
```

**PROXY-STAKING PAYMENTS**

After proxy-staking is implemented on the Hedera network, it is expected that, initially, only Hedera will proxy-stake  
coins to nodes. Eventually, Hedera plans to allow any user who holds hbars to proxy-stake their coins to nodes. At this  
time, Hedera will begin making proxy-staking payments to user accounts that have proxy-staked coins to active nodes.  
These payments, like node reward payments, will be made once every 24 hours. Payments relating to a user’s proxy-  
staked coins will be split 50-50 between the node’s account and the user’s account. The amounts of such proxy-staking  
payments are expected to be minimal.

Hbars that are staked or proxy-staked always remain under the control of their owner. Their owners can spend them at  
any time, and those who proxy-stake their hbars can turn off or redirect the proxy-staking to another node at any time.

## Hbars protect the network through coin-weighted,

## proof-of-stake consensus

```
In the initial phases of the network, Hedera is a permissioned network, meaning one in which an entity or person must
have permission from Hedera to host a node. Currently, all nodes in the Hedera network are operated by Hedera and
Council members. Hedera is currently in the process of transitioning full operation of the nodes to the Council members.
```

```
In the future, Hedera expects to allow other entities and persons to be able to host nodes on the Hedera network.
Through Hedera’s planned proof-of-stake consensus model, hbars will play a key role in how the Hedera network achieves
consensus on transactions and protects the network from cyberattacks.
```

```
ALL PERMISSIONLESS DLTS NEED A LIMITED RESOURCE
In any permissionless DLT network, anyone can run a node that participates in consensus. In addition, it is easy to
stand up numerous virtual nodes. As a result, there is a need to guard against malicious actors that seek to disrupt
the network and prevent it from reaching consensus on transactions. Hackers can do this by obtaining control of a
specified amount of the network’s total voting power over consensus — the amount varies across networks but is
typically no less than one-third of the voting power. Permissionless DLT networks need a scarce resource to secure the
networks against such attacks. ⁴
```

```
IN PROOF-OF-WORK, THE LIMITED RESOURCE IS COMPUTING POWER/ENERGY CONSUMPTION
In “proof-of-work” blockchains, such as Bitcoin and Ethereum, computing power and associated energy consumption
are limited resources. Network nodes (“miners”) group transactions into “blocks” and compete to solve a complex
cryptographic puzzle to “win” the race to add the next block to the ledger, creating an ever-growing, immutable chain
of blocks. The nodes are incentivized to do this work because the winner receives a payment of cryptocurrency. The
proof-of-work mechanism—i.e., the cryptographic puzzle—is designed to add friction, to slow the system so that blocks
are not added more quickly than the platform can reach agreement on their order. Solving the cryptographic puzzle
requires significant computing power, and that computing power in turn requires significant energy consumption. A
would-be attacker cannot easily set up enough nodes to disrupt the process of consensus, because doing so would
require a prohibitively expensive amount of computer hardware and energy consumption.
```

**4** Any distributed network can be hacked if malicious actors control a certain amount of the network’s voting power over consensus.  
For Hedera, this is 1/3 of the voting power.

**03.**

```
PROOF-OF-WORK VS PROOF-OF-STAKE
```

```
Scarce resource = coins
Energy eicient
Faster to reach consensus
```

```
Proof-of-stake systems
```

```
Power
Stations
Miners
```

```
Scarce resource = computing power
(i.e., electricity)
Signiicant waste of electricity
Slower to reach consensus
```

```
Proof-of-work blockchain
```

**IN PROOF-OF-STAKE, THE LIMITED RESOURCE IS THE NETWORK’S CRYPTOCURRENCY**  
In “proof-of-stake” DLT systems, the network’s native cryptocurrency serves as the scarce resource that  
protects the network. Rather than each node having an equal vote, a node’s ability to influence the consensus  
order of transactions is proportional to the amount of coins the node holds (i.e., its “stake”). The particular  
manner in which a node’s stake relates to achieving consensus varies from platform to platform, but it always  
occurs through the platform’s algorithm and is in some way proportional to a node’s stake of cryptocurrency.

In typical proof-of-stake systems, all of the network’s coins are created at the launch of the network (e.g.,  
all 50 billion hbars were created at the time of the Hedera network’s launch). There is no “mining” of new  
coins through expensive, energy-inefficient computations. As a result, proof-of-stake systems generally have  
much lower transactions costs and can process transactions much more quickly and cheaply than proof-of-  
work systems.

**HEDERA PREVENTS CYBERATTACKS THROUGH COIN-WEIGHTED VOTING ON CONSENSUS**  
In Hedera’s proof-of-stake system, hbars will function as the limited resource to protect the network. Any distributed  
ledger using the hashgraph consensus algorithm will achieve consensus on a transaction when the voting involves more  
than two-thirds of the network’s voting power. A malicious attacker, then, would need to attain one-third of the total  
voting power over consensus to disrupt the network. **⁵**

- 10 nodes
- 1 run by bad actor

```
1 of 10 is malicious
(10% < 33.3%)
```

- 10 nodes, 100 total coins
- Each node has 10 coins
- 1 run by bad actor

```
1 node holding 10 ocoins is maliciousf 100
(10% < 33.3%)
```

- 14 nodes
- 5 run by bad actor

```
5 of 14 are malicious
(36% > 33.3%)
```

- 14 nodes
- 5 run by bad actor
- Still only 100 total coins

```
4 nodes holding 10 of 100
coins are malicious
(10% < 33.3%)
```

SCENARIO A: Networks with no coins – Attack threshold: **1/3 of nodes**

```
Consensus achieved
```

```
Consensus achieved Consensus achieved
```

```
Network disrupted
```

SCENARIO B: PoS networks with coin-weighted voting – Attack threshold: **1/3 of coins**

###### Resistant to

###### Sybil attacks

###### Vulnerable to

###### Sybil attacks

```
Attacker sets up
4 virtual nodes
```

```
Attacker sets up
4 virtual nodes
```

- In a distributed platform, consensus is reached when a transaction is validated by >2/3 of the platform’s voting power
- To mount a successful attack, a bad actor must control 1/3 of the voting power
- Coin-weighted, PoS voting protects against Sybil attacks by making it difficult to reach that 1/3 threshold

```
COIN-WEIGHTED VOTING ON CONSENSUS
```

**5** Note: The Hedera Governing Council does not exercise discretion over node voting to validate transactions. On the Hedera network, governance  
(in which Council members vote through individual representatives) is separated from consensus (in which nodes vote automatically per the  
hashgraph consensus algorithm). While the Council members operate the initial nodes, those nodes “vote” automatically by running the algorithm.

```
HEDERA PLATFORM WITH COIN-WEIGHTED VOTING
```

In permissioned DLT networks, in which all node hosts are known and trusted by each other, the voting power could be  
calculated based on a one-node, one-vote basis. Once a transaction is validated by more than two-thirds of the nodes, the  
network would have reached consensus and the transaction would be placed into the shared ledger.

In any permissionless DLT network, anyone can run a node that participates in consensus, and it can be easy and virtually  
cost-free to set up virtual nodes. As a result, this one-node, one-vote approach leaves the network vulnerable to attackers  
who create such virtual nodes (known as “sock puppets”) at little to no cost. In this scenario, an attacker could create a horde  
of sock puppets to increase their voting power and surpass that one-third attack threshold (known as a “Sybil attack”).

To protect against Sybil attacks, the Hedera network will calculate a node’s voting power over consensus on a one-hbar, one-  
vote basis. After a node submits a transaction to the network, the transaction gets communicated to random nodes, which  
validate the transaction’s authenticity. Each node’s vote will be weighted by the number of hbars that are staked (or proxy-  
staked) to it, and consensus on a transaction will be reached once the transaction is validated by nodes representing more  
than two-thirds of the total supply of coins.

This coin-weighted system will prevent Sybil attacks, because the creation of additional nodes by an attacker would have no  
effect on the attacker’s stake of hbars, and thus the attacker’s voting power over consensus.

A bad actor would be able to disrupt consensus only by amassing and staking one-third of the total coin supply. In addition,  
because consensus will be determined by the number of staked hbars, not the number of nodes, it does not matter if a node  
goes on or offline while consensus is being calculated.

```
The platform will reach consensus on a transaction once the transaction is validated by nodes holding >2/3 of the coins
SCENARIO: Assume 7 nodes and 21 total coins
```

```
EXAMPLE A
```

- Coins distributed equally to each node (3 coins/node)
- Consensus after transaction validated by 5 nodes  
    (5x3=15, 15/21 coins = 71.4% > 66.6%)

```
EXAMPLE B
```

- Coins distributed unequally across nodes
- Consensus after transaction validated by nodes  
    holding stake of 14 coins (14/20 coins = 70% > 66.6%)

```
3+3+3+3+3=
15/21=71.4%
```

```
5+4+5=
14/20=70%
```

```
3 coins
```

```
3 coins
```

```
3 coins
```

```
3 coins
```

```
3 coins
```

```
3 coins
```

```
3 coins
```

```
5 coins
```

```
1 coin
```

```
1 coin
```

```
5 coins
```

```
2 coins
```

```
4 coins
```

```
2 coins
```

**STAKING AND PROXY-STAKING**

As Hedera’s coin-weighted consensus algorithm will require that a transaction be validated by nodes representing more  
than two-thirds of the total hbars, it will be important to ensure that well over two-thirds of the total hbars are actually  
staked to nodes. Yet while everyone who wishes to use the Hedera network will need hbars to pay for transactions on the  
network, most users are not likely to be interested in running a node.

“Proxy-staking” will allow hbar owners who do not run nodes to still stake those coins and be compensated for contributing  
to consensus by proxy-staking their hbars to a node. **⁶** Hbars proxy-staked to a node are considered part of that node’s  
stake (i.e., voting power) when validating transactions.

Node reward payments will be paid to nodes in proportion to the total amount of hbars staked (including proxy-staked  
hbars) and will be split between the node and the owner of the hbars being proxy-staked. The compensation for proxy-  
staking is meant only to encourage users (or the builders of their wallet software) to make the very small effort to choose  
a reliable node to which to proxy-stake. Users who proxy-stake their hbars will receive proxy-staking payments, but the  
amount of those payments will be de minimis.

Proxy-staked hbars remain under the control of their owner; the node to which they are proxy-staked cannot spend them.  
The owner will also be able to turn off or redirect the proxy-staking to another node or spend the hbars at any time.

```
*Hedera Treasury staked coins
```

```
PROXY STAKING
(held by Hedera Hashgraph, LLC)
```

##### User with hbars

##### Hedera Treasury

**6** Proxy-staking by network users is not yet an available feature of the network and is expected to be added in a later phase of the network’s development.

## Treasury Management & Distribution Schedule

_NOTE: This section describes the planned hbar allocation and release schedules. The release schedule  
described below may vary in the future due to unforeseen business or regulatory changes, and Hedera  
assumes no liability whatsoever for any variations therefrom._

On August 24, 2018, Hedera launched the Hedera network and created the fixed supply of 50 billion hbars held in the  
Hedera Treasury account.

Well before the network launched, Hedera developed a plan for hbar distribution to ensure the network could grow in a  
stable and secure manner. This plan was informed by key considerations of:

- Regulatory compliance
- Network security
- Decentralization
- Reliance on market forces for pricing (rather than centralized decision-making)

Hedera’s strategy behind this schedule is to release hbars from Treasury such that the growth of circulating supply is  
commensurate with the adoption and use of the Hedera network. Hedera’s strategy regarding the number of hbars in  
circulation may change depending on several factors, including (but not limited to) accelerated or diminished demand  
for services on the network, network security considerations, efforts to provide incentives or support to developers and  
others who will encourage use of the network, and as may be needed based on regulatory considerations.

**HEDERA TREASURY MANAGEMENT**

The Hedera Council is ultimately responsible for hbar distribution and circulation. Hedera has certain contractual  
obligations to distribute hbars, some of which predate the formation of the multi-member Hedera Council (e.g., SAFTs;  
agreements to pay advisors and certain vendors in hbar; compensation agreements with employees). However, hbars  
may not be transferred out of the Hedera Treasury account and new types of allocations may not be made without the  
approval of a majority of Council members or, if delegated by the Council, Hedera’s Board of Managers.

**HBAR ALLOCATIONS & DISTRIBUTIONS**

When the Hedera network opened access to the public, approximately 46% of the network’s 50 billion hbars had been  
allocated, with the remaining 54% in the Hedera Treasury. The allocated hbars included those to be distributed over  
time to SAFT investors, early management, employees, advisors, vendors pursuant to contractual commitments as well  
as hbars earmarked for future employees, community earn programs, and programs to incentivize network use through  
hbar grants to enterprises and developers.

Hedera provides monthly reports on hbar distributions, which are available at:  
https://help.hedera.com/hc/en-us/articles/ 360002789198

**04.**

```
16.30%8,138,847,866 ℏ
RCUs
```

#### 50,000,000,

```
TOTAL (Non-Inflationary)
```

```
54.91%27,454,810,977 ℏ
HEDERA TREASURY
```

```
14.50%7,270,833,557 ℏ
INVESTORS (SAFT)
5.00%2,500,000,000 ℏ
SWIRLDS, INC
2.90%1,450,000,000 ℏ
MANAGEMENT (SAFT)
2.02%1,010,714,000 ℏ
INVESTORS (SWIRLDS)
2.67%1,333,333,333 ℏ
2020 COIN PURCHASE AGREEMENT
```

```
1.20%600,000,000 ℏ
ECOSYSTEM RESERVE
0.50%241,460,267 ℏ
DEVELOPER COMMUNITY FUNDS
```

The current allocation of hbars is set forth in Figure 1 below. Please note that this allocation encompasses  
hbars that have been distributed and those yet to be distributed. Coins that have already been distributed may  
subsequently have been transferred to other parties, so the figures do not necessarily reflect current ownership.  
In addition, Figure 1 is based on current obligations and expectations, which may be subject to change.

Hedera’s estimated hbar release schedule through 2025 is set forth in Table 1 below. The annual distributions by  
category in Table 1 reflect estimated distributions under current contractual obligations and expectations. It does  
not include the quarterly “bonus” allocations of hbars to be distributed to SAFT holders who accepted the SAFT  
exchange offer described below. The distribution schedule will change based on, among other things, the number of  
“bonus” hbars distributed in connection with the SAFT exchange offer, attrition, and market conditions. In addition,  
Hedera expects to distribute additional coins from Treasury over time to support the development of the network  
ecosystem; to make coin grants to employees, contractors, and vendors; and to sell coins to cover operating costs.

```
HEDERA COIN DISTRIBUTION SCHEDULE (ESTIMATED THROUGH 2025)
```

(^) Open AccessAs of^2019202020212022202320242025 Total through 2025  
Total % of Coins Released 1% 4% 13% 18% 23% 27% 32% 34%  
Total Aggregate Distributions 372,540,769 1,934,179,7006,375,871,070 8,868,557,50511,393,645,67513,686,935,54015,805,818,09017,033,014,  
Total Incremental Distributions 372,540,769 1,561,638,931 4,441,691,370 2,492,686,435 2,525,088,170 2,293,289,865 2,118,882,550 1,227,196,  
Incremental distribution by category, current obligations *****  
Founders _(SAFT + RCUs)_ (^) 9,643,334 68,521,250 910,528,333 251,583,750 - 678,481,667 1,885,445,000 1,156,963,333 4,961,166,  
2017 Executives _(SAFT + RCUs)_ (^) 8,866,667 62,800,000 886,850,000 230,512,500 110,250,000 172,804,167 187,850,000 70,233,333 1,730,166,  
SAFT 1 + 1N _(excl. Founders, 2017 executives)_ : 30,412,857 216,691,605 746,538,334 744,352,778 744,352,778 561,932,778 11,004,583 - 3,055,285,  
SAFT 2 + 2N 139,250,000 368,968,920 839,056,383 828,586,562 656,339,326 69,798,809 - - 2,902,000,  
SAFT 3A + 3AN 135,861,270 203,791,893 340,028,155 - - - - - 679,681,  
SAFT 3B + 3BN 48,506,641 - 39,860,896 39,860,896 39,860,896 39,860,896 34,582,966 - 242,533,  
RCUs _(excl. Founders, 2017 executives)_ : Employees & Contrators - 535,897,979 229,486,708 158,934,417 90,740,761 12,394,835 - - 1,027,454,  
RCUs: Advisors & Vendors - 104,967,284 240,842,561 72,055,532 29,555,565 13,972,224 - - 461,393,  
Swirlds ** _(est. revenue share over 46 months per the MLA)_ - - 208,500,000 166,800,000 166,800,000 97,900,000 - - 640,000,  
2020 Coin Purchase Agreements _(estimated)_ - - - - 687,188,844 646,144,489 - - 1,333,333,  
Held by Swirlds *******  
Swirlds _(one-time allocation per the MLA)_ (^) 2,500,000,000 2,500,000,  
Retained by Swirlds _(future dividends to Swirlds investors; excl. Founders)_ : (^) 1,010,714,000 1,010,714,  
Other Budgeted Allocations ********  
Developer, Community & Ecosystem Incentives 6,700,000 7,300,000 1.2 billion coins expected to be distributed starting in 2020 1,241,460,  
RCUs: Reserve for future grants - - 1.8 billion coins expected to be distributed starting in 2020 1,800,000,

- ** The allocation amounts do not include the quarterly bonus allocations of hbars to SAFT 1N, 2N, 3AN, and 3BN.The actual number of hbars that Swirlds may receive under the MLA will vary depending on the price of hbars.  
    (^) *** The number represented here is an estimate only, based on the trailing 30-day median price of hbars as of March 15, 2020, and the actual number could be higher or lower.The one-time allocation to Swirlds and the hbars allocated to Swirlds investors (excluding the Founders) are held by Swirlds, have not been sold or distributed. Swirlds must provide a schedule, notice, and right of first  
    (^) **** The reserve of 1.8 billion coins for future RCU grants and most of the 1.2 billion coins allocated for developers, community and ecosystem incentives have not yet been granted or distributed, but have been earmarked for refusal to Hedera with respect to any such sales. The current coin distribution schedule provided by Swirlds to Hedera, which is for calendar year 2020, states that Swirlds has no coin sales planned for the entirety of that period.  
    such intended use.  
    **COIN  
    ALLOCATION**  
    Table 1: Hedera coin distribution schedule  
    Figure 1: Coin allocation

**SAFTS AND SAFT EXCHANGE OFFER**

Hedera raised capital to develop the Hedera network through the issuance of Simple Agreements for Future Tokens  
(“SAFTs”). Hedera issued three series of SAFTs, with the first SAFTs being offered in December 2017 and the final  
SAFT round closing in August 2018. In the aggregate, 17.45% of all hbars were sold via SAFTs.

When Hedera started distributing hbars to SAFT holders in September 2019, the distributions schedules for the SAFTs  
ranged from monthly distributions over 9 months for SAFT 3A, monthly distributions over 3 years for SAFT 2, quarterly  
distributions over 4 years for SAFT 1, and annual distributions over 4 years for SAFT 3B. Detailed information for each  
of the SAFTs can be viewed at https://help.hedera.com/hc/en-us/articles/36 0007219337.

In March 2020, all SAFT holders were given the option to participate in a SAFT exchange offer. The purpose of the offer  
was to help incentivize SAFT holders — many of whom are also developers and/or otherwise involved in the broader DLT  
ecosystem — to continue supporting further growth and development of the Hedera network, while further slowing the  
release of coins (which is contractually set) during this period of early adoption.

In exchange for extending the release schedule for their original allocation of coins, SAFT holders who accepted the  
offer will receive an additional bonus allocation of coins on a quarterly basis, beginning in Q4 of 2020, and continue until  
the cumulative value of those additional distributions equals the value of their original principal investment. Overall, 71%  
of SAFT holders accepted the exchange offer. Detailed data on the results of the SAFT exchange offer is provided in  
Table 2. The SAFT exchange offer documents are publicly available and can be viewed at https://help.hedera.com/hc/  
en-us/articles/360007276858. Distribution schedule changes due to acceptance of the SAFT exchange offer have been  
reflected in the estimated distribution schedule with respect to the original allocations of coins, but does not include the  
quarterly “bonus” allocations of coins to those who accepted the SAFT exchange offer as such amounts are difficult to  
predict and, at least initially, likely to be relatively small.

```
Number (#) Percentage (%) USD invested (~$) Percentage (%)
All SAFTs^1188 - $123,001,943 -
Accepted Offer 842 70.9% $75,295,076 61.2%
SAFT 1 Total 59 - $4,657,000 -
Accepted Offer 4 6.8% $77,000 1.7%
SAFT 2 Total 80 - $14,510,000 -
Accepted Offer 28 35.0% $3,025,000 20.8%
SAFT 3A Total 671 - $81,501,757 -
Accepted Offer 501 74.7% $51,442,296 63.1%
SAFT 3B Total 378 - $22,333,186 -
Accepted Offer 309 81.7% $20,750,780 92.9%
```

```
SAFT EXCHANGE OFFER ACCEPTANCE
```

```
Table 2: SAFT Exchange Offer acceptance
```

FOUNDERS & EARLY EXECUTIVES  
Hedera’s co-founders and early members of management also invested in SAFTs and, as part of their compensation,  
received coin grants. Accounting for coins they may receive through coin grants and the coins they will receive under their  
SAFTs, Dr. Baird and Mr. Harmon (together, the “Founders”) each have a right to just over 5% of the total coin supply. Dr.  
Baird and Mr. Harmon each have a coin grant of two billion hbars in total allocation (4% of the total supply of 50 billion  
hbars), each vesting over a six-year period.

None of the hbars that Hedera’s co-founders, Leemon Baird and Mance Harmon, are receiving as compensation (employee  
grants) were released before January 1, 2020. While Leemon and Mance also own SAFTs and will receive some hbars under  
their SAFTs, they are also further delaying the release of 76% of all of their hbars (whether from SAFTs or grants) until  
after August 2023 (i.e., after the fifth anniversary of network launch).

For both coins received under their coin grants and coins received under their SAFTs, DMr. Baird and Mr. Harmon will  
define a reasonable selling plan, which will be disclosed publicly at least 30 days before selling any of their coins. The selling  
plan will be designed to avoid flooding the market or selling based on non-public information, and to comport with all appli-  
cable laws and regulations.

Other senior executives who joined Hedera prior to March 2018 will receive an aggregate of 3.5% of the total coin supply  
through their SAFTs and coin grants. The senior executive employees who remain on staff have also agreed that none of  
the hbars they receive through employee grants were to be released before January 1, 2020, and that a substantial portion  
of their total hbars will be further delayed until October 2023.

EMPLOYEES & SERVICE PROVIDERS  
Hedera has adopted a coin plan through which it can compensate employees, contractors, advisors, vendors who provide  
services to Hedera, and other service providers using hbars. At present, all grants that have been made under the plan  
have been in the form of restricted coin units (“RCUs”), whereby individuals vest into a right to receive a number of hbars  
over a vesting will generally receive those hbars on or after the applicable vesting date.

Hedera has created a reserve of 8.1 billion hbars for the coin plan that governs the RCUs. Out of that RCU reserve,  
Hedera has granted RCU awards ccovering 6.5 billion hbars.

RCU grants to employees and contractors typically follow a four-year vesting schedule with a one-year cliff and then  
monthly thereafter (i.e., no portion of the RCU award vests unless the individual continues to provide services to Hedera  
for one year, at which point 25% of the RCU award vests and then the RCU award vests in equal monthly installments  
thereafter). With limited exceptions, if an employee or contractor departs before the end of the vesting period,  
the unvested portion of the grant reverts to Hedera while the individual retains the right to receive any vested but  
undistributed hbars. Hedera plans to continue providing RCU grants, including retention grants to employees, as part  
of its overall compensation. As of June 2020, RCU awards covering 1 billion coins have been granted to employees and  
contractors (excluding the co-founders and early executives referenced in the prior section.

The structure of RCU grants to advisors and vendors vary depending on the terms of the particular contract. As of June  
2020, RCU awards covering 461 million coins have been granted to advisors and vendors who provide services to Hedera.

```
SWIRLDS
Swirlds, which owns patents on the hashgraph technology, founded Hedera in order to create and launch a distributed
general-purpose public ledger based on the hashgraph technology. Towards that end, Swirlds has granted to Hedera an
exclusive non-transferable, perpetual right and license in and to the hashgraph technology for the limited and sole purpose
of making the Hedera network a general-purpose public ledger available to entities or individuals to use as developers,
users, testers, and node operators.
```

```
Under the license agreement between Hedera and Swirlds, a portion of the license fees are paid to Swirlds in hbars. Under
those terms, Hedera paid Swirlds a one-time allocation of 5% of the total supply of coins (2.5 billion hbars) and will make
ongoing monthly license fee payments in hbars equal to 10% of Hedera’s revenue, with a monthly minimum of $625,
worth of hbars (at fair market value) if paid in coins.^7 Because distributions of coins are subject to Council approval and
regulatory considerations, the parties remain in discussions about effectuating the minimum payments. Hedera currently
estimates that it will pay 640 million coins to Swirlds over 46 months in respect of the monthly license fee; the actual
number will be higher or lower, depending on the market price of hbars.
```

```
Independent of the license agreement, an additional 1 billion coins were allocated to Swirlds investors (excluding the
Hedera founders), who agreed to have Swirlds commit its resources and personnel almost entirely to the development
of the Hedera network during the period between Hedera’s founding and when the network was opened for public use in
September 2019.
```

```
None of the coins held by Swirlds for its own account or allocated for Swirlds investors have been sold or distributed, and
Swirlds is required to provide Hedera with a non-binding schedule that sets forth its expected plan for the sale of coins
over the subsequent twelve months and at least 24-hour notice prior to any such sale or distribution, and Hedera has a
right of first refusal at fair market price on any such sale. The current coin distribution schedule provided by Swirlds to
Hedera, which is for calendar year 2020, states that Swirlds has no coin sales planned for the entirety of that period.
```

```
DEVELOPER COMMUNITY FUNDS AND AND ECOSYSTEM RESERVE
Hedera has allocated 1.24 billion coins for programs that provide hbars to incentivize adoption and use of the Hedera
network, such as through the Hedera Heroes and Hedera Boost programs. So far, most of these 1.24 billion coins have not
yet been granted or distributed, but there may be significant allocations of this reserved number to important commercial
partners at any time.
```

```
Hedera may, through other initiatives and/or agreements, provide large amounts of hbars to enterprises, developers and
other third parties that are able to drive network growth, development, and decentralization. Hedera also may pay some
developers for services (e.g. tools, data analytics, advertising) and those payments may be in hbars, some or all of which
those developers can then use to pay for API calls or other goods and services on the Hedera network. All such programs
and distributions are subject to Council review and approval.
```

```
2020 COIN PURCHASE AGREEMENTS
Hedera is raising additional funds to support ongoing operations by selling hbars to a small number of institutional
purchasers, with coins to be delivered after a multi-year lockup period consistent with Hedera’s previously published coin
release schedule.
```

```
Under the agreed-upon terms of these sales, purchasers will pay $0.015 per hbar, will not receive any of those hbars for the
first two years, and then will receive delivery of the hbars in 12 equal monthly installments beginning two years from the
close of the sale (i.e., from month 25 to month 36 following closing).
```

```
The hbars that will ultimately be distributed to the counterparties under these agreements are hbars that otherwise could
have been release or sold by Hedera from the Treasury account during the next 2-3 years. Hedera expects to raise up to
approximately $20 million in these sales, which would account for 1,333,333,333 hbars. Table 1: Hedera coin distribution
schedule on page 15 includes the estimated release of these coins.
```

**7**^ For more on the terms of the license agreement, go to: https://help.hedera.com/hc/en-us/articles/ 360006895498

**HBAR RELEASE SCHEDULE AS PART OF THE SECURE PATH TO DECENTRALIZATION**  
Hedera believes there are four key requirements that provide a secure pathway to broad and continued  
decentralization:

1. Decentralized governance
2. Network utility
3. Permissionless nodes
4. Coin distribution

DECENTRALIZED GOVERNANCE  
Hedera achieves decentralized governance of the network through the Hedera Council, a rotating set of leading  
global enterprises from across industries and geographies. Governing Council members do not receive any economic  
interests in Hedera and, with the exception of Swirlds, they are term-limited. In these ways, the Governing Council is  
structured to provide wise, decentralized, transparent, and stable governance on behalf of the long-term interests of  
the network. For more information, visit https://www.hedera.com/council.

NETWORK UTILITY  
A successful public DLT network will provide value to its users through the applications deployed on it. The Hedera  
network’s core services provide developers and enterprises with powerful tools to create decentralized applications.  
Hedera currently has dozens of applications operating on the network aAs of March 14, 2020, the Hedera network  
is processing more than 750,000 transactions per day, generated by over two dozen applications running on the  
network and exchanges transacting hbar.

PERMISSIONLESS NODES  
“Permissioned” networks are those in which a person or entity that wishes to operate a node must have permission  
from the network’s owner (in Hedera’s case, the Hedera Council). In contrast, “permissionless” networks allow  
anyone to run a node on the network. A public DLT network (i.e., one that anyone can use) can be permissioned and/  
or permissionless. Hedera’s path to decentralization starts with a handful of permissioned nodes hosted by Council  
members, which over time will grow in number as the Council adds new members. In the future, Hedera expects to  
allow other entities and persons to be able to host nodes and, eventually, anyone would be able to host a node.

COIN DISTRIBUTION  
To ensure the Hedera network is secure under a permissionless model, the network’s coins must be widely distributed.  
Coins represent the “stake” of voting power in Hedera’s proof-of-stake consensus model – more coins equal more  
voting power over consensus. Thus, to ensure the security of the network, hbars need to be widely distributed so no  
attacker or group of attackers can amass control over one-third of the coins.

Hedera aims to combine a “path to permissionless” with a “path to widespread coin distribution” to keep the network  
secure while working to achieve greater decentralization.

First, until coins are sufficiently distributed, Hedera will remain a permissioned network. For the security of the  
network, the network will remain permissioned until the total value of all the circulating coins is high enough to be too  
expensive for a malicious user (or group of users) to buy a third of them to conduct an attack. When proxy-staking is  
introduced, there will also be a cap on how many hbars can be proxy-staked to a single node.

Second, Hedera has a slow and measured release schedule such that no more than 34% of all hbars are expected to be  
released until 2025. This slow release schedule is intended to provide for the stable and orderly growth of the network  
so that it can reach scale without sacrificing the safety necessary for a truly useful and widespread network that  
realizes the promise of building a trusted, empowering and secure online world. It is also tailored to match projected  
user needs to discourage excessive speculation in the coins. In addition, by publicly communicating the expected  
release schedule and requiring any material changes to be implemented through the vote and signature of a diverse  
set of Governing Council members, Hedera provides transparency and predictability about the total circulating supply  
of coins to further dampen speculation, minimize information asymmetry, and protect against market manipulation.

% TOTAL COINS RELEASED: **4** % **13** % **18** %^23 %^27 % **32** % **34** %

```
50,000,000,
(100%)
```

```
3.6% INITIAL
RELEASE
```

```
YEAR
Network Launch AUGUST 24, 2018 2019
```

```
Coin release Coin sale
```

```
% of hbars released irst week of open access
% of hbars released to the market by end of each year
```

```
YEAR
2020
```

```
YEAR
2021
```

```
YEAR
2022
```

```
YEAR
2023
```

```
YEAR
2024
```

```
YEAR
2025
```

```
6-YEAR HBAR RELEASE SCHEDULE
```

© 2020 Hedera Hashgraph, LLC. All rights reserved.  
The Hedera Hashgraph logo is a trademark of Hedera Hashgraph, LLC. All other company  
and product names may be trademarks of the respective companies with which they are associated.