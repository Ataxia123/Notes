---
id: "FxPortal"
aliases:
  - "FxPortal"
tags: []
---

# FxPortal

[fx-portal](https://github.com/0xPolygon/fx-portal)


What is Fx bridge (fx-portal)?

What is Fx bridge (fx-portal)?
It is a powerful yet simple implementation Polygon state sync mechanism. Polygon PoS bridge is based on it. The code in the examples folder are examples of the usage of this methodology. You can use these examples to build your own implementations or own custom bridge.

In short, it's Meta bridge. This bridge allows any state-syncs without mapping.

### Some use-cases of Fx-portal
- ERC20 token tranfer from Ethereum to Matic-Chain without mapping request
- Lazy minting of ERC20 tokens on MaticChain
- State Transfer between Ethereum-Matic
- What about PoS portal?

PoS Portal is another bridge, but it works only for few ERC standards and requires mappings. It is more developer-friendly, allows customization without much headache.

While Fx-portal focuses on permissionless-ness and flexibility, a developer might have to write more code but more customizable than PoS Portal. It requires no mapping.

Can I build my bridge?

Yes. You can check docs here: https://wiki.polygon.technology/docs/develop/l1-l2-communication/ethereum-to-matic/ https://wiki.polygon.technology/docs/develop/l1-l2-communication/matic-to-ethereum/

What are FxChild and FxRoot?
FxChild (FxChild.sol) and FxRoot (FxRoot.sol) are main contracts on which mapping-less bridge works. It calls and passes data to user-defined methods on another chain without mapping.

Mumbai
