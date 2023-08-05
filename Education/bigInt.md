---
id: "bigInt"
aliases:
  - "bigInt"
tags: []
---

# bigInt

[docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/BigInt)
[[1689816229-data-types|data types]]
```javascript

const previouslyMaxSafeInteger = 9007199254740991n;

const alsoHuge = BigInt(9007199254740991);
// 9007199254740991n

const hugeString = BigInt("9007199254740991");
// 9007199254740991n

const hugeHex = BigInt("0x1fffffffffffff");
// 9007199254740991n

const hugeOctal = BigInt("0o377777777777777777");
// 9007199254740991n

const hugeBin = BigInt(
  "0b11111111111111111111111111111111111111111111111111111",
);
// 9007199254740991n
```

```javascript
const max = 2n ** 64n - 1n;

function check64bit(number) { 
  (number > max) ?
    console.log('Number doesn\'t fit in unsigned 64-bit integer!') :
    console.log(BigInt.asUintN(64, number));
}

check64bit(2n ** 64n);
// Expected output: "Number doesn't fit in unsigned 64-bit integer!"

check64bit(2n ** 32n);
// Expected output: 4294967296n
```
