---
id: "1690603664-soliditydev"
aliases:
  - "solidityDev"
tags: []
---
[Solidity by Example](https://solidity-by-example.org/)
[[1690604719-soliditybyexamplenotes|SolidityByExampleNotes]]

[SolidityVault](https://github.com/fubuloubu/ERC4626/blob/main/contracts/SolidityVault.sol)
Require in solidity [Blog](https://www.ajaypalcheema.com/require-in-solidity/)
[StackOverflow](https://ethereum.stackexchange.com/questions/88287/how-to-implement-owner-check-in-solidity)
[EthStackExchange](https://ethereum.stackexchange.com/questions/52960/do-modifiers-work-in-interfaces)
👋

'''solidity 
abstract contract A {
    modifier adminOnly {
    /// checks admin
    _;
    }
    function f() external adminOnly returns (uint){
      return __f__(); 
    }
    function __f__() virtual internal returns (uint);
}

contract B is A {
     function __f__() internal override returns (uint) {
     // whatever you do here has modifier applied before
     }
}
'''

# solidityDev

SOLIDITY tips
1️⃣ Use "type(uint256).max" instead of "uint256(-1)"
2️⃣ Surround code with {} to avoid "stack too deep"
3️⃣ Skip tuple vars with commas: "uint a, , ,"
4️⃣ Swap vars in one line: "(a,b)=(b,a)"
5️⃣ Use "assert" and get built-in formal verification with SMTChecker

-----------------------------------------------

// Daniel Luca tips (CleanUnicorn.eth)
1️⃣  You can format numbers in Solidity using underscores.
i.e.,
1_000 is a thousand
1_0_0_0 is a thousand
1_000e0_3 is a million

Python spec https://www.python.org/dev/peps/pep-0515/

------------------------------
Contribute tips here: https://github.com/juanfranblanco/vscode-solidity/blob/master/snippets/solidity.json#L197-L201 
Escape the text using: https://www.freeformatter.com/json-escape.html
------------------------------
