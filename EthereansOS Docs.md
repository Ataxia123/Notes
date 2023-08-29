
# Factories Learn

![](https://925221316-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FwLDwr7X7O7KLz7NMgSCM%2Fuploads%2FthLCP6StIB85lMUw6nyW%2Fimage.png?alt=media&token=03a007ec-a2b0-410a-83a0-362b7f6a73b5)

### INTRO

**​**

A Factory is a smart contract acting as a repository of a model contract that others can clone and implement for their own particular use-case. A cloned contract can be initialized with custom parameters and extended with a custom Extension contract for a variety of purposes, guaranteeing that no one can modify its core.

Development of any application is made much faster and safer following this approach. Devs can focus on developing code on top of the cloned contract as needed, without having to think about developing the core or to write and redeploy it from scratch.

The entire EthereansOS ecosystem is built following the Factory approach.

### Why use Factories ?

Factories allow devs to easily clone specific smart contracts/services without the need to write a line of code. Cloning a contract that has already been developed, tested and used by many users is safer than re-deploying it from scratch.

This is a strong revolution compared to the current approach of coding that is based on taking a standard (e.g. the ERC20) as a starting point and modifying it to add/remove code or functionality, not ensuring that bugs or malicious operations are not present in the contracts, often resulting in users losing money. This does not even allow for a common codebase with shared standards and the evolution of the technology is not pushed forward as developers create code that is difficult for others to integrate.

The Factory approach, instead, points to the evolution of the entire development ecosystem following the principles of security, ease of code implementation and the creation of a constantly updated shared codebase, making development much less complex.

![](https://925221316-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FwLDwr7X7O7KLz7NMgSCM%2Fuploads%2FKybi1QYoOiswInZHT6lJ%2FTHE-NEW-FACTORY-APPROACH.png?alt=media&token=cadd27e2-66c2-4a8d-a869-f8d16bb068a8)

### Customization

Using a Factory-based approach provides a high level of customization in a secure environment. Developers can extend the code of a contract cloned by a Factory, using an Extension smart contract. The Extension is linked to the cloned contract extending its on-top functionalities and the possibilities of interaction and external integration. Consequently, you have security because the contract core is cloned from a model but you can hook an Extension on top implementing custom logic according to your project needs.

Let's take as an example a Factory that clones Farming contracts: The farming contract is the model contract and an Extension on top allows you to interact with it in a customized way. An on-chain Organization needs a custom Extension that transfers funds from the Treasury Manager in the manner provided by the operation of the Organization itself, while a DAO needs an extension that allows funds to be sent to the contract according to its specific operating logic and so on. The result is a secure cloned contract, extendable and integrable through Extensions.

The result is a secure cloned contract, extendable and integrable through Extensions.

![](https://925221316-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FwLDwr7X7O7KLz7NMgSCM%2Fuploads%2FspM3P6U6gfKvIYnzfbFz%2Fimage.png?alt=media&token=aed09f6a-269e-4181-99ab-d665a100bc6f)

### What is the FoF?

The Factory-of-Factories (FoF) is a Factory deployer and aggregator and it represents the heart of the Factory-based approach.

The FoF allows: Every developer to deploy one or more Factories at the same time or at a later date Discoverability: reconstruct all existing Factories that are always saved on-chain including the reference address that deployed them Versioning: deploy a new version of a Factory having the old one always available to be used by users at any time Metadata: each Factory has its own set of metadata that FoF allows to easily reconstruct Modularity: Factories deployed by FoF represent a shared codebase composed for many different uses. You can create your own project by cloning and implementing contracts from different Factories Extendibility: each contract cloned from different Factories can be extended using Extension smart contracts so that they perfectly fit the needs of your project

### Implement a real Business model in your Factories

Devs can implement a real business model in their Factories and in the underlying model contracts, earning fees every time their contracts are cloned and/or used.

Only the Factories deployed through the Factory-of-Factories (FoF) can implement a real fee-based business model.

The Factory maker can choose from two possible fee-based business models:

- Creation fee. This model allows the Factory maker to implement a fee for cloning the model contract, involving the burn or transfer of a certain amount of tokens.
    

Imagine a Factory, the model contracts of which are microservices that Organizations can easily clone and implement. Let’s say that the Factory maker codes the model with a creation fee, so that every time a user clones the contract he must pay/burn a fixed token amount.

- Usage fee. This model allows the Factory maker to implement a fee for the use of all clones of the Factory’s model contract. The usage fee can be static (a fixed amount of a specific token that users must burn or transfer using the cloned contracts), or variable (a percentage of the value a user transacts).
    

Imagine a Factory, the model contract of which is a Farming contract any developer can clone and implement their applications with to let users farm. Let’s say that the Factory maker codes the model with a withdrawal fee, so that every time a user withdraws liquidity from their farming position, they must pay/burn a fixed token amount (static fee) or the Factory maker receives 2% of the withdrawn tokens or the (variable fee).

[

 