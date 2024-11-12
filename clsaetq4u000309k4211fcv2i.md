---
title: "Deploy a Babylon Node in Minutes using Spheron Compute"
seoTitle: "Deploy a Babylon Node in Minutes using Spheron Compute"
seoDescription: "Spheron Compute is a powerful tool that simplifies the process of deploying Babylon Nodes, making it accessible to a wider range of users."
datePublished: Tue Feb 06 2024 13:41:54 GMT+0000 (Coordinated Universal Time)
cuid: clsaetq4u000309k4211fcv2i
slug: deploy-a-babylon-node-in-minutes-using-spheron-compute
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1707226876707/1835f18e-e50a-4bd7-ac49-1ffe501260f5.png
tags: deployment, node, blockchain, cryptocurrency, web3, decentralization, babylon

---

%[https://www.youtube.com/watch?v=Qm-9WcXXwPs] 

This article delves into the seamless deployment process for a Babylon Node using Spheron, a user-friendly platform simplifying node configuration and participation in the Babylon ecosystem.

## What is Spheron Network?

[**Spheron Network**](https://spheron.network/) is a web3 infrastructure platform that provides tools and services to decentralize cloud storage and computing, allowing audited data centers to join the Spheron marketplace. The decentralized and governed nature of the infrastructure, overseen by Spheron, ensures permissionless access and heightened security for all users. **Spheron Compute offers a feature-rich alternative to traditional cloud services at only one-third of the cost.**

Spheron offers a [**Compute Marketplace**](https://docs.spheron.network/marketplace-guide), which allows users to set up useful tools quickly and easily, whether they want to deploy databases, nodes, tools, or AI. With Spheron, you don't have to worry about the technical stuff, and you can focus on deploying your Node with ease. Spheron Network has also partnered with organizations like [**Shardeum**](https://blog.spheron.network/deploy-and-stake-a-shardeum-validator-on-spheron-in-minutes), [**Avail**](https://blog.spheron.network/deploy-an-avail-node-in-minutes-using-spheron-compute), [**Elixir**](https://blog.spheron.network/step-by-step-guide-to-launching-an-elixir-node-with-spheron), [**Filecoin**](https://filecoin.io/), [**Arbitrum**](https://arbitrum.io/), etc, to redefine access to it and promote a more decentralized, inclusive, and community-centric ecosystem.

**Spheron provides features such as Private images, Auto-scale instances, Scale on demand, Real-time instance metrics, Faster GPUs, Free Bandwidths, Terraform Providers and SDKs, Instance health checks, activity, shell access, and more. Spheron provides add-on storage solutions for long-term data storage and edge bandwidth acceleration through its global CDN. With Spheron**[**,**](https://filecoin.io/)**you can easily set up your nodes in just a few minutes and enjoy low maintenance and operations costs and a great developer experience.**

## **How do you deploy Babylon Node using Spheron Compute?**

Deploying a Babylon Node on Spheron is a simple, streamlined process that does not require any DevOps knowledge!

### **Step 1: Create a Free Spheron Network Account**

1. Visit Spheron Network: [**https://spheron.network/**](https://spheron.network/)
    
2. On the Spheron homepage, locate and click the ["Free Trial"](https://app.spheron.network/#/login) button.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706809743224/9835c20a-08ac-4ceb-b338-02bf61d73d08.png?auto=compress,format&format=webp align="left")
    
3. You'll be directed to a signup page. Choose your preferred authentication method: Web2 (GitHub account, GitLab account, or Bitbucket account) or Web3 (Ethereum).
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706810181090/ba8e9e85-0b8b-4337-9de6-57752de91851.png?auto=compress,format&format=webp align="left")
    
4. Follow the provided prompts to authenticate your chosen account securely. This step ensures safe access to the Spheron Network platform. After successful authentication, you'll be guided to a confirmation page confirming the completion of your account setup.
    

### **Step 2: Creating an Organization**

1\. Upon logging in, you'll be directed to the Create Organization page, where you can give your **organization name and choose Avatar**. Ensure the **"compute"** option is selected from the drop-down menu of the **"Start With"** option. Click **“Continue”**.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706810800400/a9abec2b-ca7c-41e5-a31a-4b12cb8c2aca.png?auto=compress,format&format=webp align="left")

2\. Next, you'll be taken to a new page. Click the **"Create New Projects"** button.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710172530482/dc261abd-b32f-4b87-8f87-9f28f1f2acf1.png align="center")

3\. Add '**Project Title'** And '**Project Description'** and Click **Create**.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710182465982/4637bb10-5496-43ee-a129-3b36d45d9293.png align="center")

### **Step 3: Deploying a Babylon Node With Spheron Platform UI**

Follow these steps to deploy a Babylon Node:

1\. Choose "Compute" to use CPU-based instances for running containers.

2\. Choose your desired Compute Type option under Compute Type.

**NOTE:** Please schedule a team call to gain early access to the **"Spot"** Type.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710174155538/42c36577-6b0f-45cc-af6d-124fe4afb509.png align="center")

3\. Click **"Start from Marketplace App"** and Select **"Babylon Validator Testnet"** from the marketplace.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710174288947/716c28d3-49ee-45ec-b562-7affc1d226a6.png align="center")

4\. **Select Region:** Select your preferred region for deployment.  Choosing a region closer to your users can improve performance and reduce latency.

5\. Next, Choose an instance plan that aligns with your requirements. Spheron will recommend a suitable plan according to the Babylon template, but you can customize it if needed from available plans or choose to **'Create Custom Plans.'**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707225112801/ee0721c5-45d4-4c46-a46f-e6b026f6e297.png align="center")

6\. Next, Configure storage:  
You have to choose storage from the available options or the custom storage option per your needs. This storage will be volatile and is erased when the instance is restarted, redeployed, or shut down.

Additionally, you get the option to choose Persistent Storage. Persistent storage will not be erased unless the instance is closed. If choosing persistent storage, specify the type of storage (NVMe) and Add a mount point.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707225203878/df108931-93a2-490c-b43d-9d1329d1254a.png align="center")

7\. During the configuration, you'll be asked to provide a unique identifier for your node, known as a "**Moniker**." Think of the Moniker as a nickname for your node that will help you identify it on the blockchain network. Click "Deploy" to deploy your node. **With Moniker, once your node is published as a validator, you can check it in the Babylon dashboard -**[https://babylonscan.io/validators](https://babylonscan.io/validators)

![](https://lh7-us.googleusercontent.com/Vaq2EvwgVBbjblJ0EdZCCzvGfuELQyDMOnY3DEuhlNPKz-6gzsioXzOCHpLC3YRUvl9pvJLZSzGHLS4ScB0Ns924IErVdBLzMWuqdlxqYLlxHlW4QMdFsGsyetrRXstEKR9Q9WbmusNpuaNP5UKnegs align="left")

8\. **Wait for your node to be fully set up.** After it's provisioned, you'll see an option to refresh the logs. Click the refresh icon to do this.

**Go to the Shell:** This is where you'll enter commands to interact with your node.

### Step 4: Create or Recover Your Wallet

1\. **To create a new wallet**, type in the Shell:

```javascript
babylond keys add wallet
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710923048070/886a3371-b484-4864-9d02-e8a813a7bfaf.png align="center")

**Note: It is important to write this mnemonic phrase in a safe place.** It is the only way to recover your account if you ever forget your password.

2\. **To recover an existing wallet**, use the below command:

**Note: You can reuse the same wallet in a new node by running this command.**

```javascript
babylond keys add wallet --recover
```

Then, enter your mnemonic phrase when prompted.

***Note: This step will ask for entering a keyring. Please enter a greater than 8-character password, which you should remember to decrypt in future steps.***

### Step 5: Fund Your Wallet

1\. To receive funds, visit the **#faucet** channel on the [official Babylon Discord server](https://discord.com/invite/babylonglobal). Here, you can request funds by sharing the address you previously created.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710923227366/f40f0637-2dfb-4cba-9fd8-e7df42d48fbc.png align="center")

**2\. Check your wallet balance** using:

```javascript
babylond q bank balances $(babylond keys show wallet -a)
```

Make sure you receive at least 0.1 **ubbn** tokens.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710923767258/a94a0904-2b17-4dd9-9bab-8de58bca65b8.png align="center")

3\. Your node might still be syncing with the blockchain if you don't see a balance. Wait until the `catching_up` status is `false`[.](https://discord.com/invite/babylonglobal)

4\. **Monitor your wallet on the Babylon Explorer:** Keep an eye on your transactions and balance by visiting [**Babylon Explorer**](https://testnet.babylon.explorers.guru/) and entering your wallet address. This step is crucial for ensuring your wallet has been successfully funded and reflects the blockchain transactions correctly.

### Step 6: Do Some Additional Stuff for Babylon

1. **Generate a BLS Key Pair -**
    
    ```javascript
    babylond create-bls-key $(babylond keys show wallet -a)
    ```
    
2. **Update the Configuration Settings**
    
    ```javascript
    sed -i -e "s|^key-name *=.*|key-name = \"wallet\"|" $HOME/.babylond/config/app.toml
    ```
    
3. And then apply this command
    
    ```javascript
    sed -i -e "s|^timeout_commit *=.*|timeout_commit = \"10s\"|" $HOME/.babylond/config/config.toml
    ```
    

### Step 7: Verify Network Synchronization

1. **Check the synchronization status** with:
    
    ```bash
    babylond status | jq .sync_info
    ```
    
    Proceed when `catching_up` turns to `false`.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710924056094/bbc364bc-8a22-4f89-a282-82c964fa98de.png align="center")

### Step 8: Register Your Validator

1\. Obtain the `pubkey` with the following command and type it down on the below command:

```javascript
babylond tendermint show-validator
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710924355041/48d9f39d-4617-4109-8242-20b2459f421f.png align="center")

**2\. Use the following command to create your validator.json file**, replacing placeholders with your information:

```javascript
echo '{"pubkey": {"@type": "your-own-pubkey-type", "key": "your-own-pub-key"}, "amount": "10000ubbn", "moniker": "your-moniker-name", "website": "your-website", "security": "your-email", "details": "your-details", "commission-rate": "0.10", "commission-max-rate": "0.20", "commission-max-change-rate": "0.01", "min-self-delegation": "1"}' > validator.json
```

**Customize the command with your details:** Replace `your-moniker-name`, `your-details`, `your-website`, and `your-email` with your information.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710924544902/157e2c24-fdf8-4901-b8d1-bdc6c4bd5bd7.png align="center")

3\. Now run this command to execute the validator creation transaction on Babylon to get yourself added as a validator

```javascript
babylond tx checkpointing create-validator validator.json --chain-id bbn-test-3 --gas="auto" --gas-adjustment="1.5" --gas-prices="0.025ubbn" --from wallet
```

**Wait 30 minutes** after executing this command before checking your node on the [Babylon Validators list](https://babylonscan.io/validators).

## Conclusion

Spheron Compute is a powerful tool that simplifies the process of deploying Babylon Nodes, making it accessible to a wider range of users. With its easy-to-use interface and seamless integration with the Babylon ecosystem, Spheron Compute is an excellent choice for anyone looking to deploy a Babylon Node.