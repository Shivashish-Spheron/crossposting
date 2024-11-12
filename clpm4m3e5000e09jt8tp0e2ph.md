---
title: "Building a NFT Marketplace with Spheron Network Infrastructure"
seoTitle: "Building a NFT Marketplace with Spheron Network Infra"
seoDescription: "Explore the power of dInfra with Spheron's NFT Marketplace. Learn how to create our step-by-step guide to set up your own NFT marketplace powered by Spheron"
datePublished: Fri Dec 01 2023 04:30:09 GMT+0000 (Coordinated Universal Time)
cuid: clpm4m3e5000e09jt8tp0e2ph
slug: building-a-nft-marketplace-with-spheron-network-infrastructure
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1701118708831/fcc7c77b-267e-4c6c-9109-612eae244a46.png
tags: blockchain, marketplace, web3, decentralization, nft

---

In recent times, [Non-Fungible Tokens (NFTs)](https://blog.spheron.network/understanding-nfts-exploring-the-world-of-non-fungible-tokens) have transformed the digital asset by allowing exclusive ownership and authentication of digital content. The emergence of NFTs with blockchain technology has opened up exciting opportunities for both creators and collectors. Spheron, the provider of decentralized infrastructure, has introduced an extensive NFT Marketplace that displays the capabilities of its decentralized services: Storage, Compute, and Site.

This article explores the creative utilization of Spheron's range of services to establish a decentralized NFT marketplace, outlining its characteristics, operations, and the necessary steps for its creation.

## Spheron Network

[Spheron Network](https://spheron.network/) is a PaaS designed for startups, optimizing scalability and minimizing infrastructural costs to boost growth and profitability. Spheron simplifies the web hosting process, making it easy for developers to deploy their applications in just a matter of minutes. Spheron offers a suite of services that support blockchain applications, including hosting, storage, and computing services.

With Spheron's user-friendly interface and robust infrastructure, users can focus on developing great apps and dapps without worrying about the hassle of setting up and managing servers. Spheron Network takes care of the technical details so developers can concentrate on what matters most - creating innovative and successful web applications.

## Spheron NFT Marketplace: An Overview

The Spheron NFT Marketplace is a comprehensive demonstration of how Spheron's suite of services can be leveraged to create a decentralized NFT marketplace. By harnessing Spheron's [Storage](https://docs.spheron.network/sdk/), Compute, and Site services, users gain the ability to mint, list, buy, and resell NFTs within a robust and secure ecosystem. This marketplace stands as a testament to the power and versatility of decentralized technology in the realm of digital asset exchange.

## Why We Built This

The primary objective behind the development of this NFT marketplace was to provide a hands-on demonstration for aspiring individuals interested in creating their decentralized marketplace using the Spheron platform. By showcasing the utilization of decentralized infrastructure, the project aims to inspire and guide others in harnessing this technology for their initiatives.

## Setting Up the Marketplace: A Step-by-Step Guide

The process of setting up the NFT marketplace involves several steps, beginning with cloning the repository, installing dependencies, and configuring environment variables. Integration with Spheron's services—Storage, Compute, and Site—requires careful setup, including obtaining access tokens and defining Docker configurations for deployment. Also, deploying the subgraph and initiating the project via commands like yarn dev or hosting on the decentralized web using the Spheron Site completes the setup process.

To set up and run this project locally, follow these steps:

1. Clone the repository:
    

```javascript
git clone https://github.com/spheronFdn/spheron-site-deployer-service.git
```

2\. Navigate to the project directory and install dependencies:

```javascript
cd spheron-site-deployer-service
```

```javascript
npm install
```

3.Create a `.env` file using the `.env-example` as a template and fill in the required environment variables:

```javascript
NEXT_PUBLIC_NFT_MARKET_ADDRESS=<deployed_contract_address>
NEXT_PUBLIC_GRAPH_URL=<your_subgraph_api>
```

4\. Sign up for a Spheron account [here](https://app.spheron.network/).

5.Obtain your Spheron Storage access token by following the instructions [here](https://docs.spheron.network/rest-api/#creating-an-access-token).

6.In the backend directory, edit the .env file to include your Spheron Storage access token:

```javascript
SPHERON_TOKEN="<your_access_token>"
```

7.Set up a Dockerfile as per your project's requirements.

```javascript
# Use the official Node.js 16 image as a parent image
FROM node:16

# Set the working directory inside the container to /app

WORKDIR /app


# Copy the package.json and package-lock.json files into the working directory

COPY package*.json ./


# Install dependencies in the container
RUN npm install 

# Copy the rest of your app's source code from your host to your image filesystem.
COPY . .

# Inform Docker that the container listens on the specified network port at runtime.
EXPOSE 8080

# Define the command to run your app using CMD which defines your runtime
CMD ["node", "index.js"]
```

8.Create a `.dockerignore` file to specify which files and directories should be ignored when building the Docker image.

```javascript
# Ignore node modules
node_modules

# Ignore a local .env file that should not be included in the Docker image
.env

# Ignore git and version control
.git
.gitignore

# Ignore Docker files

Dockerfile
.dockerignore
```

9.Follow the Spheron Compute documentation to build and push your Docker image, and learn about creating a Docker image [here](https://docs.spheron.network/compute/cluster/).

10.Use the `/initiate-upload` endpoint in your frontend to obtain an upload token for the browser SDK. Detailed instructions can be found [here](https://docs.spheron.network/sdk/browser/).

## Deploying the Subgraph and Starting the Project

The next steps involve deploying your subgraph and starting up your project:

```javascript
yarn global add @graphprotocol/graph-cli
graph init --studio nft-marketplace-1
graph auth --studio <your_studio_access_token>
cd nft-marketplace-1
graph codegen && graph build
graph deploy --studio nft-marketplace-1
```

Now, your subgraph is deployed, and you can start your project using `yarn dev` or host it on the decentralized web using the Spheron Site.

🚀 Congratulations! You now have your own end-to-end NFT marketplace, powered entirely by Spheron infrastructure.

## Understanding the Technology Stack

The functionality of the marketplace relies on a powerful tech stack:

* [**Browser Storage V2**](https://docs.spheron.network/sdk/storage-v2/)**:** Utilized for storing NFT metadata and images on IPFS, offering additional options like Arweave or Filecoin during server deployment.
    
* [**Spheron Compute**](https://docs.spheron.network/marketplace-guide/)**:** Operates the server necessary for generating one-time upload tokens used in the Browser SDK, ensuring secure and efficient data handling.
    
* [**Spheron Site**](https://docs.spheron.network/framework-guide/)**:** Facilitates the deployment of the marketplace frontend on the decentralized web, enabling seamless user interaction.
    
* [**The Graph**](https://thegraph.com/)**:** A decentralized protocol responsible for indexing and querying blockchain data, ensuring swift retrieval for DApps' efficient functionality.
    

## Joining the Spheron Community

We encourage you to [join our community](https://community.spheron.network/) for help, discussions, and any other queries you might have, and can quickly find answers to the questions without sifting through endless search results on Google. **Also, by joining the community you will get all of the updates & announcements of Spheron Network infrastructure. additionally can collaborate with other developers, ultimately contributing to the growth and success of the broader Web3 ecosystem**

## Conclusion

**The Spheron NFT Marketplace stands as a testament to the transformative capabilities of decentralized infrastructure in the realm of NFT transactions. By providing a comprehensive framework and leveraging Spheron's suite of services, this project paves the way for aspiring developers and entrepreneurs to embark on their journey towards creating decentralized marketplaces. The integration of blockchain technology not only ensures security and transparency but also opens doors to endless possibilities in the digital asset space.**

In conclusion, the development of a fully functional NFT marketplace powered by Spheron's infrastructure marks a significant milestone, showcasing the potential for innovation and decentralized exchange within the rapidly evolving digital ecosystem.

## Reference

* [Spheron Compute Docs](https://docs.spheron.network/compute/cluster/)
    
* [Spheron Browser Upload SDK](https://docs.spheron.network/sdk/browser/)
    
* [Spheron Site Docs](https://docs.spheron.network/static/deployment/logs/)
    
* [The Graph Docs](https://thegraph.com/docs/en/)
    
* [Github Repository of the Use Case](https://github.com/spheronFdn/NFTMarketPlace)