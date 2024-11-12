---
title: "Deploy and Stake a Shardeum Validator on Spheron in Minutes"
seoTitle: "Deploy and Stake a Shardeum Validator on Spheron in Minutes"
seoDescription: "Discover how to deploy and stake a Shardeum Validator on Spheron within minutes. Learn how to leverage dynamic state sharding in blockchain technology"
datePublished: Tue Jan 16 2024 06:25:22 GMT+0000 (Coordinated Universal Time)
cuid: clrfyzfz8000o08jte1ch3f3l
slug: deploy-and-stake-a-shardeum-validator-on-spheron-in-minutes
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1705386074062/d2633bdd-7628-4573-83d4-05654d85c58c.png
tags: deployment, blockchain, web3, compute, decentralization, spheron, shardeum

---

%[https://www.youtube.com/watch?v=gueNJzEz-bU] 

In blockchain technology, solutions addressing the scalability trilemma – scalability, security, and decentralization – have remained an ongoing challenge. [Shardeum](https://shardeum.org/) emerges as a groundbreaking EVM-compatible Layer 1 (L1) smart contract platform, revolutionizing this space by leveraging dynamic state sharding. This innovative approach redefines the validation process, distributing transaction verification across shards in the network for enhanced throughput and scalability.

This article delves into the seamless deployment and staking process for a Shardeum validator using Spheron, a user-friendly platform simplifying node configuration and participation in the Shardeum ecosystem. Through step-by-step guidance, users can easily deploy a Shardeum node, contribute to network security, and stake testnet SHM (Shardeum's native token) to actively participate in the testnet.

## What is Shardeum?

[Shardeum](https://shardeum.org/) is an EVM-compatible, [dynamically state sharded](https://docs.shardeum.org/introduction/dynamicstatesharding) L1 smart contract platform. Expressed simply, sharding breaks the job of validating and confirming transactions into small pieces or shards and spreads them out in the network.

*Here is a diagram demonstrating how un-sharded data in a single node can be sharded amongst three nodes:*

![](https://lh7-us.googleusercontent.com/kMLPADP0KHobzOwHogY4zeqarhrlk1WOA2pEfFYpPENDrwCJMvRzMv6DX9_igU404XuCpH_oxCHe3Z-eQmANWxykurVlN0KZBg6NpJPAHo4-mM0o__kqKx8cUeN8aBNsC0LmsfHkRqMlLBaW2fR8tnY align="left")

*Image created with LucidChart*

Shardeum utilizes parallel processing across shards to achieve high throughput with linear scalability.  This is achieved while concurrently enabling low gas fees & and ensuring security with a combined [proof-of-stake and proof-of-quorum for consensus](https://docs.shardeum.org/introduction/consensus), while block-level consensus is not required for finality.

## Solving the Scalability Trilemma

![](https://lh7-us.googleusercontent.com/V0QZsjldDWJ_fhSnB2XVqddLbFG2uxYLquAuwAgI_rEu9-VnkAvq59Lzxo4twxcFDmqU19ho9S1kSLLrO-i2nmhCDZOYzrdxlDZcJXKYYBqh1DI2kJU7Lee4qMRrZyi4zKu9xQCfDbq86rkNevRiaFk align="center")

The [scalability trilemma](https://www.researchgate.net/publication/342639281_Scaling_Blockchains_A_Comprehensive_Survey) is a set of trade-offs originally posited by Vitalik Buterin, where blockchains can generally only prioritize two out of 3 of the following characteristics:

1. Scalability
    
2. Security
    
3. Decentralization
    

Vitalik did add the caveat that achieving all three is actually possible but very difficult.

Shardeum solves this problem with the following:

* Performing consensus and processing at the transaction level instead of the block level.
    
* Using dynamic state sharding to achieve scalability through parallelization by distributing workload throughout the network.
    
* Reduced overhead for validator nodes because they only need to store state data for their own shard.
    
* This allows the network to auto-scale horizontally by adding additional nodes instead of being forced to scale vertically by increasing the computing resources of each node.
    
* This allows for fast finality and atomic shard composability.
    

## What is Spheron Network?

[**Spheron Network**](https://spheron.network/) is a Web3 infrastructure platform that provides tools and services to decentralize cloud storage and computing. It allows audited data centers to join the Spheron marketplace. Spheron oversees the decentralized and governed nature of the infrastructure, ensuring permissionless access and heightened security for all users. **Spheron Compute offers a feature-rich alternative to traditional cloud services at only one-third of the cost.**

Spheron offers a [**Compute Marketplace**](https://docs.spheron.network/marketplace-guide), which allows users to set up valuable tools quickly and easily, whether they want to deploy databases, nodes, tools, or AI. With Spheron, you don't have to worry about the technical stuff, and you can focus on deploying your Node with ease. Spheron Network has also partnered with organizations like [**Shardeum**](https://blog.spheron.network/deploy-and-stake-a-shardeum-validator-on-spheron-in-minutes), [**Avail**](https://blog.spheron.network/deploy-an-avail-node-in-minutes-using-spheron-compute), [**Elixir**](https://blog.spheron.network/step-by-step-guide-to-launching-an-elixir-node-with-spheron), [**Filecoin**](https://filecoin.io/), [**Arbitrum**](https://arbitrum.io/), etc, to redefine access to it and promote a more decentralized, inclusive, and community-centric ecosystem.

**Spheron provides features such as Private images, Auto-scale instances, Scale on demand, Real-time instance metrics, Faster GPUs, Free Bandwidths, Terraform Providers and SDKs, Instance health checks, activity, shell access, and more. Spheron provides add-on storage solutions for long-term data storage and edge bandwidth acceleration through its global CDN. With Spheron**[**,**](https://filecoin.io/)**you can easily set up your nodes in just a few minutes and enjoy low maintenance and operations costs and a great developer experience.**

## Deploy a Shardeum Validator on Spheron

Deploying a Shardeum Validator on Spheron is a straightforward process. Running a Shardeum validator allows you to contribute to network security while also earning testnet SHM rewards. Here's a step-by-step guide to setting it up:

### **Step 1: Create a Free Spheron Network Account**

1. Visit Spheron Network: [**https://spheron.network/**](https://spheron.network/)
    
2. On the Spheron homepage, locate and click the ["Free Trial"](https://app.spheron.network/#/login) button.
    
    ![](https://lh7-us.googleusercontent.com/XxVLkP28yZ4SXX7AvuRfwp7BUO8csnyzW0V8jMmFGRqajYZ5AEn5mJjg6jBKpOhc_TJX8QflckpOSyp-u9KewI_I9Mo88P68Nz6F115K0M8-4co5MYeFgdBEgeLu7xKEXZYGBRdMcVGtKHWIsAQPnlM align="left")
    
3. You'll be directed to a signup page. Choose your preferred authentication method: Web2 (GitHub account, GitLab account, or Bitbucket account) or Web3 (Ethereum).
    
    ![](https://lh7-us.googleusercontent.com/cH0fQ0JpI0Dmd-cwMN8okxCh8hWxbv_d3SNmZei4nQLU0Pn8GoHUT8Z4dGu4-n3x4Q2OcB1n_10A4o_4vAjZdjmM4T_tOoJoQIMkx_16JO4n8f1ff82NWzNytP43bcQH1nX9ZwjtjztswOUo-ARL7Ek align="left")
    
4. Follow the provided prompts to authenticate your chosen account securely. This step ensures safe access to the Spheron Network platform. After successful authentication, you'll be guided to a confirmation page confirming the completion of your account setup.
    

### **Step 2: Creating an Organization**

1\. Upon logging in, you'll be directed to the Create Organization page, where you can give your **organization name and choose Avatar**. Ensure the **"compute"** option is selected from the drop-down menu of the **"Start With"** option. Click **“Continue”**.

![](https://lh7-us.googleusercontent.com/c-lBK9YvpFciyfiV4aoSsoIa_QidNJsdPOgRqQDHf_iPKXANJH8mS9V9Fsv5K-cvyrPuHg7yY_4xNXvJSyITNVd8FLZcVT--SPVfDj7dMYBg3VfwmludxUVifHeyz-vkkwsFjtIn83RKb7YRsWj-5Xs align="left")

2\. Next, you'll be taken to a new page. Click the **"Create New Projects"** button.

![](https://lh7-us.googleusercontent.com/D3aPgsDmdh3TY-KDU58nIha1fW6tJnD_Qp4d-Pxp0YdawusSrc-PYDGui-36wzRyXNfQq3SSSlUKlOfFSf2cvpbqPKJxAtxXjCCYwdtcUH7GF7HwUrIdZhYgBYGMPCZErWO5lMg5RH7NoTOAT9MlU04 align="left")

3\. Add '**Project Title'** And '**Project Description'** and Click **Create**.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710911719480/c88210d1-c303-4326-8a87-97e5bd182577.png align="center")

### **Step 3: Deploying a Shardeum Node With Spheron Platform UI**

Follow these steps to deploy a Shardeum Node:

1\. Choose "Compute" to use CPU-based instances for running containers.

2\. Choose your desired Compute Type option under Compute Type.

**NOTE:** Please schedule a team call to gain early access to the **"Spot"** Type.

![](https://lh7-us.googleusercontent.com/BM4DECrUj-nUCLLw-VcGl5V7F8idjB-HyT_eurCE992c-JJZi8xv_lCsX6FHQBi_XPVPfGJbJMWgpWKlBSj35o6Lo1uotFQpIqTNzqE8fdlAr101lEhQgybjTmaafvP4b4Xq9s-lStylaroCWaPis08 align="left")

3\. Click **"Start from Marketplace App"** and Select **"Shardeum Testnet Validator"** from the marketplace. Spheron marketplace has a pre-baked docker image for the [Shardeum node](https://app.spheron.network/#/compute/marketplace?template=Shardeum%20Testnet%20Validator&templateId=6496eb9ba579a6bc8507cae7) that is ready to go for you!

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710911801311/23a721a2-0d6a-4e92-a660-4f9bab0e8f95.png align="center")

**4.** Select your preferred region for deployment. By default, The container will be deployed in the US-WEST region for On Demand. Choosing a region closer to your users can improve performance and reduce latency.

**Note:** For the best experience, use the **US- WEST** region to deploy your node!

5\. Next, Choose an instance plan that aligns with your requirements. Spheron will recommend a suitable plan according to the Shardeum template, but you can customize it from available plans or choose to **'Create Custom Plans.'**

This instance and storage plan were specially selected to meet the [Shardeum minimum hardware requirements noted here](https://docs.shardeum.org/node/run/validator#minimum-hardware-requirements).

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710911918943/7bcafa93-83bc-43ae-831e-96a81c36754d.png align="center")

6\. Next, Configure storage:  
You have to choose **storage** from the available options or the custom storage option that fits your needs. This storage will be volatile and is erased when the instance is restarted, redeployed, or shut down. **Additionally, you get the option to choose Persistent Storage.**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710912030632/70824230-ed26-45dd-b2ce-9a2a9648d783.png align="center")

7\. Next, You will get the option **to enable the IP on deployment. You will get 2 option to choose from.**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1711090293964/11e5ff92-5358-41ce-85d9-4aa346fe37ce.png align="center")

* **SHARED IP -** Automatically assigns a port within the 30000-32676 range. For standard web traffic, ports 80 and 443 are mapped to the assigned port, making it suitable for web applications without specific port demands.
    
* **DEDICATED IP -** Offers complete port access, including 80 and 443, for customized network configurations. It is Ideal for applications requiring direct control over network traffic.
    

**Note: We only have 200 dedicated IPs enabled in the US-WEST Region. Use Dedicated IP and make your Shardeum deployment blazing fast and super easy ⚡️**

***We will be adding more IP's soon.***

8\. The marketplace app will also automatically configure networking, ports, parameters, and commands for you. You just need to set the **password** as per your choice.  Check out the [Shardeum validator docs to learn more about these settings](https://docs.shardeum.org/node/run/validator#step-2-download-and-install-validator).

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710912085127/e652cf2a-29b6-4242-bf7b-5e165e54ae68.png align="center")

9\. Spheron abstracts away the difficulty of configuring a node.  You just need to click Deploy!  Check out the [Spheron docs for more info](https://docs.spheron.network/marketplace-guide/shardeum/).

Wait for your node to be fully set up. After it's provisioned, you'll see an option called **‘Overview’** in the dashboard; click on it to see all the details of the deployed node on Shardeum.

Now, there’s just one final step to get our validator working after this initial deployment is complete.

### **Step 4: Update the Configuration**

1\. Go to the **'Overview'** section on the left and click on the deployed shardeum node.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710914134667/9b14a5d8-fb0b-4880-b210-3fcaabc7d6a4.png align="center")

2\. Now, you will see the screen below. Copy the connection URL and go to the Settings option.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710912666025/35e84d45-effe-4473-8c1e-022af8ca68bc.png align="center")

3\. In the setting option, scroll down the configuration and copy and paste the connection URL address, leaving **HTTP://** and **:9001** and past it to the **'SERVERIP'** and **'LOCALLANP'.** Click **'Update'.**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710914343780/9f0984a4-22c1-4dfc-bc56-ca4d4f48459d.png align="center")

### Step 5: Staking your Shardeum Validator to Join the Testnet

Now that we have a Shardeum node deployed, the next step is to stake our validator with SHM so that it can be included in the network during the next rotation.

**Acquire SHM in your Wallet for Staking**

Follow these steps to set up your wallet for staking:

**1:**[Add the Shardeum network](https://docs.shardeum.org/network/endpoints) to your wallet, such as [Metamask](https://metamask.io/)

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710918398574/ef8952c2-fb14-4b1c-a2e3-9d0d3b3f90f5.png align="center")

**2:** Claim some [testnet SHM from the faucet](https://docs.shardeum.org/faucet/claim) on the Shardeum Discord.  You should receive 15 SHM from the faucet, and you will need 10+ gas fees.

![](https://lh7-us.googleusercontent.com/yqBDdqlCSUOxCWiF-H5LQRAaKDj61Wu39R2xH144y4diDa9hT2qP1QP6z7fsCQ86qa-FuMmhVkgXutfi5znr9XvRy1xI3jwTrjlkJu-b81oazLsB8heExcZjFtkxDIKzLIQ5R_TkRXGO0N8GfdgDaaM align="center")

**3:** Verify on the Discord server, then go to the **“validator-faucet”** channel and use the **/faucet** command to request SHM.

![](https://lh7-us.googleusercontent.com/RADXOQcbK83vRFPzbUkC4raJVkr-ZnF9kh39wIM31FPDshEtoJkaawOFz4QsfrnQWwx38Tj1klk92DBQK1ee3Ho7LTFa48SSf1TykgsZ4kSMTv9o5QURgIU0N07OOfXz-o8ThlAjTIiGokPmUNLBl2o align="center")

4\. Go back to the **'overview'** section and click on deployed shardeum node. Next, Spheron is forwarding port 8080, which the GUI runs on.  Get the **“Connection URL,”** which maps from port **8080** internally, and enter that URL into a browser to access the Shardeum validator dashboard.

Be sure to access the URL appended with “https://” \*\*\*e.g.\*\*\**https://provider.us-west.spheron.wiki:32085/*

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710917538522/ca0c9455-4f8e-4660-89a8-75c8364da6d0.png align="center")

**Note:** You might see a warning page when trying to access this address in your web browser. Ignore this warning and continue using the validator dashboard\*\*.  The Shardeum docs have a\*\* [**fix for that SSL issue**](https://docs.shardeum.org/Node/Run/Validator#step-4-open-validator-gui:~:text=You%20might%20see%20a%20warning%20page%20when%20trying%20to%20access%20this%20address%20in%20your%20web%20browser.%20Ignore%20this%20warning%20and%20continue%20to%20the%20validator%20dashboard.%20Another%20way%20to%20work%20around%20this%20warning%3A)**.**

**5.** Then log in with the password you set up earlier.

![](https://lh7-us.googleusercontent.com/ZiGdnwhfdWBeYUtx50IfZ9lj42ozZDK5Uzbi3MdQV-iFr1JGtV65klOuH7MC4t6DRQrBzWzl1U4nDMYxZ7hRvyVmvcthy_2Tou0Bdyk0fPJAh3WxpBnqHaMMkbZ22y5YCwZ5sMYgS1btY3R2foovCNg align="center")

**6.** Next, let’s start up the Validator.  Go to the “Maintenance” tab, then click the **“Start Node”** if it’s not already running.

![](https://lh7-us.googleusercontent.com/nOxeyuLuwjPMye8TzAbT_AEawpPm6sUN0oAbZGgAUZkE2NrV6okGZPAVAxWAw0bJmR5k4McQenj5KiNKGkoz7lSPbFuWI_0fs8gL1SRBkyWE2sc4tzMA1aofAexXrS7z7wydg-pWrOQB6C_UURDCe0o align="center")

**7.** Next, on that same page, click “Connect Wallet”.  Approve the prompt that pops up in your wallet.  After that, click “Add Stake”.  You should have received 15 SHM from the faucet from the step above.

* Stake Wallet Address *\[pre-populated with connected wallet\]*
    
* Nominee Public Key *\[pre-populated by validator\]*
    
* Stake amount (SHM) *\[In terms of ETH, not WEI\]*
    

It is recommended to stake 10 SHM.

![](https://lh7-us.googleusercontent.com/18Gv_lUkCBxz2hYRQHu3ylyCaDlYNV7faOTtnZJyYIOpbNc_fXg-vxeHctS84jOH36u31ad4R6lJAOeZX8WfzfkI6ft07_KYvkzLR2LhKwlB1kwz9jAU1oM57w6giJU3gUOZHKLTBgwR-d_AQWMtjms align="center")

**8.** Enter 10 into the “Stake Amount” field and click “Stake” then sign the wallet transaction.

![](https://lh7-us.googleusercontent.com/QluU2qkAnABJ61xpP6hUWFNPKjbA-42rvWDPRqEkub8JEIi9LWEAmsCtw5k7cPu_3tglyP-oudyfTyUNKTSCZDsq0H7CU8NaGXLNSFCWUvLAsjzsWYWY3qJKjidJQjunVUiSAryCvdVGGlFEvpQ-pGM align="center")

9\. You can view the staking transaction on the Sphinx Shardeum block explorer.

**Example:**

[*https://explorer-sphinx.shardeum.org/tx/0x5f55856fc3a0476d65037ccca099594fc8e345699fada0d3686e9e32f2a1e686*](https://shardeum.org/)

### Joining the network

Your node will initially be in **“Standby”** mode but become **“Active”** during the next rotation.

Alternatively, if you prefer, you can stake directly via the CLI; check the [Shardeum docs for more info](https://docs.shardeum.org/node/run/validator#cli).  This will require you to expose your private key as a secret ENV var, so be sure your wallet does not contain any mainnet assets.

After completing your stake, you can check the node status with the **operator-cli** on the **“Shell”** tab on your Spheron instance page.

Check the node status with the following command:

```javascript
operator-cli status
```

You can also check the status of your GUI with:

```javascript
operator-cli gui status
```

Check back on your node after taking a break; eventually, your node will transition from **“Standby” mode to “Active”!**

Congratulations!  You are now running a staked Shardeum validator.  Spheron will do all the heavy lifting to ensure your node is a resilient and responsive network member!

Check out this [Shardeum FAQ](https://shardeum.org/blog/how-to-run-a-validator-node-on-shardeum-sphinx/#Frequently_Asked_Questions_FAQs) for answers to common validator issues.

## Conclusion

In conclusion, deploying and staking a Shardeum validator on Spheron is straightforward and can be completed in a few simple steps. With Spheron's user-friendly interface and automated configuration, users can easily participate in the Shardeum testnet, contribute to the network's security, and earn testnet SHM rewards.

Following the instructions in this article, users can deploy a Shardeum node, update the config, and stake their validator to join the testnet. This combination of advanced technology and user-friendly platforms makes blockchain participation more accessible and rewarding.

## References

* **Spheron Doc** - [https://docs.spheron.network/marketplace-guide/shardeum](https://docs.spheron.network/marketplace-guide/shardeum)
    
* **Shardeum Doc -**[https://docs.shardeum.org/node/run/validator](https://docs.shardeum.org/node/run/validator)