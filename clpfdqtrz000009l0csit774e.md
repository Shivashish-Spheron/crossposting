---
title: "Deploy MongoDB in Minutes using Spheron Compute"
seoTitle: "Deploy MongoDB in Minutes using Spheron Compute"
seoDescription: "Learn how to deploy MongoDB effortlessly in just a few minutes using Spheron Compute!"
datePublished: Sun Nov 26 2023 11:11:23 GMT+0000 (Coordinated Universal Time)
cuid: clpfdqtrz000009l0csit774e
slug: deploy-mongodb-in-minutes-using-spheron-compute
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1700993582450/97167b77-83df-43e8-ab05-474316452279.png
tags: mongodb, blockchain, web3, decentralization, spheron

---

%[https://youtu.be/UiGRVkjyYIs] 

MongoDB is a popular NoSQL database widely used for its flexibility, scalability, and ease of use. [MongoDB](https://www.mongodb.com/) is a fully managed cloud database service that makes deploying, managing, and scaling MongoDB databases easy. This guide will walk you through launching your first MongoDB instance using [Spheron Network](https://spheron.network/) and connecting it with MongoDB.

## What is Spheron Network?

[Spheron Network](https://spheron.network/) is a next-generation PaaS that offers low-cost and seamless access to Web3 infrastructure across multiple chains. It is explicitly designed to serve a broader audience, including startups, developers, and organizations looking to scale their infrastructure.

Spheron harnesses the power of blockchain technology to provide secure and scalable solutions, simplifying the hosting and deployment of dApps while reducing the learning curve. By combining IPFS storage, Filecoin, and Arweave, Spheron ensures a seamless yet affordable experience. In addition to web hosting, compute, and storage capabilities, Spheron offers many features to enhance productivity and enable stakeholders to reach new heights while prioritizing privacy, security, and reliability.

## What is Spheron Network Marketplace?

The Spheron Network [Marketplace](https://docs.spheron.network/marketplace-guide/) is a full-featured developer-focused platform designed for developers. It brings together a vast range of technologies under one umbrella, delivering an unmatched convenience to those crafting diverse digital solutions. It is designed to streamline the development and deployment of projects. It offers many technologies in one place, including popular databases, nodes, and tools. It also provides a competitive and flexible pricing structure, providing healthier options than its counterparts like AWS, GCP, and Azure pricing options, making it a cost-effective solution for developers and businesses.

## How to create a MongoDB instance?

You can follow these steps to Launch your first MongoDB instance using Spheron and connect it with MongoDB.

### Step 1: Creating a Spheron Network Account

1. Visit Spheron Network: [https://spheron.network/](https://spheron.network/)
    
2. On the Spheron homepage, locate and click the **"Free Trial"** button.
    
3. You'll be directed to a login/signup page. **Choose your preferred authentication method:** **GitHub account, GitLab account, or Bitbucket account.**
    
4. Follow the prompts to authenticate your account securely. This step ensures safe access to the platform.
    
5. After successful authentication, you'll be guided to a confirmation page indicating the completion of your account setup.
    

### Step 2: Create an Organization and Launch a MongoDB Instance using Spheron Marketplace

1. Upon logging in, you'll be directed to the Create Organization page, where you can give your organization a name and a username. Ensure the **"Compute"** option is selected from the drop-down menu at the top right corner.
    
2. You'll be taken to the Compute Dashboard. Click **"New Cluster"** on the top right corner.
    
3. Select the **"Start from marketplace app"** option. From the available marketplace apps, choose **MongoDB**.
    
4. **Scaling (Scale Hardware Resources):** Spheron gives you different options to consider for scaling computational resources allocated to an instance. This can help you match the needs of your application.
    
    * **Manual Scaling -** Resources can be manually scaled. You have the power to adjust the amount of hardware resources your application needs according to the requirements. Manual scaling is currently in alpha access. To access this feature, please follow the process outlined in the [documentation](https://docs.spheron.network/compute/scaling/manual/).
        
    * **Auto Scaling -**  This is like having an intelligent assistant that adapts to changes without you needing to intervene. Spheron automatically adjusts the hardware resources based on the demands of your application. This exciting feature is not yet live and is coming soon.
        
    * **No Scaling -** Resources can't be scaled after the deployment. **Currently, this option is available for the scaling section.**
        
5. **Regions:** Next, If you have selected **No Scaling**, Select your preferred region for deployment. The container will be deployed in **Any** by default. Choosing a region closer to your users can improve performance and reduce latency. Spheron offers the following regions to choose from:
    
    * US-east
        
    * US-west
        
    * US-central
        
    * EU-west
        
    * Any
        
        **Note:**
        
    * For **Manual Scaling** deployments, we only have **eu-east** region live right now.
        
    * It is recommended to select **Any** region for no scaling option to get higher chances of successful deployment as it will deploy on any providers in the network.
        
6. **Plans:** Next, Choose an instance plan that aligns with your requirements. Spheron Network will recommend a suitable plan according to the template, but you can customize it if needed from available plans or choose to **create custom plans**.
    
    **Note:** The pricing plans for the **manual scaling** option will be according to the selected regions, while the **no scaling option** will follow plans irrespective of regions
    
7. The next step is configuring storage: You have to choose **Ephemeral Storage** from the available options. Additionally, you get the option to choose **Persistent Storage**.
    
    * **Ephemeral storage** is called Volatile storage and is erased when the instance is restarted, redeployed, or shut down.
        
    * **Persistent storage** will not be erased unless the instance is closed. If choosing persistent storage, specify the **type of storage (HDD, SSD, NVMe) and Add the mount point as ‘data/db’**
        
8. Set up the Root Username and Root Password for the MongoDB instance.
    
    1. **Root Username** - The username used for accessing the MongoDB database.
        
    2. **Root Password** - Password associated with the MongoDB database user.
        
9. Review your instance configuration and click the **"Deploy"** button to initiate deployment.
    

**Note: Persistent Storage and Mount Point**

Persistent storage refers to a type of storage that retains data even after the associated application or system is restarted or updated. In the context of containerized applications like MongoDB instances, persistent storage plays a crucial role in preserving data integrity across various scenarios. Persistent storage will not be erased unless the instance is closed.

For example, **MongoDB mount point is** `/data/db`. In a containerized MongoDB setup, this path would represent the directory where MongoDB stores its database files, which are crucial for the operation of the database instance. By attaching persistent storage to this mount point, the data stored in this directory becomes immune to container updates, restarts, or crashes

### Step 3: Verification and Connecting to MongoDB

It's important to note that access to MongoDB is only possible after the Compute Instance setup is fully provisioned. You'll need to wait for the installation to complete before utilizing it.

### Step 4: Connecting to MongoDB using Connection String URI

To connect to MongoDB, you can use [MongoDB Compass](https://www.mongodb.com/products/compass), launch the application on your computer, and click **"New Connection"** on the initial screen. In the **"New Connection"** window, input your MongoDB connection URI into the labeled **"Connection String"** field.

Next, click **"Connect,"** prompting MongoDB Compass to endeavor a connection to the cluster through the provided URI. Upon successful connection, you can seamlessly explore and interact with your MongoDB data within the Compass interface.

MongoDB can be accessed using a connection string URI, which follows this standard format:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693026933999/1ecfbe42-d407-46e7-abe1-9735aef7b612.png align="center")

The parts in square brackets indicate optional parts. You may have noticed that most parts of the URI are optional. It might also be apparent that you can encode many pieces of information in the URI.

* `mongodb://` **\-** A required prefix to identify that this is a string in the standard connection format.
    
* `username: password` **(optional)** - Authentication credentials passed in App Configuration. The client will attempt to authenticate the user to the authSource if specified.
    
* `host[: port]` - The host and port number where the MongoDB instance is running. Use the Connection URL provided by Spheron under Port Policy Info.
    
* `/database` **(optional)** - The authentication database to use if the connection string includes username: password authentication credentials, but the `authSource` option is unspecified. If both `authSource` and default `authdb` are unspecified, the client will attempt to authenticate the specified user to the admin database.
    
* `?options` **(optional)** - An optional list of additional parameters that can affect the connection behavior. The parameter list is composed of key-value pairs. The key and value within each pair are separated by an equal sign (=), and each pair is separated from the next by an ampersand (&). The parameter list begins with a question mark (?). If no default authentication database is provided, you must begin the parameter list with the slash and question mark (/?) after the last host definition.
    

## Benefits of Spheron Marketplace

1. **Convenient Deployment:** Spheron Network Marketplace offers a full suite of services to help users build and easily deploy their projects. This means users can deploy their projects quickly and easily without worrying about complex deployment processes.
    
2. **All in One Solution -** The Spheron Network Marketplace offers a comprehensive platform for developers and businesses, providing a wide array of technologies in one place. This includes support for popular databases like Redis, MongoDB, MySQL, and PostgreSQL, over 14 popular nodes such as IPFS, Arbitrum, and Filecoin, and tools like Jupyter Notebook and Grafana. This global reach opens up new opportunities for businesses to expand their customer base and increase their market presence by leveraging diverse technologies from a single platform.
    
3. **Effortless Organization Management:** Users can create one or more organization accounts using the Spheron Network. All their projects will be grouped under this organization. These accounts represent a collection of people who share ownership of projects, and there are various ways to manage different groups within these individuals. The organization owner can invite members to join their organization by providing the person's Email ID.
    
4. **Competitive pricing:** The Spheron Network Marketplace fosters better pricing than AWS, GCP, and Azure, ultimately benefiting buyers. Buyers have many affordable choices for what they need. There are 10+ or more ready-made pricing options; if buyers want, they can make their custom plan. This helps buyers, leading to better deals and more cost-effective solutions.
    

## Conclusion

Spheron Network platform is an excellent choice for MongoDB because it offers an easy and affordable way to set up, manage, and use MongoDB databases. With Spheron, you can quickly create your MongoDB instance through a user-friendly interface and connect it securely to the cloud.

The Spheron platform's combination of blockchain technology and various advanced tools makes hosting and deploying your databases simple, even if you're new to this technology. Plus, Spheron's marketplace provides a wide range of technologies, saving you time and effort by offering everything you need in one place.

So, if you're looking for a convenient and efficient solution to work with MongoDB, Spheron Network is a top-notch option.

## Resources

1. Spheron Marketplace Guide: [https://docs.spheron.network/marketplace-guide/mongodb/](https://docs.spheron.network/marketplace-guide/mongodb/)
    
2. MongoDB Docs:[https://www.mongodb.com/docs/manual/reference/connection-string/](https://www.mongodb.com/docs/manual/reference/connection-string/)
    
3. MongoDB Compass: [https://www.mongodb.com/docs/compass/current/](https://www.mongodb.com/docs/compass/current/)