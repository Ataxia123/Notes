---
id: "se-os"
aliases:
  - "Scaffold Ethereans Farming front end "
tags: []
---
[[project-directory]]
# Scaffold Ethereans Farming front end 

**Project Goal**: To create a forkable front end using scaffold for Ethereans farming positions

 TODO: Currently porting build to latest scaffold version

 
//TODO: 0) get LP token information [done]
//           -- TOken address + user balance <---- 
//           -- display user balannce
//           -- functions:
//           handleAMmountChange{
//           -- get price of ether
//           -- determine price of token using pool information 
//           -- change ammound based on price
//           }
//            handleApprove{
//            check approval status
//            run approvals for missing tokens
//            }
<mark>2023-07-14 12:19
</mark>
- we're doing something 🔜
-
Issues:
  The return type for the position query using farming contract are wrong. Need to fix into 2 arrays or something

Apparently I entirely broke wagmi because of stuff

use scaffold for listener and wagmi for everything else
<mark>done:</mark>
fetch main token address && eth balance

POSITION MANAGER STRUCTURE

1)Get position ID
2) Query the Slot0
3) Get user balances
4)Get user positions
5)get user position??



UNISWAP SDK work 
- refs:
- [[1689387226-unniswapv3|unniswapV3]] [[javascript arrow fxs]]
-> do query
-> store price
-> calculate balance
