---
slug: WAAS
title: WalletAsAServer
authors:
  name: At0x
  title: chief nerd
tags: [nerddao, hacks, ethereum]
---

# Rethinking Revenue Models: Wallet as a Service on decentralized social graphs.

## Introduction

A lot of innovation in crypto comes from the discorvery of novel revenue models and funding mechanisms. One only needs to look at the ICO craze and the NFT summer as examples of novel revenue models that brought a slew of new use cases to the ecosystem. Each of these mechanisms leveraged a property of decentralized networks to create never before seen capital transfers. However in time they also highlighted their weaknesses as market participants realized once again that there are no silver bullets.

## Revenue

Currently the entire crypto space is grappling with the problem of long term revenue streams. Both ICOs and NFT drops struggle after the main raise to keep revenue as volumes arent guaranteed in perpetuity and the market attention moves elsewhere. In the same vein, projects struggle to find mechanisms to gracefully capture value for their token or treasury without creating friction (and fork potential) for the entire protocol.

## Lens-Power: Decentralized graphs as content distribution platforms.

Lens Protocol is NOT a social media app. It is a decentralized social graph. A Social Graph is a model representing relationships in a social network. In other words, Lens is the backend for all the web3 apps that want to use a social component.

Web 2.0 companies use social graphs to personalize content, exploit network effects, and analyze user behavior for insights. these companies, like Twitter, Facebook, TikTok, monetize the social graph by using your data and relationships to serve targeted advertisements and curated content, thereby influencing what you see and interact with, and often generating significant revenue in the process.

Decentralizing the social graph means users own and control their own data, enhancing privacy and enabling cross-platform interactions. This also means that users can monetize their own content however they see fit. Furthermore, it means that individual developers can create experiences that are distributed on the Lens graph thus opening the doors for a whole new class of software.

## The Current State of the Lens Garden: A Web2 Remake.

As far as I can tell every product developed on lens so far has taken a web2 approach to the implementation of the social graph. This means that the available products right now are more or less recreating their Web2 counterparts such as:

- Twitter - https://lenster.xyz/
- Instagram - https://lensta.xyz/
- Youtube - https://lenstube.xyz/
- Reddit - https://diversehq.xyz/
- OpenSea (kek) - https://lensport.xyz/

Although this is a prefectly valid approach and these interfaces are very much needed, in my opinion they currently fail to fully capitalize on the best qualities of the lens protocol (Although they will be the most used interfaces for a long time).

## How to Wield the Lens Powr

Behind the features that we all are familiar with on a social network lens has an added two extra tools that changes the game entirely: Collect, and Referral Fee.

### Collect: Take The Power to Take.

With the collect module, the lens protocol gives the power to monetize the content to the content creator. In a nutshell, it allows posts to be purchased, much like an NFT mint, with predetermined conditions. Authors can make their content limited by time or edition size and they can split revenue among different participants, enabling trustless collaboration.

### ReferalFee: Take The Power to Give

The referal fee is probably the most underappreciated feature in the entire protocol at the moment, perhaps because it is not immediately apparent how it works. In a nutshell if Bob posts something with a referal fee, then Alice shares Bob's post to her feed, and Steve, who follows Alice, collects it then Alice gets paid a % of the revenue that Bob has set as the referallFee.

## The Smart Bot User.

One of the things that can be done using the lens protocol is to rethink the user as more than just a regular individual. If we abstract the Social Graph as a content distribution network. ( I post something, my followers see it, they share and their followers see it = content distributed ). A user can be seen as a node in this network and their followers are the list of nodes that "subscribe" to the user node.

![](https://hackmd.io/_uploads/H1ZhxtUvh.png)

In this regard. I believe that there is a new class of users: Smart Bot User that can leverage this new kind of network to provide serivces to other nodes and therefore turn into anchor points for the network.

What is a Smart Bot User? A Smart Bot User is a lens profile that is owned by a server or smart contract instead of an end user. This smart bot executes a predetermined logic that other users can call on however the developers see fit.

Users can rely on the smart bots to enhance their reach in the network. For example, by paying to get their posts shared or owning a group feed that can post to a greater number of nodes or post content to a curated feed that will reach their intended audience and enable the end user to monetize their own content. By adding collect modules that split revenue between users and smart bots and add a referal fee on top we can create a new business model enabled by decentralized social graphs. This is the basis for the curator economy. In it value can be extracted from content by distributing it widely on specialize dnetworks which distribute the value generated back to all participants.

## Putting it in Practice: SavePointGPT.

To illustrate these ideas I created a project called SavePointGPT. SPGPT is an application that will take a chatGPT unique share link, encrypt it and post it on Lens alongside with a comment (hopefully) describing its contents. This enables any user to monetize their chatGPT conversations in a new medium: Dialogues.

![](https://hackmd.io/_uploads/rJjWGcID3.png)

### The value of dialogue.

Arguably, the most powerful form of communication we have is dialogue. Not because it transmits information, but because it generates knowledge. For the first time in history we have this Aristotle like figure in LLMs that we can ask questions to and capture knowledge that we can share, just like Jimmy Neutron's chewable books dialogue chews knowledge into easily digestable bites that we can ingest.

Much like video cameras produce "moving pictures". ChatGPT conversations are "moving conversations". Users can reformulate questions and keep the thread going with the existing context in order to experience the thought process of the author as he conversed with the AI.

## How its Done:

![](https://hackmd.io/_uploads/HJ1lb3ID2.png)<br></br>
I'm using my trusty do-it-yourself web3 stack comprised of [scaffold-eth](https://buidlguidl.com/) as a NextJS/Typestcrypt framework and the Lens SDK to publish posts on lens.

The client and the server do input validation to make sure you're sharing the correct link format. Then it sends an encrypted post to the savePointGPT profile. using the LensSDK

Once the post is created a comment is automatically added to let everyone know what the hidden link is about. THe posts appear on ANY interfaced used by a user who follows this account. This makes SavePointGPT the best way to share and monetize your chatGPT dialogues.

<br></br>
![](https://hackmd.io/_uploads/Bk2GWhLv3.png)
<br></br>
The default split for every post sale is as follows:

- #### Collect
- **99%** goes to the original poster
- **1%** goes to save-point-gpt

---

- #### ReferalFee
- **10%** of the total sale is set as referalFee
  <br></br>
  ![](https://hackmd.io/_uploads/HJUQ-38P3.png)

Try it out!

Testnet link: https://savepoint-gpt.vercel.app/

## NERD RULE # 5123 HYPERSTURCTURES ONLY

In the NerdQuarters we are commited to open source development. WIth that in mind we have to design for open systems. Instead of having a proprietary secret sauce i'm making the entire code available on my [github](https://github.com/Ataxia123/NerdBrain). The output of the protocol is meant to serve as a building block: a unique identifier to a specific conversation with an AI. This could be used to create many things, such as online courses, , a dictionary, doctor prescriptions, escape room experiences, DnD adventures, interactive novels, school curriculums, etc. Aditionally I think that theres a need for many individual smart bots, each curating a thread of posts.

If you want to use this for your own ideas, let me know! I want to help.

-At0x

![](https://hackmd.io/_uploads/SkeimhIvh.png)

Github: https://github.com/allyu-xyz

Join the Nerds: https://y.at/%F0%9F%A4%93%E2%9C%89%EF%B8%8F%F0%9F%A4%93

![](https://squigsig-api.vercel.app/squigsig/image/6970?output_width=350&crop=true&col=white&alignment=right&logo_col=blue)
