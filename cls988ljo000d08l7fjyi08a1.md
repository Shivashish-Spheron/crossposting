---
title: "Why Centralized RPC Nodes Are a Threat to Web3"
seoTitle: "Why Centralized RPC Nodes Are a Threat to Web3"
seoDescription: "The rise of decentralized RPC node providers, such as dRPC, offers a promising solution to the challenges posed by centralized infrastructure in web3"
datePublished: Sat Feb 03 2024 18:30:00 GMT+0000 (Coordinated Universal Time)
cuid: cls988ljo000d08l7fjyi08a1
slug: why-a-centralized-rpc-nodes-are-a-threat-to-web3
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1707155274911/06ebe42a-753c-4be2-a948-0e85d976a77a.png
tags: deployment, node, blockchain, cryptocurrency, rpc, web3, decentralization, centralized

---

Blockchains and the rise of the web3 ecosystem aim to eliminate the need for centralized institutions, putting the power in the hands of users through decentralized networks. The vision is to create permissionless, censorship-resistant systems that empower individuals and reshape financial institutions.

While the goal is to be user-centric and community-driven, there's a noteworthy issue within the web3 space. A small group of centralized service providers controls the primary gateways for developers and users to access on-chain data. These gateways play a vital role in decentralized applications, facilitating activities such as checking the network's state, communication between applications, transaction broadcasting, and other on-chain functions.

One crucial aspect is the Remote Procedure Call (RPC) protocol, allowing programs to execute functions on a remote server as if they were local. This concept, crucial for distributed computing, has been adapted by emerging blockchain networks to enable seamless interaction for developers and users across different nodes.

For example, suppose a user wants to swap assets, bridge to a layer-2 network, buy an NFT, or access a loan through a DeFi lending app. In that case, all these actions depend on the proper functioning of the respective RPC node infrastructure of the user's wallet, DEX, bridge, or lending platform.

In simpler terms, if these nodes fail to operate, users won't be able to access the network or the necessary data, rendering these applications useless. This potential risk is not receiving enough attention within the broader web3 community.

## History of the RPC node

The history of RPC protocols dates back to the 1970s when researchers sought to facilitate inter-process communication across different machines. This aimed to simplify distributed computing for developers.

One of the earliest successful implementations was Sun Microsystems [Network File System (NFS)](https://en.wikipedia.org/wiki/Network_File_System#:~:text=Network%20File%20System%20(NFS)%20is,like%20local%20storage%20is%20accessed.), accompanied by the ONC RPC protocol. This standardized communication protocol quickly gained traction in the industry. Microsoft followed suit in the early 1990s with [DCE/RPC](https://en.wikipedia.org/wiki/DCE/RPC) for Windows, further establishing RPC technology in the Windows ecosystem.

In the 2000s and beyond, JSON-RPC and REST emerged as popular alternatives due to their simplicity, particularly in web development. They utilize JSON for data encoding and leverage the principles of Representational State Transfer.

[JSON](https://www.json.org/json-en.html) and [REST](https://www.codecademy.com/article/what-is-rest) remain the leading RPC protocols in web2 and web3 development, enjoying widespread adoption and use.

## The Challenges of Centralized Infrastructure in Web3 Development

In the early stages of web3 development, developers had the option to either run their own blockchain nodes or use centralized RPC (Remote Procedure Call) providers, which made it easier to access nodes and launch applications quickly. However, these centralized systems faced issues like high costs and being vulnerable as single points of failure, impacting security and reliability.

The common choice for developers creating their first blockchain-based applications has been to use third-party RPC node providers due to the significant capital and technical expertise required to maintain nodes independently. Examples of these providers include Alchemy, Infura, and QuickNode, similar to how web2 cloud hosting services like AWS, Azure, and GCP support websites and mobile applications in the traditional web.

Interestingly, these web3 RPC providers rely on web2 cloud hosting providers to maintain their server infrastructure. Consequently, when major cloud providers face downtime, it results in outages in the web3 space.

Similar to web2, the web3 RPC provider landscape exhibits an oligopoly, with a few dominant players controlling the market. The RPC nodes-as-a-service business has become commoditized, leading to consolidation as providers aim to gain more market share. This trend towards centralization creates a cycle where the market is dominated by a few players, causing concerns about the decentralization of the web3 ecosystem.

**A notable example of this centralization is** [**Metamask**](https://metamask.io/)**, the largest Ethereum wallet with over 30 million users, relying solely on** [**Infura**](https://www.infura.io/) **as its RPC provider. Both Metamask and Infura are products of ConsenSys, a blockchain venture studio. However, Infura's past outages in 2020 and 2022 have caused disruptions for Metamask and other top decentralized applications (dApps).**

Centralized infrastructure, whether among RPC providers or the underlying cloud services, exposes risks such as vulnerability to government actions. Governments can potentially disrupt decentralized finance (DeFi) applications by coercing RPC providers to disable services or restrict access to blockchain networks within their borders. Furthermore, leading centralized RPC providers currently censor transactions from addresses sanctioned by the Office of Foreign Assets Control (OFAC), compromising the censorship-resistant nature essential to blockchain networks.

## The dRPC Model

In response to the challenges posed by centralization, there has been a rise in decentralized RPC node providers. Among the popular alternatives are Ankr, Lava Network, dRPC, and Pocket Network.

In early 2023, [P2P.org](http://P2P.org), a prominent player in web3 staking, collaborated with approximately 20 trusted web3 infrastructure providers to introduce [dRPC.org](http://dRPC.org), introducing a distinctive approach to decentralization. dRPC has established a network of providers offering high-performance nodes strategically placed across diverse geographical locations.

Significantly, dRPC opted not to manage its own nodes, focusing on software development and creating a load-balancing system. In this model, providers maintain their nodes, and an automated rating system selects the most suitable candidate to handle users' requests. Another noteworthy aspect is dRPC's strategic choice not to launch a token, relying instead on organic growth to compensate the providers within the network.

When compared to other decentralized providers, dRPC may not be as fully decentralized due to its "permission" approach. Providers must demonstrate adherence to specific quality and performance standards to join the network, operating nodes with low latency and high uptime. While this manual approval process sacrifices a degree of decentralization, it aims to enhance performance.

## Conclusion

In conclusion, the rise of decentralized RPC node providers, such as dRPC, offers a promising solution to the challenges posed by centralized infrastructure in web3 development. By providing a decentralized alternative to traditional centralized RPC providers, dRPC enables the web3 ecosystem to maintain its core principles of decentralization, security, and censorship resistance.

While there are trade-offs between decentralization and performance, the dRPC model is committed to balancing these factors. By leveraging a network of trusted providers and a rating system, dRPC ensures that users can access high-quality, reliable, and secure RPC services without relying on a single central authority.

As the web3 ecosystem evolves, solutions like dRPC must receive continued support and adoption. Doing so will help ensure that the benefits of decentralization are preserved and that the web3 community can continue to build and innovate without the constraints imposed by centralized infrastructure.