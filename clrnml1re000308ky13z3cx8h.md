---
title: "Twitter Space Recap:  Spheron x Shardeum -  Solving the Scalability Trilema and Operating Community-Owned Decentralized Infrastructure"
seoTitle: "Twitter Space Recap:  Spheron x Shardeum"
seoDescription: "Learn about Shardeum, the decentralized platform that's scaling Ethereum to meet the needs of the growing Web3 ecosystem."
datePublished: Sun Jan 21 2024 15:00:24 GMT+0000 (Coordinated Universal Time)
cuid: clrnml1re000308ky13z3cx8h
slug: twitter-space-recap-spheron-x-shardeum-solving-the-scalability-trilema-and-operating-community-owned-decentralized-infrastructure
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1705846650800/3fdbe65a-d41d-48cb-8637-ee70bdc8f3d3.jpeg
tags: security, blockchain, scalability, web3, decentralization, spheron, shardeum

---

**Twitter Space(Available until 2/15/2024):**  [https://twitter.com/i/spaces/1mrxmyLLReLxy](https://twitter.com/i/spaces/1mrxmyLLReLxy)

**Moderator:**  [Chris Anatalio, Developer Advocate @ Spheron](https://twitter.com/CAnatalio)

**Guest:**  [Sandipan Kundu, Developer Relations Manager @ Shardeum](https://twitter.com/SandipanKundu42)

In this Twitter Space, we discussed [Shardeum's](https://shardeum.org/) approach to solving the scalability trilemma through dynamic state sharding, achieving linear scalability over time. The conversation covered the combined proof of stake and proof of quorum consensus, fast finality by processing at the transaction level, and the benefits for end-users and developers. We also discussed Shardeum’s guiding principles of openness, collaboration, and community-driven development.

### **Key points covered:**

* How Shardeum handles high throughput with parallel processing
    
* Its approach to decentralization
    
* Sharding at the network, transaction, and state level
    
* Advantages for validators
    
* Shardeum's Roadmap for 2024
    
* Compatibility with Ethereum tools like Solidity and Hardhat
    
* Ease of onboarding developers
    
* Using Spheron for simplified node deployment
    
* Using Spheron’s Telegram bot for deploying Shardeum nodes
    

### How Shardeum Uses Dynamic State Sharding to Achieve Linear Scalability Over Time

**Chris | Spheron**

So, I guess we're just going over a high-level overview of Shardeum. The main principle is you're dynamically state-sharded, right? So, you do parallel processing across shards, where each shard is essentially a node. And this allows you to achieve linear scalability, right? So, if you increase the number of nodes by 30%, that will theoretically increase throughput by 30%. Is that right?

**Sandipan | Shardeum**

Yeah, that's on the line. So, initially, based on the number of validators. Initially, that may not be linear, but as the network grows more and more, it translates to linear scalabilities like that. But initially, when, for example, there are 1400 validators, it doesn't necessarily mean. So, that initial threshold needs to be crossed to achieve that linear scalability. But once you get past that point, the linear scalability kicks in.

**Chris | Spheron**

I see. So there's like a certain critical mass in the network that you have to achieve to get that network effect where you get that linear scalability. Okay, that makes sense.

### How the Combined Proof of Stake and Proof of Quorum Consensus Operates

**Chris | Spheron**

So, you use a combined proof of stake and proof of quorum consensus. Could you briefly give us a high-level overview of how that works?

**Sandipan | Shardeum -  805630 to 909340 (in milliseconds)**

Yeah. So, proof of stake is implemented as it is in other networks. All the validators who are joining need to add a specific amount of stake to be considered part of the network. And also we can talk about it later. But the standby and active validator concept. But even to go to the standby list of validators, you must add that stake. That stake is supposed to act as an economic security, that your node will perform the actions as intended and won't do any malicious events. And if it does, and if it's not in a particular interval, if it's not performing as it's intended, that stake will start getting slashed. So that's the Proof of Stake part. The Proof of Quorum part is mainly on how the transactions are processed. In Shardeum's cases, Shardeum has an underlying protocol. Shardeum uses an underlying protocol called Shardis, which has been developing since 2017. Shardeum uses that protocol as a plugin, you can say, into the network, and that implements the proof of code in which multiple virtual consensus clients are formed in NS shard. And those votes vote on whether that transaction should pass or not. And then all the votes are collected from the nodes, which are voted on, and then it's calculated whether a majority of it agrees and then. If it agrees, that transaction is processed, and we move forward. So that's the proof of code in part.

### How Shardeum achieves Fast Finality by Processing at the Transaction Level instead of the Block Level, removing the need for Block Level Consensus

**Chris | Spheron**

Okay, cool. And processing happens at the transaction level versus the block level. Right. So that's, like, one of the reasons why you have such fast finality. Yeah. Okay.

**Sandipan | Shardeum**

When you're processing in multiple shards, and since each shard has not, the whole concept of shard, is that it's a part of the network, but it doesn't have the entire state of the network, of the entire blockchain. When that happens, then forming blocks is not efficient. So we do a first come, first serve-based transaction ordering so each transaction is timestamped to when it's submitted to the network. According to the timestamp, each of the transactions is processed linearly. So that gives a lot of advantages, especially for exchanges. We want that to happen because, in certain exchanges, you will see in other networks that exchanges ask for 256 block confirmation. After all, until there is enough block confirmation, you can't be really sure that a transaction has occurred because it can be reverted. That's what we call re-org. Multiple chains have reorgs. So, in the case of Shardeum, you can be sure that if a transaction has been submitted, finalized, and successful, it cannot be rolled back because there is no block to roll. So that's the advantage of it.

**Chris | Spheron**

Okay. Wow. And just like that, you solved the scalability trilemma. That's awesome. Let me see. Yeah. Another benefit is validators. They don't have to store the entire world state; they store the state of their shard. So, that lowers the bar for operating a validator. So that's awesome as well.

### Speaking about Shardeum’s Guiding Principles of Openness, Collaboration, and Community

**Chris | Spheron**

So, one thing I love about Shardeum is your guiding principles, right? You're very dedicated to the spirit of web3 being open, collaborative, and community-driven. Just reading through your docs, you try to keep everything transparent, docs, discussions. One of my favorite lines is when you call the community the CEO. Right. And we're on the same team against centralization, right? Yeah. I guess I'd like to hear, in your own words, your thoughts about the guiding principles of Shardeum.

**Sandipan | Shardeum**

Yeah, I think in this case, pretty much. I think the best example of community-oriented has been Ethereum, and Shardeum is trying to follow that path. It's an internally built protocol, but we are in the process of open-sourcing it, and we don't want in future a scenario in which the Shardeum team is just responsible for the protocol its upgrades, and its future features. We want to make it as open and collaborative as possible so the community can participate. Hopefully, multiple teams will be participating and committing to the Shardeum code base in the future. And so that's the future we envision, and we just don't want to keep it company-centric. And we are going very aggressive on open source, so that's something. And on the community part, I think we are one of the blockchains that has launched. We have launched and announced the project as we are building the project. Like many of those you would see in the market, the use cases are like other blockchains, for example, built on stealth and then just announced a testnet. And briefly, after this testnet, they have gone mainnet. But in our case, since our first ever Testnet, which has been liberty, liberty is no more. Even in our docs, it's so old, like it was, I think, 1.5 years ago. So, since our Liberty testnets, we have been building on public, and we have been getting constant feedback, and we are iterating on that. So we definitely wanted to keep it as open and community-centric as possible from the beginning, and we plan to do it even further. So Shadim, eventually, we have plans. Even in our white paper, you can read we have plans to transition to a day owned and governed by the community.

**Chris | Spheron**

That's super awesome. Many people talk about being community-centric, but yeah, you're walking the walk and embodying that philosophy. So that's awesome. Yeah, Spheron is super happy to be part of this community. We're super happy to be your partner.

### How Does Sharding Benefit End-Users and Developers from a Practical Perspective?

**Chris | Spheron**

But I guess the next topic I wanted to dive into was sharding. From a practical standpoint, like the benefits for end-users for developers, what use cases for developers stand to benefit the most from your sharding architecture?

**Sandipan | Shardeum**

Yeah. One of the biggest things everyone asks us since 2024 is why a new l one? Why an EVM l one? If you roll back the history and see how the other EVM networks have started, I think Ethereum has, like Ethereum, started the whole EVM thing. Then they came up with their solution, which was cutting edge in 2017 but could not scale up according to the demand in 2024 because that was not even envisioned while building Ethereum. Those are the things that Shardeum is trying to achieve, as we see from the past examples of where there are missing pieces and where there are hurdles and barriers. For example, in Ethereum, even if the entire Ethereum network grows over 500,000 nodes, it will still be able to process around 20 transactions. So, it's not dependent on how many participants there are in the network. And that's not a scalable design, but that was still cutting-edge, and it introduced a lot of things in the 2017/2016 era. So that's the part where it made an innovation, and we just want to take that innovation and move forward like we are EVM compatible in that sense. But how Shardeum and sharding work is instead of having the entire network go through and process all the transactions and has the consensus on the transactions, we divide the network into smaller chunks of groups of nodes; each called a shard. And each of those shards independently is capable of processing transactions. And when you divide that network into multiple shards, and each of the shards in itself sort of has the capability to process the transactions. You get parallel processing just by that, without even having to parallel process the EVM-level stuff. So even in the protocol level stuff, you can have that. But I think sharding has been a very new concept in computer science. It has been implemented, and it is very popular in databases. We just wanted to bring that concept into Web Three because I think at the end of the goal, the end goal of everyone is to have as many to reach, to make Web Three reach as many people as possible. So that's why we implemented that. And now that you have parallel processing, even though we are EVM-based, even though the network is processing the transaction according to the EVM rules, we are still getting parallel processing of transactions. And that's also leading to much more decentralization because of how the nodes share the data and how shards are formed; that's why we are dynamically state-sharded blockchain. Those are not fixed. Those can't be predicted. So, that adds a layer of economic security to the network. So these are some of the things in which Shardeum is pushing the boundary of what Ethereum started and coming to the part where people specifically, let's get to the part where developers can benefit. That is, you have a limit in block-level blockchains, which use the block-level thing. And in every fixed time, you can only produce one block. Theoretically, if you are producing other blocks, then as I mentioned, the re-org happens. But theoretically, the process is that you produce a block in a fixed interval of time, and everyone is competing for that space. In the case of Shardeum, since the network can grow and shrink according to the network demand, there is no competition to fix, to fit a lot of stuff into one place because the network adjusts according to that. So, that's where the developers can build applications requiring much more throughput. However, we cannot reach those levels because of the network constraints. So we want to see it. There is still a lot of research going on, and we are still working with a lot of dapps, which are trying to enhance their application based upon and utilizing sharding technology. But the main concept is that if a DAP wants to go through a high throughput and a fixed number of very constant streams of transactions, and they want to ensure that each transaction is processed linearly without having to compete for that block space, that's where they can get benefited by building on Shardeum. So that's one of the limitations we just removed straight away. And it's exciting to see how developers develop different solutions and build more sharded applications.

**Chris | Spheron**

Yeah, that's awesome. Yeah, I mean, if you look at any web app with a web-scale with hundreds of millions of users, it will have some kind of distributed database like MongoDB or Cassandra with a sharded architecture. The only difference is instead of all the nodes living in a proprietary database, the community owns all the nodes. Like you said, it's not a revolutionary concept, it is just the next evolution of it. Right? So that's super awesome.

### How Horizontal Auto-Scaling of Nodes Works in Shardeum

**Chris | Spheron**

So, if I could clarify one thing, you're talking about the horizontal auto-scaling of nodes. You have these nodes on standby. So when you get a spike in transaction traffic, will the network pull in some of those standby validators to pick up that load?

**Sandipan | Shardeum**

Yeah. So, it happens when a node joins the network. It gets to the standby nodes pool. So, we have two kinds of nodes in Shardeum. When you start joining the network, you get into the standby pool and, eventually, enter the active pool. And we have a period of cycles like every cycle is 60 seconds. In every cycle after the end of every cycle, the network checks the demand of how many transactions are coming in, and it then decides whether the current number of active nodes is sufficient. If they're not, then more nodes from the standby pool are brought into the reactive pool. And then, as the network is sharded, you get more shards formed, and then each of those shards can even process more transactions. Again. In the next cycle, the network will again check if this is enough. If not, it will continuously grow and bring in more validators from the standby pool until the standby pool. No standby pool is available, but because we are trying to make that again, we will also jump to the node point. That's why we focus on making running a validator simple and easy. Shardeum is one of those blockchains that is not limiting people to join in as a validator; instead, it benefits from having more validators. So, as long as there are always more standby nodes available, the network can theoretically grow as much as possible. So that's the whole standby and active validator concept.

### Limitations and Drawbacks of Ethereum’s Focus on L2s to Scale

**Chris | Spheron**

Okay, yeah, that's awesome. With Ethereum, when you add nodes to the network, it only adds security. As you said, they're going to be constrained at that transaction limit, conceded to that limit when they went to the roll-up-centric roadmap, and rely on L2s to scale. But there will always be that bottleneck, right, the one at the fundamental level.

**Sandipan | Shardeum**

And also, the whole scaling of using L2s is just making – we need unification. Ultimately, if you want to scale to the web2 kind of scale, like the web2 level scale, we need unification. Then, the liquidity disappears and gets divided whenever you divide the network into subparts, L2s and L3s. Then, the user gets divided. Then again, there are optimistic roll-ups in which there is a lock-in period when you transfer, and you need to wait for a fixed period of time to really ensure that your transfer is indeed successful. So many factors come in, but I think in general, the community gave up on the concept that an L1 can be scalable, and we are just trying to build on that because sharding was still in research in the early stage. There is a lot of research going on in sharding and blockchain. But when we can make this possible, that's the point where we will see that you don't need to divide the network into l two s and l three s. And with just the main chain, you can have the scalability. So that's the end goal for us.

### How Shardeum Compares to Other Sharded L1s

**Chris | Spheron**

Okay, yeah. That makes sense. So this one might be a little difficult, but what if I asked you to differentiate Shardeum from other sharded l ones, like Monad? What are the main differentiators from some of the other sharded L1s?

**Sandipan | Shardeum**

Yeah, I think I have very little information about the other sharded blockchains, but as far as I am aware, Monad is doing it on the EVM level and not on the protocol level. In the case of Shardeum, I can tell you that we are doing it on the protocol level, and it's on all three perspectives. It's network level, transaction level, and state level. So we are covering; there is no further state where you can share the network. And there are some networks. For example near also has in its roadmap as shard. But those are fixed shards, and they manually increment the shard. And they are like right now in the process of upgrading. So other blockchains are trying to do it, but we are trying to cover it from all three perspectives. As I said, the network level, then the transaction level, and the protocol level. So that's, I think, probably the differentiation. But I may need to read more about Monad to comment further on that. But yeah, that's what I'm aware of. Okay.

**Chris | Spheron**

Yeah, that makes sense. Yeah, I assumed it would be just implementation differences. But yeah, if you're at the protocol level, that has to be the theoretical maximum, right? For sharding.

### Looking forward to the Shardeum Roadmap for 2024

**Chris | Spheron**

Okay, I'd like to dig into something like looking forward to your roadmap. What are some of the most exciting things on your roadmap for 2024?

**Sandipan | Shardeum**

Yeah, so we're releasing the final stages of our testnet of Sphinx and then the end goal, and then there is the mainnet. So we are very close to Mainnet, and that's pretty much it. We just wanted to go to mainnet with as many features as possible. So, we have taken our time to build those before we launch to Mainnet. Because once you go mainnet, upgrading things becomes ten times more difficult. But yeah, that's pretty much the roadmap in our case. The internal team has tested shards as the network has already tested mid-level shards in which 5000 or 6000 nodes are active simultaneously. And they're extending that further to see how many nodes it can grow. So we are trying to reach, technically. Theoretically, it should automatically reach 10,000, 50,000, 1 million, we don't know. So we are trying to figure out that number. But that is already too far from what the market demands. So, at least for the initial few years, we are good, and we are going to continuously research that and create that extra layer of padding between what's needed and what's actually possible. But as long as the demand is similar to what we are seeing in the market and nothing crazy, like if tomorrow 5 billion people jump into Wesley, that will be a different case. But until that happens, I think we are pretty much equipped for a future level of growth.

**Chris | Spheron**

Okay. And I love that just being future-proof and thinking on a long time horizon that's awesome.

### How can dApp Developers get Started on Shardeum?

**Chris | Spheron**

So I guess just to switch gears a little, Dapp developers, let's say, Ethereum developers, want to get started building on Shardeum. Can they use their whole standard tool set like solidity, hard hat, foundry forge, is it just another deployment target?

**Sandipan | Shardeum**

Everything is just another deployment target because we use Ethereum JS for the processing. How Ethereum processes the sharding part is only on the protocol level, so it doesn't touch the EVM level stuff. The EVM-level stuff behaves just like on Ethereum or any other EVM-compatible chains. So if a developer already has something, a smart contract or a DAP running on another chain, they need to change their RPC and deploy on Shardeum, and they should be good.

**Chris | Spheron**

Okay, that's awesome. So you're basically like a drop-in replacement for Ethereum, but scalable. That's awesome. Okay, so I mean, what's the best way for developers to get board just the standard flow, get on Discord, go through the docs, go on the faucet, just start experimenting with different use cases, any resources you want to call out for a quick start or getting started on Shardeum.

**Sandipan | Shardeum**

Yeah, so definitely, the first point will be that you can join the Discord server, and then there are dedicated channels to ask your queries. And then the second point of contact specifically for developers will be the docs. Our docs are pretty much very streamlined and simple. It only mentions what's needed, and you get all the information you need to start building your dapps from the docs. And if you go to the Shardeum or GitHub, you will see a Shardeum DAP boilerplate. You can get started with that too to spin up a quick DAP NFT application, uniswap like Dex. And you can try experimenting. Those are already configured with the shuttle network. The contracts are already deployed, but you can deploy the contracts by yourself also and then try experimenting with the network and then you can move on to building your project. And that's pretty much, I think the user the developer journey in our ecosystem is. If people have come up with their MVP, they can get connected with us, and our ecosystem team can help further guide that project into going to mainnet with us.

**Chris | Spheron**

Okay, awesome. Yeah, that seems like a nice on-ramp for developers trying to get on board into the ecosystem.

### Shardeum CTAs and Announcements

**Chris | Spheron**

I guess I wanted to ask you, do you have any call to action for any campaigns or incentive programs or any kind of events you have coming up soon that you wanted to announce?

**Sandipan | Shardeum**

Yeah, there's some interesting stuff coming up at the beginning of February. I recommend closely monitoring the Sharia handles everywhere on social media, Discord, and Twitter. So, something is exciting for both users and developers. But I will let the team publicly announce it, and then I think we can. But something exciting is coming, which shows close to mainnet. Yeah, I would say that.

**Chris | Spheron**

Oh, no mystery. Okay, well, that's super exciting.

### Running a Community-Owned Validator Network with Spheron

**Chris | Spheron**

I'm going to pivot now into more of running validator infrastructure. One thing you touched on is a guiding principle of Shardeum, which is that it's community-driven. So, if you want community-owned and community-managed infrastructure, I feel like we really have to lower the technical bar for running validators. Right. If you need a full engineering team of DevOps engineers to deploy and operate a validator, that's a pretty high bar. So, one thing I'm excited about is Spheron's partnership with Shardeum. Suppose you haven't heard about Spheron. We are a decentralized physical infrastructure network. We try to make it easy for developers to deploy any docker container to a decentralized compute network. If you don't have a DevOps team, no problem. We try to make it as simple as possible. A couple of clicks, a few minutes, and you got a node spun up. That's kind of our philosophy. Our approach is that we have a feature called Spheron marketplace and a Shardeum node. It's pre-installed and pre-configured.

We've already gone through all the steps to install all the dependencies and get set up. We even handpicked a specific instance, like a machine, that almost exactly matches the hardware requirements for Shardeum. So basically, the developer flow is you click a link, go to Spheron Marketplace, click a button, and that brings you to the Spheron cluster deployment page, and everything is already preset. You must configure your region and your Shardeum GUI password—the Shardeum GUI for operating and administering the node. So yeah, we have tons of resources for you to consume to learn how to deploy node, but it's pretty easy. And we'll send out these videos, these articles, and our docs, of course. One exciting thing we just released to make it as simple and friction-free as possible is a telegram bot where you can do a slash command. You type in a chat command into a telegram bot, and you can spin up a Shardeum node.

### Using Spheron’s Telegram bot to Deploy a Shardeum Node

**Chris | Spheron**

Have you had a chance to work with our telegram bot for deploying a Shardeum node yet, or have you seen the video?

**Sandipan | Shardeum**

Yeah, for sure. I've already gone through it, and I've already tested the bot. And yeah, I'm very excited about that because, from our team, we already planned it to be as simple as possible. That's why we even have a GUI. Many of the node infrastructures of other networks don't even have that. It's deliberately kept complex to keep people away from running, trying to start running their nodes, and in many cases, you can't even run the nodes. But in our case, as I mentioned, the network benefits from that. And we have already tried to make that process simple. But I think infrastructure like Smyron is even taking that to the next level that just using your phone, you can, using the bot, you can start setting up your own sharia validator. So that's another level of simplification, which I think the community will appreciate.

**Chris | Spheron**

Yeah, absolutely. If you want to be community-owned and inclusive, you must also allow non-technical users to participate. It shouldn't be just engineers who have a certification that could participate.

### Thanks for Listening!

**Chris | Spheron**

This is our first Twitter space of 2024, so I want to take a quick moment to shout out some of our milestones. **From 2023, we onboarded 7000 developers into the** [**Spheron**](https://spheron.network/) **ecosystem. We've handled 42 million API requests. We had the first annual Web3 Reinvent conference. We've uploaded 1 million files to ipfs, 5700 deployments, four nines of uptime, and added four data centers. So now we have three regions that you could deploy to. We have 30 marketplace templates, including Shardeum, where you can deploy a node in minutes with just a GUI or a telegram bot. You don't have to be a DevOps engineer, and that's how it should be. Right, let me see. Yeah, we will send out all the links to the resources we discussed during the space.** Yeah, I want to thank you so much, Sandipan, for speaking with us today. We appreciate your partnership and admire the mission and philosophy of Shardeum.

**Sandipan | Shardeum**

I'm super glad to be working with a team like Spheron, and we appreciate the integration. We are looking forward to seeing how even people with no background in node running can spin up their Shardeum nodes using Spheron and take it up a further step. And also for shipping. It's so fast. That's what I love. So, yeah, thanks a lot.

**Chris | Spheron**

Yeah, definitely, we try to move fast and not break things.

**Sandipan | Shardeum**

I think that's a better way of moving fast.

**Chris | Spheron**

Yeah, cool. Thank you so much for joining us on our first Twitter space of the new year. And yeah, we'll give you the recording. We'll send this out, we'll send out a recap of the Twitter space. Yeah, and I guess that's about it. Thank you, everyone. Keep on building.

**Sandipan | Shardeum**

Awesome. Thanks for having me. Thanks, everyone. Bye bye.

**Chris | Spheron**

Yes, thanks. Bye.