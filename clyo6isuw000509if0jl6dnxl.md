---
title: "Particle Network: A Comprehensive Overview"
seoTitle: "Particle Network: A Comprehensive Overview"
seoDescription: "Particle Network is a comprehensive Web3 infrastructure system that offers developers convenient tools for building protocols and DApps, while also serving."
datePublished: Tue Jul 16 2024 08:56:28 GMT+0000 (Coordinated Universal Time)
cuid: clyo6isuw000509if0jl6dnxl
slug: particle-network-a-comprehensive-overview
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1725881288130/b58f468b-0370-4b28-9ef7-d13f71363c5b.png
tags: ai, artificial-intelligence, blockchain, web3, decentralization, wallet, spheron, depin, particle-network

---

[Particle Network](https://particle.network/) is a comprehensive Web3 infrastructure system that offers developers convenient tools for building protocols and DApps, while also serving as a robust support hub for infrastructure. This alleviates the developers' workload, allowing them to concentrate on creating key features and enhancing user experience.

Beyond providing a variety of SDKs for Wallet, NFT, and Node Service, Particle Network places a particular emphasis on Account Abstraction. This focus distinguishes Particle Network in the Crypto market, as Account Abstraction technology is vital for expanding Crypto's reach to a broader audience.

Account Abstraction technology optimizes infrastructure and facilitates the integration of Blockchain and cryptocurrencies into everyday life. Through this feature, Particle Network offers a powerful technical platform and significantly promotes widespread Crypto adoption. This positions Particle Network as a crucial and pioneering partner in the journey towards Mass Adoption of Crypto.

## **Overview**

Particle Network, co-founded by [Pengyu Wang](https://www.linkedin.com/in/pengyu-wang-1a6391195/?originalSubdomain=sg) and [Tao Pan](https://x.com/0xpeterpan_), [was announced in April 2022](https://medium.com/@ParticleNetwork/particle-network-secures-1-5m-to-build-the-web3-mobile-app-data-and-development-platform-69b6297cd0fb). Leveraging their background in mobile game development, the founders established Particle Network to offer backend infrastructure for developers. The company has successfully [raised $25 million](https://blog.particle.network/25-million-funding/) across four funding rounds, attracting investors such as Spartan Group, Gumi Crypto, Animoca Ventures, LongHash Ventures, and Alibaba Group. The incentivized L1 testnet for Particle Network was [launched on May 2, 2024](https://blog.particle.network/particle-network-testnet-guide-airdrop/), with point rewards available through the [Particle Pioneer platform.](https://pioneer.particle.network/en) The mainnet launch is planned for the latter half of 2024.

## **Particle Network Key Features**

### [**Universal Accounts**](https://developers.particle.network/docs/universal-accounts)

Particle Network's Universal Accounts consolidate token balances across all chains by seamlessly routing and executing atomic cross-chain transactions. These accounts leverage Particle’s Universal Liquidity, functioning as specialized Smart Accounts deployed and coordinated across multiple chains. A Universal Account can be created and managed by connecting a wallet, derived from social logins via Particle Network’s [Modular Smart Wallet-as-a-Service](https://developers.particle.network/docs/modular-smart-waas) or a Web3 wallet like MetaMask, UniSat, or Keplr.

[![](https://files.readme.io/acfbf36-8-2.png align="left")](https://developers.particle.network/docs/particle-chain)

Universal Accounts utilize Particle Network to maintain a unified state and employ Universal Liquidity. They act as an interface over existing wallets, enabling users to deposit and utilize funds across a chain-abstracted ecosystem. Developers can integrate Universal Accounts into their dApps using Particle Network’s Universal SDKs.

### [**Universal Liquidity**](https://developers.particle.network/docs/universal-liquidity)

Universal Liquidity aggregates balances across all chains, driven by atomic cross-chain transactions and swaps managed by the Particle Network. These transactions are powered by Bundler nodes, which execute UserOperations on target chains using Liquidity Providers to move intermediary tokens, such as USDC and USDT, between chains through token pools.

[![Transaction flow for cross-chain UserOperations, using the movement of value between Polygon and Base as an example](https://i.imgur.com/eMNc1Gb.png align="left")](https://developers.particle.network/docs/particle-chain)

For instance, using USDC across multiple chains to purchase an NFT priced in ETH on Base involves Particle Network aggregating the user's USDC balances, allowing the purchase, and automatically swapping USDC to ETH to complete the transaction. This process adds only a few seconds of processing time and is seamless to the user.

### **Universal Gas**

![Stack of core functionalities provided by Particle Network's Modular L1](https://files.readme.io/f2bc7b3-photo_2024-05-10_21-33-33.jpg align="left")

Particle Network addresses the fragmentation of gas tokens across chains by unifying balances through Universal Liquidity. Historically, maintaining gas fee balances across chains has been a significant user friction point. Particle Network resolves this by using its native Paymaster, allowing users to pay gas fees with any token on any chain, ultimately settled in the Particle Network L1 using the chain’s native token, PARTI. Users do not need to hold PARTI, as the required swaps are performed automatically.

## **Core Architecture**

### **Modular L1 Approach**

Particle Network adopts a unique modular L1 architecture, compartmentalizing different infrastructure components to decentralize tasks, with some outsourced to third parties. This is realized through Modular Nodes, a collection of nodes driving Particle Network’s core functionalities.

### **Utility and Key Modules**

Particle Network utilizes three primary modules to address Web3's user and account fragmentation across chains:

* **Master Keystore Hub:** Acts as the central component for coordinating smart contract deployments and updates across networks, ensuring state parity for each Universal Account instance. Account settings are stored centrally and synchronized automatically.
    
* **Decentralized Messaging Network (DMN):** Relayer Nodes use a Messaging Protocol to monitor user operations on external chains and settle execution status on the L1. This network ensures the synchronization and maintenance of smart account states across chains.
    
* **Decentralized Bundler:** Designed for high-volume, cross-chain UserOperation processing, the decentralized Bundler network initiates and executes UserOperations on external chains.
    

### **Modular Nodes**

Modular Nodes allow operators to contribute to Particle Networks and support decentralization by validating and computing key functionalities:

![Architecture of the Particle Network Modular L1](https://particlenetwork.notion.site/image/https%3A%2F%2Fprod-files-secure.s3.us-west-2.amazonaws.com%2Fa9eb77b9-d04c-48f1-ba2e-b7cdb5cc9116%2F2cca301b-8987-4db8-94b3-e7b9a5373e40%2Fimage_(60).png?table=block&id=d7b50af1-dde9-479b-bda5-ede9f3b6c7e9&spaceId=a9eb77b9-d04c-48f1-ba2e-b7cdb5cc9116&width=2000&userId=&cache=v2 align="left")

* **Bundler Nodes:** Enable Universal Liquidity by bundling and executing transactions on external chains.
    
* **Relayer Nodes:** Monitor and synchronize execution status on external chains and assist in maintaining account state parity.
    
* **Watchtower Nodes:** Ensure the liveness of interconnected nodes and provide execution and fraud proofs for each block.
    

## **Aggregated Data Availability (AggDA)**

![](https://i.imgur.com/6EaMYzP.jpeg align="left")

Particle Network employs a unique [Data Availability (DA)](https://developers.particle.network/docs/particle-chain#aggregated-data-availability-aggda) approach, coordinating cross-chain transactions while maintaining state across Universal Accounts. This involves aggregating multiple DA providers such as Celestia, Avail, and NEAR DA, enhancing security, stability, and redundancy through random deterministic redundancy or selective conditional publishing.

## **Dual Staking**

![](https://i.imgur.com/IdPny65.jpeg align="left")

Particle Network employs a dual staking model to ensure crypto-economic security and accessibility. Two validator pools secure the network by using BTC's economic security through Babylon and its native token, PARTI. This reduces dependence on the native token, leveraging the crypto-economic security of staked ETH.

## Project development

Particle Network boasts a globally distributed team of 30+ full-time employees, predominantly developers. Through our ongoing collaborations, they are helping shape Web3’s chain abstraction scene, unifying efforts for the greater benefit of our ecosystem and advancing awareness of Web3’s increasing fragmentation.

Furthermore, since the initial announcement of its modular L1, we’ve established over 60 blockchain partnerships to initially support Universal Accounts, including Berachain, Avalanche, Arbitrum, and zkSync. The initial implementation of the Particle Network modular L1 and Universal Accounts will also be supported by various partner technologies, such as Avail DA, Celestia, Hyperlane, and Babylon.

## **Public Testnet Launch**

On May 2, 2024, Particle Network [launched](https://blog.particle.network/particle-network-testnet-guide-airdrop/) its public testnet, featuring two key functionalities: Universal Accounts and Universal Gas. Users can [sign up for the testnet](https://pioneer.particle.network/en/signup) and create a Universal Account using an EVM wallet such as MetaMask or Rainbow as the signer. Additionally, through Particle Network’s BTC Connect, users can control a Universal Account with a Bitcoin wallet, such as Unisat or OKX.

To test Particle Network’s Universal Gas feature, users can deposit native tokens from supported testnet networks (e.g., ETH for Ethereum, BNB for BNB Smart Chain). These tokens are automatically converted into Universal Gas (USDG), which can be used to send transactions on the testnet. As of now, 9.6 million transactions have utilized USDG, with UserOperations exceeding 121.5 million transactions. Note that this is an early version of Universal Gas and may change in the mainnet.

## First Co-Testnet Live

Recently, the team introduced the [Chain Abstraction Coalition, a groundbreaking collaboration](https://blog.particle.network/many-blockchains-one-mission-introducing-the-chain-abstraction-coalition/) among Web3's leading ecosystems to address the fragmentation within their ecosystem.

![Chain Abstraction Coalition: Our First Co-Testnet Is Now Live on Particle Pioneer!](https://blog.particle.network/content/images/size/w2000/2024/07/Co-Testnet-Bera-and-Sei.jpg align="left")

This coalition unites prominent networks such as Arbitrum, Berachain, Avalanche, BNB Chain, Linea, and Botanix, all dedicated to creating a unified Web3 experience that transcends individual blockchain boundaries. A key initiative for this coalition is the introduction of Co-Testnets, which demonstrate the power of chain abstraction through integrating Particle Network's Universal Accounts across multiple networks.

## **Investor Rounds**

![We’ve Raised $25M to Unify All Chains!](https://blog.particle.network/content/images/size/w2000/2024/06/Fundrasing-Updated-Banner.png align="left")

Particle Network recently has officially raised $25 Million to continue funding its vision of chain abstraction. This announcement comes after a $15M round led by Spartan Group and Gumi Crypto, with additional backing from SevenX Ventures, Morningstar Ventures, HashKey Capital, MH Ventures, UOB Venture Management, Flow Traders, ZeroSevenOne Labs, and SNZ. These investors join their OG backers, which include Animoca Ventures, LongHash Ventures, and Alibaba Group.

**Pre-Seed Round (May 5, 2022):** Particle Network raised $1.5 million in the Pre-Seed investment round, which included contributions from Insignia Ventures Partners, CyberConnect, BitCoke Ventures, 7 O'Clock Capital, FSC Ventures, Monad Labs, and others.

**Seed Round (March 29, 2023):** During the Seed investment round, Particle Network secured $7 million from various investment funds, including ABCDE, Animoca, Longhash Ventures, GSR Ventures, and HashKey.

## Spheron X Particle Network: Decentralized Compute Meets Account Abstraction

The partnership between [Spheron Network](https://www.spheron.network/) and Particle Network aims to leverage the strengths of both platforms. Spheron will provide decentralized GPU resources to Particle Network, offering scalable compute solutions for global AI workloads.

As a GPU provider in Particle's ecosystem, Spheron will enhance Particle's infrastructure by delivering cost-effective and powerful compute services. This collaboration will aid developers in building more efficient Web3 protocols and applications. It will also streamline blockchain technology integration into everyday use, driving mass crypto adoption through account abstraction and improved infrastructure support.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1725880569988/b45a6a39-da8f-4a9f-9f47-45f2cf3b411e.png align="center")

## **Particle Pioneer Program**

The [Particle Pioneer program](https://pioneer.particle.network/en) encourages user participation in the Particle Network testnet by rewarding users with PARTI points. These points make addresses eligible for future airdrops, bonuses on the People’s Launchpad, and whitelist spots for various ecosystem projects. The People’s Launchpad is designed to support and promote projects within the Particle Network ecosystem.

Users earn points by sending transactions and paying gas fees with USDG, receiving 50 points per transaction (up to 100 transactions per day). Additional points are awarded for daily check-ins, with more points given for consecutive days of transactions.

The Particle Pioneer program also offers boosted points through Particle Pioneer NFTs, which are reserved for active testnet participants and those involved in previous campaigns. There are three types of NFTs, offering point boosts ranging from 2% to 30%.

So far, 1.4+ million accounts have signed up for the Particle Pioneer program, and **13,169,760,160** PARTI points have been distributed.

## **Roadmap**

Following the testnet launch in May, Particle Network is moving closer to its mainnet launch. The roadmap includes:

* Q2 2024: Adding Universal Liquidity and Modular Nodes to the public testnet
    
* Q3 2024: Mainnet V1 launch with Universal Accounts, Universal Liquidity, and Universal Gas
    
* Q4 2024: Testnet launches for Dual Staking and AggDA
    
* 2025: Mainnet V2 with support for Dual Staking and AggDA
    

## **Closing Summary**

Particle Network is addressing the challenges of liquidity fragmentation and user experience in a multichain ecosystem. With its modular L1 blockchain, the network offers Universal Accounts, Universal Liquidity, and Universal Gas, enabling chain abstraction and simplifying user interactions across various blockchains. Since its launch in April 2022, Particle Network has introduced its incentivized L1 testnet and attracted funding from prominent investors. The team plans to launch the mainnet in the second half of 2024. Particle Network's technology stack includes the Cosmos SDK, CometBFT, and several innovative modules, facilitating seamless cross-chain transactions and state synchronization.

The public testnet, launched in May 2024, highlighted the functionalities of Universal Accounts and Universal Gas. Future plans include the integration of Universal Liquidity and Modular Nodes, with the mainnet launch set for Q3 2024 and additional features to be introduced in 2025. Competing with projects like NEAR, Avocado by Instadapp, and XION, Particle Network's comprehensive approach to chain abstraction and dual staking system positions it as a strong contender in the chain abstraction design space.