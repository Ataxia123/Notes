---
id: se-os
aliases:
  - "Scaffold Ethereans Farming front end "
tags:
  - Project
cssclass: cornell-left cornell-border
---
[[project-directory]]
# Scaffold Ethereans Farming front end 
[[]]
>[!cue] Project Goal: To create a forkable front end using scaffold for Ethereans farming positions
>TODO: Currently porting build to latest scaffold version

[[SeOsDevLog]]





<mark>2023-07-14 12:19
</mark>
- we're doing something 🔜
-
>[!cue] **Issues:**
>The return type for the position query using farming contract are wrong. Need to fix into 2 arrays or something

>[!cue] ***POSITION MANAGER STRUCTURE***

1)Get position ID
2) Query the Slot0
3) Get user balances
4)Get user positions
5)get user position??


### UNISWAP SDK work 
--------------------------
2023-07-27 07:48
-> Test liquidity addLiquidity
-> Test Withdraw liquidity
-> Implemente CollectFees


----------------------------
2023-07-26 11:43
-> Current status:
Improve the positioId stuff...
Implementing withdraw function

the math changes were reverted :(



----------------------------
- refs:
- [[1689387226-unniswapv3|unniswapV3]] [[javascript arrow fxs]]
-> do query
-> store price
-> calculate balance

[[2023-07-17|July 17, 2023]]

-> Created array for token data
[[At0x-Scratchpad|learning Topics]]
- learn something about js arrays

2023-07-19 11:40
-> approval fx now works
-> Started working on addLiquidity function
TODO: change the abi from min_stake_whatever to the other one

learn about [[bigInt]]

## Currently errroring:

client.js:1 ContractFunctionExecutionError: The contract function "openPosition" reverted with the following reason:
Invalid setup

Contract Call:
  address:   0x679780Ea3133C388E3c7efeb22e98a68Ccf99aFf
  function:  openPosition((uint256 setupIndex, uint256 amount0, uint256 amount1, address positionOwner, uint256 amount0Min, uint256 amount1Min))
  args:                  ({"setupIndex":"6","amount0":"1000000000000000000","amount1":"844576791479338","positionOwner":"0x69eF61AFc3AA356e1ac97347119d75cBdAbEF534","amount0Min":"1000000000000000000","amount1Min":"1203115123179889"})
  sender:    0x69eF61AFc3AA356e1ac97347119d75cBdAbEF534
s
