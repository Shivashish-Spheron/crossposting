---
title: "Managing Compute and Storage Infrastructure with a DAO-Based Deployment Pipeline"
seoTitle: "Managing Compute & Storage Infra with a DAO-Based Deployment Pipeline"
seoDescription: "Delve into the process of using executed DAO Proposals to automatically trigger a deployment pipeline for community-owned infra using Spheron"
datePublished: Sun Feb 25 2024 06:50:20 GMT+0000 (Coordinated Universal Time)
cuid: clt15hmoo000009l2ewpkhwtf
slug: managing-compute-and-storage-infrastructure-with-a-dao-based-deployment-pipeline
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1708843548289/7773070b-f178-4f30-9d96-395ce3eebbc6.png
tags: blockchain, cryptocurrency, web3, decentralization, daos

---

%[https://www.youtube.com/watch?v=nyhw-KNx12k] 

Imagine a DAO proposal consisting of text describing nodes, indexers, validators, or other web3 computing infrastructure that needs to be deployed and operated for the DAO.  The DAO members would have to rely on others to take these actions and trust that they were done to specification.

What if a DAO proposal could clearly define a representation of infrastructure-as-code?  Furthermore, what if there were an automated deployment pipeline that would automatically deploy that infrastructure in response to the execution of that DAO proposal?

This article delves into the process of using executed DAO Proposals to automatically trigger a deployment pipeline for community-owned infrastructure using a DAO smart contract deployed on an EVM-compatible network and a deployed back-end service that can use Etherscan to poll for log events emitted by the DAO smart contract.

## What is Spheron Network?

[Spheron Network](https://spheron.network/) is a web3 infrastructure platform that provides tools and services to decentralize cloud storage and computing, allowing audited data centers to join the Spheron marketplace. The decentralized and governed nature of the infrastructure, overseen by Spheron, ensures permissionless access and heightened security for all users. Spheron Compute offers a feature-rich alternative to traditional cloud services at only one-third of the cost.

Spheron offers a [Compute Marketplace](https://docs.spheron.network/marketplace-guide), which allows users to set up useful tools quickly and easily, whether they want to deploy databases, nodes, tools, or AI. With Spheron, you don't have to worry about the technical stuff, and you can focus on deploying your Node with ease. Spheron Network has also partnered with organizations like [Shardeum](https://blog.spheron.network/deploy-and-stake-a-shardeum-validator-on-spheron-in-minutes), [Avail](https://blog.spheron.network/deploy-an-avail-node-in-minutes-using-spheron-compute), [Elixir](https://blog.spheron.network/step-by-step-guide-to-launching-an-elixir-node-with-spheron), [Filecoin](https://filecoin.io/), [Arbitrum](https://arbitrum.io/), etc., to redefine access to it and promote a more decentralized, inclusive, and community-centric ecosystem.

**Spheron provides features such as Private images, Auto-scale instances, Scale on demand, Real-time instance metrics, Faster GPUs, Free Bandwidths, Terraform Providers and SDKs, Instance health checks, activity, shell access, and more. Spheron provides add-on storage solutions for long-term data storage and edge bandwidth acceleration through its global CDN**[**.**](https://blog.spheron.network/deploy-an-avail-node-in-minutes-using-spheron-compute) **With Spheron**[**,**](https://filecoin.io/) **you can easily set up your nodes in just a few minutes and enjoy low maintenance and operations costs and a great developer experience.**

If you don’t already have a [Spheron account, then sign up here](https://app.spheron.network/#/signup)!

## High-Level Design of the Process 

Deploying community infrastructure Spheron via a DAO proposal execution can be accomplished in a streamlined process that does not require any DevOps knowledge!

![](https://lh7-us.googleusercontent.com/Q1uB8_9G1dFbfhQQgyNHiwWOKq7DzB5E15oGvfkDmdzNu6FCL2Pzsj8Wu2Gk9-m1Vjm3ixtXQHNXcAFnlzBZA0iHUyRakPv2SRHz4nij-jvbdB7V6lHNwEwfszhwaSp2PCHmY0d2tcNp7uR9cpuODW4 align="left")

### Designing the DAO Voting, Proposal, and Execution Process

*In this section, we will discuss how the various DAO operations will function and what specific features need to be implemented so that we can notify a backend service that certain infrastructure needs to be deployed.*

First off, we need to design how the DAO functions.  We need to implement 4 basic functions of a DAO at the minimum:

1. **DAO Membership:**  We need to gate membership to the DAO by possession of a membership NFT in the DAO member’s wallet.
    
2. **Proposal Creation:**  We need to allow certain members of the DAO to create a Proposal.
    
    * **Proposal:**  A proposal is a set of data represented as a struct, a basic Solidity data structure. The proposal contains the number of yes/no votes, the deadline, whether it’s been executed yet, and a list of members who voted.
        
    * We then add another field to that proposal that stores a JSON that will represent the infrastructure that will be deployed. This JSON is defined by the [Spheron SDK and contains details about a deployed instance](https://docs.spheron.network/sdk/compute#create).
        
3. **Proposal Voting:**  We also need to allow DAO members to vote yes or no on a proposal
    
    * Vote weight, or the number of votes, can be related to the number of NFTs members hold in their wallets.
        
    * Proposals will have a deadline, which is the block. Timestamp plus a certain elapsed amount of time.
        
4. **Proposal Execution:**  If a proposal reaches a quorum of voters and the number of yes votes is greater than no votes(simple majority), then that proposal will be eligible for execution after the deadline has passed
    
    * Executing a proposal will emit a specific event, `DeployEvent`, which can be detected by using the Etherscan API.
        
    * The `DeployEvent` will be used by a backend service that is polling the contract address for these specific events on a specific topic and will begin the deployment process in response to this event.
        

### **Defining the Data Structure of a Proposal**

Here is an example of the Solidity code, which defines a Proposal’s metadata as a struct:

```javascript
struct Proposal {

        // deadline - the UNIX timestamp until which this proposal is active. Proposal can be executed after the deadline has been exceeded.
        uint256 deadline;
        // yayVotes - number of yay votes for this proposal
        uint256 yayVotes;
        // nayVotes - number of nay votes for this proposal
        uint256 nayVotes;
        // executed - whether or not this proposal has been executed yet. Cannot be executed before the deadline has been exceeded.
        bool executed;
        // voters - a mapping of SpheronDevsNFT tokenIDs to booleans indicating whether that NFT has already been used to cast a vote or not
        mapping(uint256 => bool) voters;
        // spheronInstanceJson - a string representation of a JSON representing infrastructure to be deployed on Spheron
        string spheronInstanceJson;
    }
```

###  **Defining the Emitted Event**

The `spheronInstanceJson` string should also be a member of the emitted DeployEvent so that the backend service polling for events has easy access.

```javascript
event DeployEvent(address indexed _from, string msg, string spheronInstanceJson);
```

### **Defining the Execute Proposal Function**

The `executeProposal()` function should emit the `DeployEvent` if the proposal has a simple majority of yes votes.

```javascript
  function executeProposal(uint256 proposalIndex)
    external
    nftHolderOnly
    inactiveProposalOnly(proposalIndex)
    {
        Proposal storage proposal = proposals[proposalIndex];

        // If the proposal has more YAY votes than NAY votes
        if (proposal.yayVotes > proposal.nayVotes) {
            emit DeployEvent(msg.sender, "Deploy", proposal.spheronInstanceJson);
        }
        proposal.executed = true;
    }
```

The full source code for the SpheronDevsDAO Solidity smart contract is available at the following [Spheron Github repository](https://github.com/spheronFdn/SpheronDevsDAO).

### Designing the NFT Contract for DAO Membership

We will be gating access to the DAO based on ownership of a specific NFT and defining the voting weight of the NFT based on the number of NFTs a member possesses.

We will pass the address of the deployed SpheronDevsNFT contract to the SpheronDevsDAO constructor.

```javascript
  constructor(address _spheronDevsNFT) payable {
        spheronDevsNFT = ISpheronDevsNFT(_spheronDevsNFT);
    }
```

Then, we will create a modifier to ensure that only NFT holders are able to perform specific actions in the DAO.

```javascript
 modifier nftHolderOnly() {
        require(spheronDevsNFT.balanceOf(msg.sender) > 0, "NOT_A_DAO_MEMBER");
        _;
    }
```

The full source code for the SpheronDevsNFT Solidity smart contract is available at the following [Spheron Github repository](https://github.com/spheronFdn/SpheronDevsNFT).

### Designing the Backend Service for Polling Events and Performing the Spheron Deployment

We will need to create a backend service that can perform 2 main functions:

1. Polling the [Etherscan API Logs Module](https://docs.etherscan.io/api-endpoints/logs) for `DeployEvent` events emitted by the deployed `SpheronDevsDAO` contract.
    
2. Using the [Spheron Compute SDK](https://docs.spheron.network/sdk/compute) to deploy the specific infrastructure defined by the `spheronInstanceJson`string.
    

This service will need a process that operates on a specific set interval that polls the Etherscan API logs module for specific events emitted by a deployed SpheronDAO contract.

The service will define a function with a @Cron annotation that will execute every 5 seconds.  This function will query the Etherscan API for emitted events passing in the deployed SpheronDevsDAO contract address and an Etherscan API Token.

We will then iterate over the returned list of found events filter for a specific topic and then parse the event for the associated spheronInstanceJson string.

The full source code for the Spheron Community Infrastructure Provisioning Service is available at the following [Spheron Github repository](https://github.com/spheronFdn/CommunityInfraProvisioning).

## Implementation Details of the Operationalized System

Now that we have designed the process, how do we actually implement the system?

![](https://lh7-us.googleusercontent.com/qAUjXousNQpuJSaeTnN7nPHohrTpGqYzkTLeQWqLrQbAFDGGvn-QQZd-Q6atu7lrVCLL1srQBjPZ4kb6kOhQ2ci5X-G2f5Yip139hQQWrNtCF6A0klP9-FHUng4wmg9gAzefEF1C5N_r50vDM7ZIrn4 align="left")

### Deploying our Smart Contracts

We will be deploying these contracts on the Ethereum Sepolia testnet.

We will be using Hardhat to deploy our contracts.  You can read more about deploying to the [Ethereum testnets from the Hardhat docs](https://hardhat.org/tutorial/deploying-to-a-live-network).

### Deploying our Backend Service

We will create a Nest.js backend service that is Dockerized and deployed to Spheron.  

We will need to pass in 3 environmental parameters:

1. Etherscan API Token
    
2. Spheron Access Token
    
3. Deployed DAO Contract Address
    

We will need to create a Dockerfile for the service and push it up to DockerHub:

```javascript
FROM node:18-alpine

ARG ETHERSCAN_API_TOKEN
ENV ETHERSCAN_API_TOKEN=$ETHERSCAN_API_TOKEN

ARG SPHERON_ACCESS_TOKEN
ENV SPHERON_ACCESS_TOKEN=$SPHERON_ACCESS_TOKEN

ARG DEPLOYED_DAO_CONTRACT
ENV DEPLOYED_DAO_CONTRACT=$DEPLOYED_DAO_CONTRACT

# Create app directory
WORKDIR /usr/src/app

# Copy application dependency manifests to the container image.
COPY --chown=node:node package*.json ./

# Install dependencies
RUN npm ci

# Bundle app source
COPY --chown=node:node . .

# Build the Next.js app
RUN npm run build

# Set NODE_ENV environment variable
ENV NODE_ENV production

USER node

# Expose the port that Next.js runs on
EXPOSE 3000

# Run the Next.js app
CMD [ "node", "dist/main.js" ]
```

Then, we will need to deploy this service to Spheron.

* Click the "New Cluster" button.
    
* Select Compute Type As: On-demand
    
* Select “Import from Docker Registry” and enter the image and tag of the Docker image.
    
    * **Image:**  chrisaspheron/community-infra-provisioning
        
    * **Tag:** latest
        

Choose your region, instance plan, and amount of storage. Then map port 3000 to a random port.

### Executing Operations on our Deployed DAO Contract

We then need to call our deployed DAO smart contract, create the proposal, vote on the proposal, and execute it.  We have created a series of Hardhat scripts that we can execute for these operations.

**Minting a SpheronDevs DAO Membership NFT**

In the [SpheronDevsNFT](https://github.com/spheronFdn/SpheronDevsNFT) project, we can execute the following steps to mint an NFT.

Setup your `.env` file:

```javascript
INFURA_HTTP_URL=
PRIVATE_KEY=
```

Run the following script in the /hardhat directory:

```javascript
npx hardhat run scripts/mint.js --network sepolia
```

**Creating a DAO Proposal**

In the [SpheronDevsDAO](https://github.com/spheronFdn/SpheronDevsDAO) project we can execute the following steps to create a DAO proposal.

Setup your **.env** file:

```javascript
INFURA_HTTP_URL=
PRIVATE_KEY=
```

Run the following script in the `/backend directory:`

```javascript
npx hardhat run scripts/createProposal.js --network sepolia
```

**Voting on a DAO Proposal**

Then, we need to vote on the proposal we just created.

```javascript
npx hardhat run scripts/vote.js --network sepolia
```

**Executing the DAO Proposal**

Finally, we need to execute that proposal.

```javascript
npx hardhat run scripts/execute.js --network sepolia
```

From this point onward, the deployment pipeline should be triggered, and the next steps should happen automatically.

---

## The Automatic Deployment Pipeline in Action

Now that all the pieces are in place let’s review how the deployment pipeline works and take a look at each piece in action.

After executing the proposal, the Ethereum transaction will be broadcast and confirmed on Sepolia, and a DeployEvent Solidity log event will be emitted.  Etherscan will index the transaction and event data, which will then be made available via the Etherscan API.

Our backend service is polling the Etherscan API every 5 seconds and will pick up the event after it is indexed.

```javascript
  @Cron(CronExpression.EVERY_5_SECONDS)
    async pollForEvent() {

       let url = `https://api-sepolia.etherscan.io/api?module=logs&action=getLogs&address=${process.env.DEPLOYED_DAO_CONTRACT}&page=1&offset=1000&apikey=${process.env.ETHERSCAN_API_TOKEN}`;

        let res = await this.httpService.axiosRef.get(url)
            .then(response => response);
```

It will then use the Spheron Compute SDK to deploy the instance defined by the spheronInstanceJson string from the event.  The SDK will allow for the specific infrastructure-as-code to be deployed on Spheron’s decentralized, robust, and elastic compute service as portable Docker containers.

```javascript
    const client = new SpheronClient({
            token: process.env.SPHERON_ACCESS_TOKEN,
        });

return client.instance.create(config);
```

---

## Benefits of Spheron

Spheron’s composable architecture allows for deep integrations with external systems, CI/CD pipelines, and smart contracts, as detailed in this article.  Spheron offers a streamlined developer experience while maintaining the flexibility to define infrastructure-as-code in customized deployment pipelines.  Spheron’s decentralized architecture is robust and elastic and will ensure any infrastructure that is deployed is resilient and responsive.

## Conclusion

As we can see, it is possible to automate deployment of infrastructure based on executed proposals from a DAO.  

In general, DAO proposals consisting purely of text rely on another party to take action in response to the proposal execution and the DAO members must trust that the actions taken are in accordance with the spirit of the specifications.  DAO members must trust that these actions are executed in good faith and in the best interest of the DAO.

When a DAO proposal is able to explicitly define actions, such as a JSON specification representation of infrastructure-as-code, it leads to more clarity and minimization of trust when executing proposals.  This leads to more productive, effective, and efficient DAO management and operation. The future of DAOs is in the automatic execution of logic in response to proposal execution in a transparent, predictable, and reliable manner.