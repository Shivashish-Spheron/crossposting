---
title: "Deploy an Avail Full Node in Minutes using Spheron Compute"
seoTitle: "Deploy an Avail Node in Minutes using Spheron Compute"
seoDescription: "Learn how to deploy an Avail Node in minutes using Spheron Compute."
datePublished: Tue Jan 02 2024 04:58:09 GMT+0000 (Coordinated Universal Time)
cuid: clqvvpd0h000109jq7rnt7le8
slug: deploy-an-avail-node-in-minutes-using-spheron-compute
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1703794018037/a8a347f0-e9fc-49bb-bd78-21ba4ba35498.png
tags: deployment, blockchain, web3, decentralization, spheron

---

%[https://youtu.be/Wp0poU-NDR8] 

[Avail](https://www.availproject.org/) is a data availability-focused base layer designed for next-gen, trust-minimized applications and sovereign rollups. Its innovative security approach enables easy verification through peer-to-peer sampling, and blockchain integration is made easy as the developers do not have to worry about the validators set or tokenomics.

Avail prioritizes transaction ordering, allowing users to verify block data without downloading the entire block. Deploying an Avail Node on the Akash Network is now easier than ever, thanks to Spheron Compute. This step-by-step guide will walk you through the process, allowing you to set up your Avail Node within minutes.

## **What is Spheron Network?**

[**Spheron Network**](https://spheron.network/) is a Web3 infrastructure platform that provides tools and services to decentralize cloud storage and computing. It allows audited data centers to join the Spheron marketplace. Spheron oversees the decentralized and governed nature of the infrastructure, ensuring permissionless access and heightened security for all users. **Spheron Compute offers a feature-rich alternative to traditional cloud services at only one-third of the cost.**

Spheron offers a [**Compute Marketplace**](https://docs.spheron.network/marketplace-guide), which allows users to set up valuable tools quickly and easily, whether they want to deploy databases, nodes, tools, or AI. With Spheron, you don't have to worry about the technical stuff, and you can focus on deploying your Node with ease. Spheron Network has also partnered with organizations like [**Shardeum**](https://blog.spheron.network/deploy-and-stake-a-shardeum-validator-on-spheron-in-minutes), [**Avail**](https://blog.spheron.network/deploy-an-avail-node-in-minutes-using-spheron-compute), [**Elixir**](https://blog.spheron.network/step-by-step-guide-to-launching-an-elixir-node-with-spheron), [**Filecoin**](https://filecoin.io/), [**Arbitrum**](https://arbitrum.io/), etc, to redefine access to it and promote a more decentralized, inclusive, and community-centric ecosystem.

**Spheron provides features such as Private images, Auto-scale instances, Scale on demand, Real-time instance metrics, Faster GPUs, Free Bandwidths, Terraform Providers and SDKs, Instance health checks, activity, shell access, and more. Spheron provides add-on storage solutions for long-term data storage and edge bandwidth acceleration through its global CDN. With Spheron**[**,**](https://filecoin.io/) **you can easily set up your nodes in just a few minutes and enjoy low maintenance and operations costs and a great developer experience.**

## **How do you deploy an Avail Node using Spheron Compute?**

You can follow these steps to deploy an Avail Node on Spheron Compute.

### **Step 1: Create a Free Spheron Network Account**

1. Visit Spheron Network: [https://spheron.network/](https://docs.spheron.network/)
    
2. On the Spheron homepage, locate and click the "Free Trial" button.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706809743224/9835c20a-08ac-4ceb-b338-02bf61d73d08.png align="center")
    
3. You'll be directed to a signup page. Choose your preferred authentication method: Web2 (GitHub account, GitLab account, or Bitbucket account) or Web3 (Ethereum).
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706810181090/ba8e9e85-0b8b-4337-9de6-57752de91851.png align="center")
    
4. Follow the provided prompts to authenticate your chosen account securely. This step ensures safe access to the Spheron Network platform. After successful authentication, you'll be guided to a confirmation page confirming the completion of your account setup.
    

### **Step 2: Creating an Organization**

1\. Upon logging in, you'll be directed to the Create Organization page, where you can give your **organization name and choose Avatar**. Ensure the **"compute"** option is selected from the drop-down menu of the **"Start With"** option. Click **“Continue”**.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706810800400/a9abec2b-ca7c-41e5-a31a-4b12cb8c2aca.png align="center")

2\. Next, you'll be taken to a new page. Click the **"Create New Projects"** button. Add '**Project Title'** And '**Project Description'** and Click **Create**.

![](https://lh7-us.googleusercontent.com/1Qr0KIVaGMKiQv3mmh3uVWwWTQ3jl22NPkMspRMaq4vC5iTmi_0WvwGmKoTRr6nGA5htHdICv-4XzwpVq_a5I2ux2bhez_Nek5-CepYIEKxpFlCdLMFinEbqMIuSX0xKBtXOJXHIVQjHHcozwFWI9-4 align="left")

### **Step 3: Deploying an Avail Full Node With Spheron Platform UI**

Follow these steps to deploy an Avail Full Node:

1\. Choose "Compute" to use CPU-based instances for running containers.

2\. Choose your desired Compute Type option under Compute Type.

**NOTE:** Please schedule a team call to gain early access to the **"Spot"** Type.

![](https://lh7-us.googleusercontent.com/k3xiILzq8zCZ3EtTvgXUq4mTWIRvP4Ow35rQanZo8Um-baisBbAyZL6dNF4KsqWqHaAucaXrQi4VyjdvO_p6EoguulM6_8sQZnHeWpb2vooQhrm0ITVvzZtBFm5MmcCS_DIEIW1Tjh_Srjetq_pKb2A align="left")

3\. Click **"Start from Marketplace App"** and Select **"Avail Full Node"** from the marketplace.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710941960909/f6860706-e8ad-4e6f-a60d-0b1c02a2e5a5.png align="center")

4\. **Select Region:** Select your preferred region for deployment. Choosing a region closer to you. This can improve performance and reduce latency. **US-West has a higher chance of deploying everything successfully. You can start from the US-West option.**

5\. Next, Choose an instance plan that aligns with your requirements. Spheron will recommend a suitable plan according to the Avail Full Node template, but you can customize it from available plans or choose to **'Create Custom Plans.'**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710942686555/d23bb420-6452-450d-9cb5-61c9ffc47f12.png align="center")

6\. Next, Configure storage:  
You have to choose storage from the available options or the custom storage option that fits your needs. This storage will be volatile and is erased when the instance is restarted, redeployed, or shut down. Additionally, you get the option to choose Persistent Storage.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710944621910/322b3e66-f45d-4e91-8ce1-1fc73436ec05.png align="center")

7\. Next, you will get the configuration option, but Spheron has made it easy and auto-filled the configuration options. You can add advanced configuration if required. [**Click here to know mo**](https://docs.spheron.network/compute/cluster/compute#advance-configuration-1)**re.**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710944681865/97a138ee-90c1-4e8e-aaa7-77ec2c39941f.png align="center")

8\. Once you're all set, click **"Deploy"** to start the deployment process. It's as simple as that!

That's it! Your Avail Node instance will now be deployed.

**NOTE:** Wait for your node to be fully set up. After it's provisioned, you'll see an option called **‘Overview’** in the dashboard; click on it to see all the details of the deployed node on the **'Avail Full Node'**.

### **Step 4: Check your running node**

Go to Avail Telemetry [**https//**](https://telemetry.avail.tools/)[**telemetry.avail.tools/**](http://telemetry.avail.tools/)[,](https://telemetry.avail.tools/) and check the synchronization status of the node. The block needs to attain a specific hash to become part of the validation network.

*The synchronization will take time as per the network ~15hrs*

## **Benefits of Deploying Avail Node with Spheron Compute**

Deploying your Avail Node with Spheron Compute offers many benefits, including:

1. **Simplicity and Speed:** Spheron Compute's user-friendly interface and streamlined deployment process make it easy for both beginners and experienced users to set up an Avail Node quickly. You can save valuable time that would otherwise be spent on server provisioning and configuration.
    
2. **Cost-Efficiency:** Spheron Compute provides cost-effective solutions, ensuring you get the most out of your resources. You can choose the plan that aligns with your budget and scale as needed without breaking the bank.
    
3. **Reliability and Performance:** Spheron's infrastructure is designed for stability and high performance. Your Avail Node will run smoothly, ensuring you can access your data when needed without interruptions.
    
4. **Flexibility:** With various instance plans and the ability to create custom plans, you can tailor your deployment to meet your specific requirements. This flexibility allows you to optimize your resources for the best performance.
    
5. **Persistent Storage:** Spheron Compute offers the option to add persistent storage, ensuring your data is safe and accessible even if the instance is updated or replaced.
    
6. **Scalability:** Whether starting small or planning for growth, Spheron Compute allows you to scale your Avail Node deployment easily. You can handle increasing data volumes and growing user demands effortlessly.
    
7. **Support and documentation:** Spheron provides comprehensive documentation and support, helping you navigate any challenges you may face during deployment and development.
    

## **Conclusion**

Whether you're a blockchain enthusiast, developer, or organization seeking to harness the power of Avail Full Node, Spheron Network offers an efficient and accessible solution. Don't miss out on the blockchain revolution. Start your Avail Node deployment journey today and be part of the ever-expanding world of web3 innovation.

Explore the [Spheron Guide](https://docs.spheron.network/) to start your journey toward hassle-free deployment and development.

## **Resources**

**Spheron Avail Node Guide:** [https://docs.spheron.network/marketplace-guide/avail/](https://docs.spheron.network/marketplace-guide/avail-full)

**Avail Node Documentation:** [https://docs.availproject.org/operate/node/docker/](https://docs.availproject.org/operate/node/docker/)