---
title: "Deploy Redis in Minutes using Spheron Compute"
seoTitle: "Deploy Redis in Minutes using Spheron Compute"
seoDescription: "Learn step-by-step how to deploy your Redis deployment in minutes with Spheron Compute - Simplify the process effortlessly."
datePublished: Tue Nov 28 2023 04:45:10 GMT+0000 (Coordinated Universal Time)
cuid: clphutuch000608l52sja3lxg
slug: deploy-redis-in-minutes-using-spheron-compute
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1701001928047/89009074-1393-473e-ad5b-c6764dd537d1.png
tags: reactjs, blockchain, web3, decentralization, spheron

---

%[https://youtu.be/4sFsbVnFq48] 

[Redis](https://redis.io/), a high-performance, open-source, in-memory data store, is an essential component for many modern applications. Whether you need to cache data, manage session information, or support real-time analytics, Redis can deliver outstanding performance.

If you're looking to deploy Redis quickly and effortlessly, Spheron Compute has you covered. In this guide, we will walk you through the simple steps to deploy Redis within minutes using Spheron.

# **What is Spheron Network?**

[Spheron Network](https://spheron.network/) is a next-generation PaaS that offers low-cost and seamless access to Web3 infrastructure across multiple chains. It is explicitly designed to serve a broader audience, including startups, developers, and organizations looking to scale their infrastructure.

Spheron Network offers a [Compute Marketplace](https://docs.spheron.network/marketplace-guide/) that you can use to quickly set up useful tools like Redis. With Spheron, you don't have to worry about the technical stuff and you can focus on deploying Redis with ease. In addition to compute, web hosting, and storage capabilities, Spheron offers many features to enhance productivity and enable stakeholders to reach new heights while prioritizing privacy, security, and reliability.

## **How to deploy Redis using Spheron Compute?**

You can follow these steps to deploy Redis on Spheron Compute.

### **Step 1: Create a Free Spheron Network Account**

1. Visit Spheron Network: [https://spheron.network/](https://docs.spheron.network/)
    
2. On the Spheron homepage, locate and click the "Free Trial" button.
    
3. You'll be redirected to a login/signup page. Choose your preferred authentication method: Web2 (GitHub account, GitLab account, or Bitbucket account) or Web3 (Ethereum).
    
4. Follow the provided prompts to authenticate your chosen account securely. This step ensures safe access to the Spheron Network platform.
    
5. After successful authentication, you'll be guided to a confirmation page confirming the completion of your account setup.
    

### **Step 2: Creating an Organization**

1. Upon logging in, navigate to the "Compute" section using the dropdown on the top right corner.
    
2. You'll be prompted to create your organization's name, username, and Avatar. Add and click “Save”.
    
3. Next, you'll be taken to a new page. Click the "New Cluster" button.
    

### **Step 3: Deploying Redis With Spheron Platform UI**

Follow these steps to deploy Redis:

1. Choose "Compute" to use CPU-based instances for running containers.
    
2. Choose the type of compute you need from the options under "Compute Type." You can pick the one that suits your requirements.
    

**NOTE:** Please schedule a team call to gain early access to the On Demand Type.

1. Select "Start from Marketplace App".
    
2. Pick "Redis" from the marketplace. It's as easy as choosing an app you want to install.
    
3. Select your preferred region for deployment. The container will be deployed in any region for Spot, or in the EU-east region for On Demand. Choosing a region closer to your users can improve performance and reduce latency. Spheron offers the following regions to choose from for Spot:
    
    * US-east
        
    * US-west
        
    * US-central
        
    * EU-west
        
    * Any
        

**NOTE:** It is recommended to select any region for Spot to get a higher chance of successful deployment as it will deploy on any providers in the network.

1. Next, Choose an instance plan that aligns with your requirements. Spheron will recommend a suitable plan according to the IPFS template, but you can customize it if needed from available plans or choose to 'Create Custom Plans'
    
2. Next, Configure storage:  
    You have to choose Storage from the available options. This storage will be volatile storage and is erased when the instance is restarted, redeployed, or shut down.
    
    Additionally, you get the option to choose Persistent Storage. Persistent storage will not be erased unless the instance is closed. If choosing persistent storage, specify the type of storage (HDD, SSD, NVMe) and Add mount point.
    
3. For advanced configurations, feel free to explore more options. Just [click here](https://docs.spheron.network/compute/cluster/#advance-configuration-1) to learn more about these advanced settings.
    
4. Once you're all set, click "Deploy" to start the deployment process. It's as simple as that!
    

That's it! Your Redis instance will now be deployed.

**NOTE:** Keep in mind that you can access Redis only after the Compute Instance is provisioned. So, allow some time for the installation to complete before you can start using it.

### **Connecting to Redis**

* You can use the connection string URI to connect to Redis. The standard URI connection scheme has the following format:
    
    ```javascript
    redis://[password@]host[:port]
    ```
    
* Run the following command in your terminal to test your connection:
    
    ```javascript
    redis-cli -u redis://[password@]host[:port] PING
    ```
    

## **Benefits of Deploying Redis with Spheron Compute**

Deploying Redis with Spheron Compute offers many benefits, including:

1. **Simplicity and Speed:** Spheron Compute's user-friendly interface and streamlined deployment process make it easy for both beginners and experienced users to set up Redis quickly. You can save valuable time that would otherwise be spent on server provisioning and configuration.
    
2. **Cost-Efficiency:** Spheron Compute provides cost-effective solutions, ensuring you get the most out of your resources. You can choose the plan that aligns with your budget and scale as needed without breaking the bank.
    
3. **Reliability and Performance:** Spheron's infrastructure is designed for stability and high performance. Your Redis instance will run smoothly, ensuring you have access to your data when you need it, without interruptions.
    
4. **Flexibility:** With a variety of instance plans and the ability to create custom plans, you can tailor your deployment to meet your specific requirements. This flexibility allows you to optimize your resources for the best performance.
    
5. **Persistent Storage:** Spheron Compute offers the option to add persistent storage, ensuring your data is safe and accessible even if the instance is updated or replaced.
    
6. **Scalability:** Whether you're starting small or planning for growth, Spheron Compute allows you to scale your Redis deployment with ease. You can handle increasing data volumes and growing user demands effortlessly.
    
7. **Support and documentation:** Spheron provides comprehensive documentation and support, helping you navigate any challenges you may face during deployment and development.
    

## **Conclusion**

In conclusion, deploying Redis within minutes with Spheron Compute offers a seamless and efficient solution for those looking to harness the power of this high-performance in-memory data store. Spheron's user-friendly platform simplifies the deployment process, allowing you to customize your instance, choose your preferred configuration, and access your Redis database in no time.

Explore the [Spheron Guide](https://docs.spheron.network/) to start your journey toward hassle-free deployment and development.

## **Resources**

**Spheron Redis Guide:** [https://docs.spheron.network/marketplace-guide/redis/](https://docs.spheron.network/)

**Redis Documentation:** [https://redis.io/docs/ui/cli/](https://docs.spheron.network/)