---
title: "Deploy a Pryzm Node in Minutes using Spheron Compute"
seoTitle: "Deploy a Pryzm Node in Minutes using Spheron Compute"
seoDescription: "This article delves into the seamless deployment process for a Pryzm Node using Spheron, a user-friendly platform simplifying node configuration and"
datePublished: Thu Feb 15 2024 04:45:26 GMT+0000 (Coordinated Universal Time)
cuid: clsmqmhf4000209jp5aljfqxq
slug: deploy-a-pryzm-node-in-minutes-using-spheron-compute
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1707937490205/80b63293-f8f7-4a45-91d6-058d6de797ba.png
tags: deployment, node, blockchain, cryptocurrency, web3, compute, decentralization, spheron, pryzm

---

%[https://www.youtube.com/watch?v=VcW1ps2Lt-Y] 

This article delves into the seamless deployment process for a Pryzm Node using Spheron, a user-friendly platform simplifying node configuration and participation in the Pryzm ecosystem.

## What is Spheron Network?

[**Spheron Network**](https://spheron.network/) is a web3 infrastructure platform that provides tools and services to decentralize cloud storage and computing, allowing audited data centers to join the Spheron marketplace. The decentralized and governed nature of the infrastructure, overseen by Spheron, ensures permissionless access and heightened security for all users. **Spheron Compute offers a feature-rich alternative to traditional cloud services at only one-third of the cost.**

Spheron offers a [**Compute Marketplace**](https://docs.spheron.network/marketplace-guide), which allows users to set up useful tools quickly and easily, whether they want to deploy databases, nodes, tools, or AI. With Spheron, you don't have to worry about the technical stuff, and you can focus on deploying your Node with ease. Spheron Network has also partnered with organizations like [**Shardeum**](https://blog.spheron.network/deploy-and-stake-a-shardeum-validator-on-spheron-in-minutes), [**Avail**](https://blog.spheron.network/deploy-an-avail-node-in-minutes-using-spheron-compute), [**Elixir**](https://blog.spheron.network/step-by-step-guide-to-launching-an-elixir-node-with-spheron), [**Filecoin**](https://filecoin.io/), [**Arbitrum**](https://arbitrum.io/), etc, to redefine access to it and promote a more decentralized, inclusive, and community-centric ecosystem.

**Spheron provides features such as Private images, Auto-scale instances, Scale on demand, Real-time instance metrics, Faster GPUs, Free Bandwidths, Terraform Providers and SDKs, Instance health checks, activity, shell access, and more. Spheron provides add-on storage solutions for long-term data storage and edge bandwidth acceleration through its global CDN. With Spheron**[**,**](https://filecoin.io/) **you can easily set up your nodes in just a few minutes and enjoy low maintenance and operations costs and a great developer experience.**

## **How do you deploy Pryzm Node using Spheron Compute?**

Deploying a Pryzm Node on Spheron is a simple, streamlined process that does not require any DevOps knowledge!

### **Step 1: Create a Free Spheron Network Account**

1. Visit Spheron Network: [**spheron.network**](https://spheron.network/)
    
2. On the Spheron homepage, locate and click the [**"Free Trial"**](https://app.spheron.network/#/login) button.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706809743224/9835c20a-08ac-4ceb-b338-02bf61d73d08.png?auto=compress,format&format=webp&auto=compress,format&format=webp align="left")
    
3. You'll be directed to a signup page. Choose your preferred authentication method: Web2 (GitHub account, GitLab account, or Bitbucket account) or Web3 (Ethereum).
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706810181090/ba8e9e85-0b8b-4337-9de6-57752de91851.png?auto=compress,format&format=webp&auto=compress,format&format=webp align="left")
    
4. Follow the provided prompts to authenticate your chosen account securely. This step ensures safe access to the Spheron Network platform. After successful authentication, you'll be guided to a confirmation page confirming the completion of your account setup.
    

### **Step 2: Creating an Organization**

1\. Upon logging in, you'll be directed to the Create Organization page, where you can give your **organization name and choose Avatar**. Ensure the **"compute"** option is selected from the drop-down menu of the **"Start With"** option. Click **“Continue”**.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706810800400/a9abec2b-ca7c-41e5-a31a-4b12cb8c2aca.png?auto=compress,format&format=webp&auto=compress,format&format=webp align="left")

2\. Next, you'll be taken to a new page. Click the **"Create New Project"** button.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706814975307/82f8ee13-8a76-43cc-afcc-2e6e13044117.png?auto=compress,format&format=webp&auto=compress,format&format=webp align="left")

3\. Add '**Project Title'** And '**Project Description'**, Click **Create**.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710929092806/4965d6b3-faee-450e-9eca-367326e1fceb.png align="center")

### **Step 3: Deploying a Pryzm Node With Spheron Platform UI**

Follow these steps to deploy a Pryzm Node:

1\. Choose "Compute" to use CPU-based instances for running containers.

2\. Choose your desired Compute Type option under Compute Type.

**NOTE:** Please schedule a team call to gain early access to the **"Spot"** Type.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706816196072/f3be6d4c-d64a-4dff-ace7-f249ff21653f.png?auto=compress,format&format=webp&auto=compress,format&format=webp align="left")

3\. Click **"Start from Marketplace App"** and Select **"Pryzm Validator Testnet"** from the marketplace.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707923842061/17b7c176-31c6-4f12-b792-df2930ddfc19.png align="center")

4\. **Select Region:** Select your preferred region for deployment. Choosing a region closer to your users can improve performance and reduce latency.

5\. Next, Choose an instance plan that aligns with your requirements. Spheron will recommend a suitable plan according to the Pryzm template, but you can customize it if needed from available plans or choose to **'Create Custom Plans.'**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707924015695/fe6256f0-35f5-4a06-8379-3a3397832ff1.png align="center")

6\. Next, Configure storage. You get 2 options to choose from:  
First, you can choose storage from the available options or the custom storage option that fits your needs. This storage will be volatile and is erased when the instance is restarted, redeployed, or shut down.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707924177181/9b737089-980c-447a-ba8c-972b7b0862f6.png align="center")

Additionally, you get the option to choose Persistent Storage. Persistent storage will not be erased unless the instance is closed. If choosing persistent storage, specify the type of storage (NVMe) and Add a mount point.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707924269306/8efc7a0b-15f8-4890-9370-f525e3828f7c.png align="center")

7\. Next, You'll be asked to provide a unique identifier for your node, a "**Moniker**." Think of the Moniker as a nickname for your node that will help you identify it on the blockchain network.

Click **"Deploy"** to deploy your node. Once your node is set up and running as a validator, you can view its status and activity through the Pryzm Validator Dashboard at [this link](https://testnet.chainsco.pe/pryzm/validators).

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707924523764/b95569bc-9b4c-40cf-9bc1-42d9684e26bd.png align="center")

8\. Wait for your node to be fully set up. After it's provisioned, you'll see an option called **‘Overview’** in the dashboard; click on it to see all the details of the deployed node on Pryzm.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710930293153/7b6cd40c-2ad6-4a38-ba6c-2585971785a2.png align="center")

9\. Now, Click on the deployed `pryzm-validator-testnet` and go to **'Shell Command.'**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710930480977/396aa3fe-9b00-4e43-b66c-1d6a0ea7a2d9.png align="center")

### **Step 4: Prepare Your Environment Before Working on Commands**

**1\. Before adding any commands in Sheel, initialize your environment by running:**

```javascript
. $HOME/.profile
```

**If you encounter an error** that says `/bin/sh: 1: pryzmd: not found`, run the same command again to fix it.

### **Step 5: Create or Recover Your Wallet**

**1\. To create a new wallet**, type in the Shell:

```javascript
pryzmd keys add wallet
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710931912992/32318802-4215-4216-b506-e0f95abf7579.png align="center")

**Note:** Important to write this mnemonic phrase in a safe place It is the only way to recover your account if you ever forget your password.

**2\. To recover an existing wallet**, use:

```javascript
pryzmd keys add wallet --recover
```

Then, enter your mnemonic phrase when prompted.

### **Step 6: Fund Your Wallet**

**1\. Visit the faucet app** at [this link](https://testnet.pryzm.zone/faucet) to request test tokens for your wallet. Enter the Pryzm address you got from the above step.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710932105729/76fe64fb-2f69-4dc4-a798-73e9fa0022de.png align="center")

**2\. Check your wallet balance** using:

```javascript
pryzmd q bank balances $(pryzmd keys show wallet -a)
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707925436896/46e49a8a-9bfe-4d22-83de-b50e0c7563fe.png align="center")

3\. Make sure you receive at least **2 upryzm** tokens.

**4\. If you don't see a balance**, your node might still be syncing with the blockchain. Wait until the `catching_up` status is `false`.

**5\. Monitor your wallet on the Pryzm Explorer:** Keep an eye on your transactions and balance by visiting [Pryzm Explorer](https://testnet.chainsco.pe/pryzm) and entering your wallet address. This step is crucial for ensuring that your wallet has been successfully funded and correctly reflects the blockchain transactions.

### **Step 7: Verify Network Synchronization**

**Check the synchronization status** with:

```javascript
pryzmd status | jq .SyncInfo
```

Proceed when `catching_up` turns to `false`.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710932296606/c7233f5f-38bc-4d95-a59f-6d8bb35c98fc.png align="center")

### **Step 8: Register Your Validator**

**1\. Use the following command to create your validator**, replacing placeholders with your information:

```javascript
pryzmd tx staking create-validator --amount 1000000upryzm --pubkey $(pryzmd tendermint show-validator) --moniker "your-moniker-name" --details "your-details" --website "your-website" --security-contact "your-email" --chain-id indigo-1 --commission-rate 0.05 --commission-max-rate 0.20 --commission-max-change-rate 0.01 --min-self-delegation 1 --from wallet --gas-adjustment 1.4 --gas auto --gas-prices 0.015upryzm -y
```

**2\. Customize the command with your details:** Replace `your-moniker-name`, `your-details`, `your-website`, and `your-email` with your own information.

**3\. Wait a few minutes** after executing this command before checking your node on the [Pryzm Validators list](https://testnet.chainsco.pe/pryzm/validators).

## Cheat Sheet

### 1\. Managing keys

Managing keys on a Tendermint-based chain involves securing and controlling access to cryptographic keys used for chain operations.

* Generate a new key: `pryzmd keys add wallet`
    
* Recover key: `pryzmd keys add wallet --recover`
    
* List all keys: `pryzmd keys list`
    
* Delete key: `pryzmd keys delete wallet`
    
* Export key: `pryzmd keys export wallet`
    
* Query wallet balances: `pryzmd q bank balances $(pryzmd keys show wallet -a)`
    

### 2\. Managing validators

Ensure you've updated your moniker, identity, details, and website to match your values.

1\. Create validator:

```javascript
pryzmd tx staking create-validator --amount 1000000upryzm --pubkey $(pryzmd tendermint show-validator) --moniker "your-moniker-name" --identity "your-keybase-id" --details "your-details" --website "your-website" --security-contact "your-email" --chain-id indigo-1 --commission-rate 0.05 --commission-max-rate 0.20 --commission-max-change-rate 0.01 --min-self-delegation 1 --from wallet --gas-adjustment 1.4 --gas auto --gas-prices 0.015upryzm -y
```

2\. Edit validator:

```javascript
pryzmd tx staking edit-validator --new-moniker "your-moniker-name" --identity "your-keybase-id" --details "your-details" --website "your-website" --security-contact "your-email" --chain-id indigo-1 --commission-rate 0.05 --from wallet --gas-adjustment 1.4 --gas auto --gas-prices 0.015upryzm -y
```

3\. Unjail validator:

```javascript
pryzmd tx slashing unjail --from wallet --chain-id indigo-1 --gas-adjustment 1.4 --gas auto --gas-prices 0.015upryzm -y
```

4\. Validator jail reason:

```javascript
pryzmd query slashing signing-info $(pryzmd tendermint show-validator)
```

5\. List active validator:

```javascript
pryzmd q staking validators -oj --limit=3000 | jq '.validators[] | select(.status=="BOND_STATUS_BONDED")' | jq -r '(.tokens|tonumber/pow(10; 6)|floor|tostring) + " \\t " + .description.moniker' | sort -gr | nl
```

6\. List inactive validator:

```javascript
pryzmd q staking validators -oj --limit=3000 | jq '.validators[] | select(.status=="BOND_STATUS_UNBONDED")' | jq -r '(.tokens|tonumber/pow(10; 6)|floor|tostring) + " \\t " + .description.moniker' | sort -gr | nl
```

7\. View validator details:

```javascript
pryzmd q staking validator $(pryzmd keys show wallet --bech val -a)
```

### 3\. Managing Tokens

1\. Withdraw reward from all validators:

```javascript
pryzmd tx distribution withdraw-all-rewards --from wallet --chain-id indigo-1 --gas-adjustment 1.4 --gas auto --gas-prices 0.015upryzm -y
```

2\. Withdraw reward and commission:

```javascript
pryzmd tx distribution withdraw-rewards $(pryzmd keys show wallet --bech val -a) --commission --from wallet --chain-id indigo-1 --gas-adjustment 1.4 --gas auto --gas-prices 0.015upryzm -y
```

3\. Delegate tokens to your validator:

```javascript
pryzmd tx staking delegate $(pryzmd keys show wallet --bech val -a) 1000000upryzm --from wallet --chain-id indigo-1 --gas-adjustment 1.4 --gas auto --gas-prices 0.015upryzm -y
```

4\. Delegate the token to other validators, change `<to-valoper-address>` as you like:

```javascript
pryzmd tx staking delegate <to-valoper-address> 1000000upryzm --from wallet --chain-id indigo-1 --gas-adjustment 1.4 --gas auto --gas-prices 0.
```

## Conclusion

In conclusion, deploying a Pryzm Node using Spheron Network is a straightforward process that can be completed in just a few steps. With Spheron, users can easily set up a Pryzm Node without extensive technical knowledge, making it accessible to a wider range of participants. By following the steps outlined in this guide, users can quickly and easily deploy their own Pryzm Node and start contributing to the network.