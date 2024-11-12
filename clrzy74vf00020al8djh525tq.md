---
title: "Step-by-Step Guide to Launching an Elixir Node with Spheron"
seoTitle: "Step-by-Step Guide to Launching an Elixir Node with Spheron"
seoDescription: "This comprehensive guide will walk you through launching an Elixir node using Spheron. Whether you're a blockchain enthusiast, developer or organization"
datePublished: Tue Jan 30 2024 05:58:45 GMT+0000 (Coordinated Universal Time)
cuid: clrzy74vf00020al8djh525tq
slug: step-by-step-guide-to-launching-an-elixir-node-with-spheron
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1706594086386/bdabbdd1-1785-48a9-8b4d-79cb9d0473f8.png
tags: deployment, elixir, node, blockchain, cryptocurrency, web3, decentralization, spheron

---

%[https://www.youtube.com/watch?v=3jt_5RPBxgg] 

In this comprehensive guide, we'll walk you through the process of launching an Elixir node using [Spheron](https://www.spheron.network/). Whether you're a blockchain enthusiast, developer, or organization looking to participate in network validation, this quick deployment method will get you up and running without the hassle of manual configurations.

## How do you deploy an Elixir Node using Spheron Compute?

Deploying an Elixir node on Spheron is a simple, streamlined process that does not require any DevOps knowledge!

### **Step 1: Create a Free Spheron Network Account**

1\. Visit Spheron Network: [**https://spheron.network/**](https://spheron.network/)

2\. On the Spheron homepage, locate and click the ["Free Trial"](https://app.spheron.network/#/login) button.

![](https://lh7-us.googleusercontent.com/-bOasXj2iTH5rasm5egjGldc6rTKUjwdSXcu4DRCpUaKiEy9GZ4kRuA4Pl8WZ2MgqIFkhDQrDxTzpJ4NaMpnd4PtK6Wb9wxKnfEW0sPikFjJ1WJCUx-uyeEB7V8azVV2m0IMKz39wwfjUT_iNx5AxBk align="left")

3\. You'll be directed to a signup page. Choose your preferred authentication method: Web2 (GitHub account, GitLab account, or Bitbucket account) or Web3 (Ethereum).

![](https://lh7-us.googleusercontent.com/YpOM81YGYuntp-CC6sMzh4sSijw7ieTWES8Be55h6lbtPjFKGfTrY8WKEe6E1frmz3zJF7AxaOM5QmodAlE763K0cyKY9lndvNK5rdIYccni-NGvZz9FSKb4DSPtGjp9_UtY9SrPb_l8gfSfi1fOX44 align="left")

4\. Follow the provided prompts to authenticate your chosen account securely. This step ensures safe access to the Spheron Network platform. After successful authentication, you'll be guided to a confirmation page confirming the completion of your account setup.

### **Step 2: Creating an Organization**

1\. Upon logging in, you'll be directed to the Create Organization page, where you can give your **organization name and choose Avatar**. Ensure the **"compute"** option is selected from the drop-down menu of the **"Start With"** option. Click **“Continue”**.

![](https://lh7-us.googleusercontent.com/M_GEjdum9IXW14bhAlGAog3AY6ouCYoTC61AP1wYaS8t4nJYG0yQBmQpmpNTZoWsou6r6Q7C30B4aNlSm-wVZ2QaKwLyXUlpZ3uZ1h9y6GVhAzB33c0Q4w9BLGqV7eh34_B8BNsvFVXvML9mqmHTmM4 align="left")

2\. Next, you'll be taken to a new page. Click the **"Create New Projects"** button. Add '**Project Title'** And '**Project Description'** and Click **Create**.

![](https://lh7-us.googleusercontent.com/1Qr0KIVaGMKiQv3mmh3uVWwWTQ3jl22NPkMspRMaq4vC5iTmi_0WvwGmKoTRr6nGA5htHdICv-4XzwpVq_a5I2ux2bhez_Nek5-CepYIEKxpFlCdLMFinEbqMIuSX0xKBtXOJXHIVQjHHcozwFWI9-4 align="left")

### **Step 3: Deploying Elixir Validator With Spheron Platform UI**

Follow these steps to deploy an Elixir Node:

1\. Choose **"Compute"** to use CPU-based instances for running containers.

2\. Choose your desired Compute Type option under Compute Type.

**NOTE:** Please schedule a team call to gain early access to the **"Spot"** Type.

![](https://lh7-us.googleusercontent.com/k3xiILzq8zCZ3EtTvgXUq4mTWIRvP4Ow35rQanZo8Um-baisBbAyZL6dNF4KsqWqHaAucaXrQi4VyjdvO_p6EoguulM6_8sQZnHeWpb2vooQhrm0ITVvzZtBFm5MmcCS_DIEIW1Tjh_Srjetq_pKb2A align="left")

3\. Click **"Start from Marketplace App"** and Select **"Elixir Validator"** from the marketplace.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710876850046/d7afdecc-0300-4e73-bc62-335fe9c09dfd.png align="center")

4\. **Select Region:** Select your preferred region for deployment. Choosing a region closer to you. This can improve performance and reduce latency. **US-West has a higher chance of deploying everything successfully. You can start from the US-West option.**

5\. Next, Choose an instance plan that aligns with your requirements. Spheron will recommend a suitable plan according to the Elixir template, but you can customize it from available plans or choose to **'Create Custom Plans.'**

[According to Elixir Docs](https://docs.elixir.xyz/running-an-elixir-validator), Most hardware is capable of running a validator node. However, it is recommended that you have a system that can be run 24 hours a day, with 4GB of memory and a reliable 100Mbit internet connection. Disk usage is minimal; in most cases, 30GB should be enough.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710877300885/3c94deac-2765-49db-9b43-20fedb161e58.png align="center")

6\. Next, Configure storage:  
You have to choose **storage** from the available options or the custom storage option that fits your needs. This storage will be volatile and is erased when the instance is restarted, redeployed, or shut down. **Additionally, you get the option to choose Persistent Storage.**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710877473802/35fce001-b939-47a2-be44-4661494de570.png align="center")

7\. Next, go to the configuration. In the ‘**Template Configuration’** section, you have to configure the **address, private\_key, and Validator\_name**. Add according to the below table.

![](https://cdn-images-1.medium.com/max/800/1*70D9_rsfyLevf5f35CwflQ.png align="left")

![](https://lh7-us.googleusercontent.com/kfNIVMzudP9fcf0LAOSq9VpC4CPhaZp1VUtNdoMFPLyZkCOYbzqB4teWGzjqO8uvx3TLIS3YZbxSQuNrvSg5_qo20c9XStheIFBkKsgT0-3B2f4L6S5ytEybYky4UuApSciMLDBj3OVS-9wgxNPco1k align="left")

### Step 4: **Create a Metamask account (Skip this step if you already have a Metamask wallet)**

1\. Go to [https://metamask.io/](https://metamask.io/) and click on **'Download for Chrome.'** You can also download it directly from [**here**](https://chromewebstore.google.com/detail/metamask/nkbihfbeogaeaoehlefnkodbefgpgknn?utm_source=google.com)**.**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710878042698/21a1e125-1b64-4a28-b92b-8d422efd4301.png align="center")

2\. Click **'Add to Chrome'** on the next window and add the extension to the browser.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710878188501/8ee20e96-0707-4486-b58b-9059224bfd74.png align="center")

3\. After that it will automatically open the extension window of metmask. Click the check box to agree to the terms & conditions and click **'Create a new wallet.'** If you already have a wallet, you can import it too.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710878305244/007a72cf-a647-4c3f-b695-baae899465dd.png align="center")

4\. Click I agree. The next step is to create a unique password. **Please take note that losing the password can result in the loss of the account due to MetaMask not being able to recover it. Store the password in a safe place, and try to write it down instead of saving the account details to the device.**

A video will appear, briefing about the security of passwords and warnings. Proceed to watch this video to better understand how to store passwords. Securing a password in a notebook, a safe, or a secure file is a good way to protect passwords.

### Step 5: Get the address and private\_key

1\. Click on the Metmask extension on the browser. Below the account name, you will get the '**address'**, copy it, and paste it into the Spheron address box.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710879578737/8f21c073-9d60-4465-a7fc-157f6b992ddc.png align="center")

2\. Click on the **Kebab Menu** on the upper right side, go to the account details, click **'Show Private Keys,'** add your password, and click to reveal the **private key**. Copy it and paste it to the spheron '**PRIVATE\_KEY'** box.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710880218993/8af0c437-908e-41c2-8310-25a242e9f899.gif align="center")

### **Step 6: Final Steps**

1\. After adding the **address, private\_key, and Validator\_name,** your configuration will look like the image below.

2\. Once you're all set, click **"Deploy"** to start the deployment process. It's as simple as that!

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710880653258/bc8f5c05-9465-4619-a91f-7f634e72966b.png align="center")

That's it! Your Elixir instance will now be deployed.

3\. Wait for your node to be fully set up. After it's provisioned, you'll see an option called **‘Overview’** in the dashboard; click on it to see all the details of the deployed node on Subspace.

## Claiming ELXR Tokens and Enrolling Your Validator:

### 1\. Claiming ELXR Tokens:

Do a simple Google search and Visit sites offering Goerli testnet tokens, claim ELXR tokens, and return to [dashboard.elixir.finance](http://dashboard.elixir.finance), Connect your wallet, and claim the ELXR tokens.

![](https://lh7-us.googleusercontent.com/OotbWCLaxh8e7YuxPlOZgIvE_kg-cAM-1aMu0kycSHW4gesRoj_dPwGs1Jyd2BHg5YXPs0ASWKKMd7ASkYE5ido-o67A8ssOFSSEjFLm0xG1SXQgFXhMi9Oqb1yMpfss-hmWITWokOhu2FZd32aQCkI align="left")

### 2\. Enroll Yourself:

Enroll your wallet address associated with the deployed validator. Confirm the enrollment, and once completed, stake a minimum of 100 ELXR.

![](https://lh7-us.googleusercontent.com/bwXTwX5dwCzcJXQLv1TSxLbpg7nnyra6r3PFdk3fyFmdGsFRj9rHVBsEtoQMUz25ubaNUZE9wdBUMHSOOyytJHWbDQYtVzwyTWoNEmV0L_PGJ3V0IoghahF32rY9EWfcHcweVy8InuuwTGQ6mXbh6vc align="left")

![](https://lh7-us.googleusercontent.com/CGCNOH4ZmaHyO3BoI1x5w-UCvw2bXuyUXqwACO8wiFpt0N_rT7s-xqfBYJ9ORDzsYVycC956sKM9RsR1pru1vrd8tY0Cg8oEWXTDiHQWTbewlUotRDSEEnUFBBbujIWTL9W1F5hA57ag7t320Fi5JiM align="left")

![](https://lh7-us.googleusercontent.com/nJ_5sasxIiepmUTpn2GABRlR1jDxUjYOYdyjx4bW1ZXL5pNJhFJfyU2Kcby2YWQQVmU5rip9QWEWIuZ_8dPAfnxsg7cxpR6M2V_GZGaU4MOcTdna5-Xl3-hXLHcBLFOe3909ySmRobbiKLF-cDea_eI align="left")

![](https://lh7-us.googleusercontent.com/6tQb-NjPEKBYP4C83iQBS3exglmHNh6LG8ObMXiCymmmz77IlA-rS4kEa4AwSX1D7zxPWWI1V4_sjH22JMWihuLhxU12CCG4N9KfTzk7fogDbvpspStTis3GAHRY7JS4l8KZQsbF78oBYBZyXxhNNfs align="left")

### 3\. Monitor Stake and Node Status:

Through the dashboard, you can monitor your stake and validator status. You can also monitor any logs or events related to your node's deployment.

![](https://lh7-us.googleusercontent.com/P-qnnBgiefFJvP-1K4X-G569m98f3hfzOUeZK9wIPCT5TXRtAPmMcaQTXwNoFCXKnEqlLETFxccDW9hPeUrZtnPmemNGjiUUb24sl86YxXNPCCnIX29tm1xMXCbYtxPLnMA2N2EEG4HXs_9_OUIIQ40 align="left")

## Troubleshooting and Support:

### 1\. Addressing Issues:

If you encounter any issues, refer to the [community.spheron.network](https://community.spheron.network/) or reach out on [Discord](https://sphn.wiki/discord) for assistance. Clear cache if necessary.

### 2\. Final Checks:

Verify that your node's log entries indicate successful deployment. Be patient, as it may take up to 30 minutes for logs to appear. If issues persist, seek support from the community.

## Conclusion

Congratulations, your Elixir node is up and running! Participate in the blockchain network, and if you plan to run multiple nodes, consider reaching out to Spheron for possible discounts. Stay engaged with the community and embrace the exciting world of blockchain technology. Happy deploying!

## References

* **Elixir Doc** - [https://docs.elixir.finance/running-an-elixir-validator](https://docs.elixir.finance/running-an-elixir-validator)