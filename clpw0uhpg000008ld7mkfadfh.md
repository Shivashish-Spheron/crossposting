---
title: "Deploy a PostgreSQL database in Minutes using Spheron Compute"
seoTitle: "Deploy a PostgreSQL database in Minutes using Spheron Compute"
seoDescription: "Deploy a PostgreSQL database in minutes using Spheron Compute. Spheron Compute offers a user-friendly platform to deploy a PostgreSQL database."
datePublished: Fri Dec 08 2023 02:42:24 GMT+0000 (Coordinated Universal Time)
cuid: clpw0uhpg000008ld7mkfadfh
slug: deploy-a-postgresql-database-in-minutes-using-spheron-compute
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1701978495920/e3c911fa-658f-48ee-80f9-d41646868d0f.png
tags: postgresql, deployment, blockchain, web3, spheron

---

%[https://youtu.be/6zKjyOFzafY] 

When setting up a [PostgreSQL](https://www.postgresql.org/) database for your web application or project, the last thing you want is to spend hours configuring and fine-tuning the database. Fortunately, deploying a PostgreSQL database can be a quick and painless process if you use the right tools. In this blog post, we'll walk you through the steps to deploy a PostgreSQL database within minutes using Spheron Compute. Spheron Compute offers an effortless and straightforward way to get your database up and running on the Akash Network. So, let's get started!

# **What is Spheron Network?**

[Spheron Network](https://spheron.network/) is a next-generation PaaS that offers low-cost and seamless access to Web3 infrastructure across multiple chains. It is explicitly designed to serve a broader audience, including startups, developers, and organizations looking to scale their infrastructure.

Spheron Network offers a [Compute Marketplace](https://docs.spheron.network/marketplace-guide/) that you can use to set up useful tools like PostgreSQL quickly. With Spheron, you don't have to worry about the technical stuff and you can focus on deploying a PostgreSQL database with ease. In addition to compute, web hosting, and storage capabilities, Spheron offers many features to enhance productivity and enable stakeholders to reach new heights while prioritizing privacy, security, and reliability.

# **How do you deploy a PostgreSQL database using Spheron Compute?**

You can follow these steps to deploy a PostgreSQL database on Spheron Compute.

## **Step 1: Create a Free Spheron Network Account**

1. Visit Spheron Network: [https://spheron.network/](https://docs.spheron.network/)
    
2. On the Spheron homepage, locate and click the **"Free Trial"** button.
    
3. You'll be directed to a login/signup page. Choose your preferred authentication method: Web2 (GitHub account, GitLab account, or Bitbucket account) or Web3 (Ethereum).
    
4. Follow the provided prompts to authenticate your chosen account securely. This step ensures safe access to the Spheron Network platform.
    
5. After successful authentication, you'll be guided to a confirmation page confirming the completion of your account setup.
    

## **Step 2: Creating an Organization**

1. Upon logging in, navigate to the **"Compute"** section using the dropdown on the top right corner.
    
2. You'll be prompted to create your organization's name, username, and Avatar. Add and click **“Save.”**
    
3. Next, you'll be taken to a new page. Click the **"New Cluster"** button.
    

## **Step 3: Deploying a PostgreSQL database With Spheron Platform UI**

Follow these steps to deploy a PostgreSQL database:

1. Choose "Compute" to use CPU-based instances for running containers.
    
2. Choose the computer you need from the options under **"Compute Type."** You can pick the one that suits your requirements.
    

**NOTE:** Please schedule a team call to gain early access to the On Demand Type.

3.Select **"Start from Marketplace App"**.

4.Pick **"Postgres"** from the marketplace. It's as easy as choosing an app you want to install.

5.Select your preferred region for deployment. The container will be deployed in any region for Spot or the EU-east region for On Demand. Choosing a region closer to your users can improve performance and reduce latency. Spheron offers the following regions to choose from for Spot:

* US-east
    
* US-west
    
* US-central
    
* EU-west
    
* Any
    

**NOTE:** It is recommended to select any region for Spot to get a higher chance of successful deployment, as it will deploy on any providers in the network.

6.Next, Choose an instance plan that aligns with your requirements. Spheron will recommend a suitable plan according to the IPFS template, but you can customize it if needed from available plans or choose to **'Create Custom Plans.'**

7.Next, Configure storage:  
You have to choose Storage from the available options. This storage will be volatile storage and is erased when the instance is restarted, redeployed, or shut down.

Additionally, you get the option to choose Persistent Storage. Persistent storage will not be erased unless the instance is closed. If choosing persistent storage, specify the type of storage (HDD, SSD, NVMe) and Add mount point.

8.For advanced configurations, feel free to explore more options. Just [click here](https://docs.spheron.network/compute/cluster/#advance-configuration-1) to learn more about these advanced settings.

9.Once you're all set, click "Deploy" to start the deployment process. It's as simple as that!

That's it! Your PostgreSQL database instance will now be deployed.

**NOTE:** Keep in mind that you can access the PostgreSQL database only after the Compute Instance is provisioned. So, allow some time for the installation to complete before you can start using it.

## **Connecting to the PostgreSQL database**

* You can run the following command in your terminal to connect to your PostgreSQL server: ***psql postgresql://\[username:password@\]host\[:port\]\[/dbname\]***
    

# **Benefits of Deploying a PostgreSQL database with Spheron Compute**

Deploying a PostgreSQL database with Spheron Compute offers many benefits, including:

1. **Simplicity and Speed:** Spheron Compute's user-friendly interface and streamlined deployment process make it easy for both beginners and experienced users to set up PostgreSQL quickly. You can save valuable time that would otherwise be spent on server provisioning and configuration.
    
2. **Cost-Efficiency:** Spheron Compute provides cost-effective solutions, ensuring you get the most out of your resources. You can choose the plan that aligns with your budget and scale as needed without breaking the bank.
    
3. **Reliability and Performance:** Spheron's infrastructure is designed for stability and high performance. Your PostgreSQL instance will run smoothly, ensuring you have access to your data when you need it, without interruptions.
    
4. **Flexibility:** With a variety of instance plans and the ability to create custom plans, you can tailor your deployment to meet your specific requirements. This flexibility allows you to optimize your resources for the best performance.
    
5. **Persistent Storage:** Spheron Compute offers the option to add persistent storage, ensuring your data is safe and accessible even if the instance is updated or replaced.
    
6. **Scalability:** Whether you're starting small or planning for growth, Spheron Compute allows you to scale your PostgreSQL deployment easily. You can handle increasing data volumes and growing user demands effortlessly.
    
7. **Support and documentation:** Spheron provides comprehensive documentation and support, helping you navigate any challenges you may face during deployment and development.
    

# **Conclusion**

Deploying a PostgreSQL database can be a complex task, but with Spheron Compute, it becomes a breeze. Following the steps outlined in this guide, you can have your PostgreSQL database ready for action in just a few minutes. This streamlined process saves you time and effort, allowing you to focus on utilizing your database for your applications and projects.

Explore the [Spheron Guide](https://docs.spheron.network/) to start your journey toward hassle-free deployment and development.

# **Resources**

**Spheron PostgreSQL Guide:** [https://docs.spheron.network/marketplace-guide/postgresql/](https://docs.spheron.network/)

**PostgreSQL Documentation:** [https://www.postgresql.org/docs/current/app-psql.html](https://docs.spheron.network/)