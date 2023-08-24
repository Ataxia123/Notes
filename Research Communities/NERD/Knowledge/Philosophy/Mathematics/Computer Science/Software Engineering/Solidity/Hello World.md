---
id: "Hello World"
aliases:
  - "Hello World"
tags: []
---

# Hello World

[Source](https://solidity-by-example.org/hello-world/)

Hello World
<mark>pragma specifies the compiler version of Solidity.</mark>

'''solidity
// SPDX-License-Identifier: MIT
// compiler version must be greater than or equal to 0.8.17 and less than 0.9.0
pragma solidity ^0.8.17;

contract HelloWorld {
    string public greet = "Hello World!";
}
'''

[first App](https://solidity-by-example.org/first-app/)
'''solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.17;

contract Counter {
    uint public count;

    // Function to get the current count
    function get() public view returns (uint) {
        return count;
    }

    // Function to increment count by 1
    function inc() public {
        count += 1;
    }

    // Function to decrement count by 1
    function dec() public {
        // This function will fail if count = 0
        count -= 1;
    }
}
'''
