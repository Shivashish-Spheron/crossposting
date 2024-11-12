---
title: "Streamline Your Web Development Workflow with Spheron Site Deployer"
seoTitle: "Streamline Your Web Development Workflow with Spheron Site Deployer"
seoDescription: "Explore the Spheron Site Deployer Service a solution merging blockchain technology with web development for decentralized and secure front-end deployment"
datePublished: Sat Dec 02 2023 04:31:09 GMT+0000 (Coordinated Universal Time)
cuid: clpnk389x000509l94xyccwjl
slug: streamline-your-web-development-workflow-with-spheron-site-deployer
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1701200094972/bad0c287-e7c8-43ea-b85b-05c0c75bcbe3.png
tags: blockchain, push-notifications, web3, decentralization, spheron

---

As the world moves towards a more decentralized future, blockchain technology has become increasingly popular in various industries, and innovation knows no bounds. One area where blockchain can significantly impact is web development, particularly in the deployment of front-end applications. Traditional methods rely on centralized servers, posing security risks and compromising the principles of decentralization. **To address this issue, we present a use case called** [**"Spheron Site Deployer Service"**](https://github.com/spheronFdn/spheron-site-deployer-service)**, an automated blockchain-driven deployment service that utilizes Spheron and PushAPI for secure and decentralized frontend delivery.**

In the realm of decentralized applications, Spheron has emerged as a powerful tool for automated, blockchain-driven deployments. In this article, we will explore the Spheron Site Deployer Service, its purpose, and how to use it effectively.

## Spheron Network

[Spheron Network](https://spheron.network/) is a PaaS designed for startups, optimizing scalability and minimizing infrastructural costs to boost growth and profitability. Spheron simplifies the web hosting process, making it easy for developers to deploy their applications in just a matter of minutes. Spheron offers a suite of services that support blockchain applications, including hosting, storage, and computing services.

With Spheron's user-friendly interface and robust infrastructure, users can focus on developing great apps and dapps without worrying about the hassle of setting up and managing servers. Spheron Network takes care of the technical details so developers can concentrate on what matters most - creating innovative and successful web applications.

## What is Push SDK?

The [Push SDK](https://docs.push.org/developers/developer-tooling/push-sdk) is a collection of tools that make it easier for developers to use the Push protocol in their frontend applications. This collection, stored in a single repository (called a Monorepo), offers various packages to help with different tasks during app development.

It's made specifically in JavaScript and is beneficial for both the front-end (what users see) and the back-end (how the app functions behind the scenes). Here's what it helps developers do:

* **Sending Notifications:** Easily send messages or notifications.
    
* **Subscribing and Unsubscribing:** Allow users to choose whether they want to receive notifications or not.
    
* **Integrating Push Features:** Seamlessly include Push protocol features into decentralized applications (dApps).
    
* **Accessing Push Nodes APIs:** Utilize different functionalities provided by Push Nodes (part of the Push protocol).
    
* **Creating Default Notifications Interface:** Offer a basic setup for displaying notifications to users.
    

## What is the Spheron Site Deployer Service?

The [**Spheron Site Deployer Service**](https://github.com/spheronFdn/spheron-site-deployer-service) is designed to automate the deployment of frontend applications to decentralized storage using Spheron based on blockchain events. But what makes it truly unique is its ability to trigger deployments through on-chain events or governance proposals within a DAO, creating a seamless and decentralized Continuous Integration/Continuous Deployment (CI/CD) pipeline.

The service utilizes the local environmental configurations to initialize blockchain interaction tools securely and leverages PushAPI to listen for specific on-chain events. When triggered, it deploys web applications to [IPFS (InterPlanetary File System)](https://ipfs.tech/), [Filecoin](https://filecoin.io/), and [Arweave](https://www.arweave.org/) ensuring efficient and secure automation within the local infrastructure.

## How Does it Work?

The **Spheron Site Deployer Service** leverages local environmental configurations to initialize blockchain interaction tools securely. It uses PushAPI to listen for specific on-chain events and triggers a Spheron-based deployment of your web applications to IPFS, Arweave, or FIlecoin when those events occur. The deployment leverages only relevant environmental variables, ensuring efficient and secure automation within the local infrastructure.

## Why is It Built? Why Use Spheron Site Deployer Service?

The Spheron team developed this service with a clear vision in mind. Here are some of the key reasons we built the Spheron Site Deployer Service:

### 1\. Deploy Frontends Based on DAO Governance Proposals

[Decentralized Autonomous Organizations (DAOs)](https://en.wikipedia.org/wiki/Decentralized_autonomous_organization) are becoming increasingly popular for making collective decisions in a transparent and decentralized manner. With the Spheron Site Deployer Service, front-end applications can be automatically deployed based on DAO governance proposals, ensuring that the community's decisions are swiftly implemented.

### 2\. Automatic Deployments on Blockchain Events

Blockchain events like reward halving or changes in smart contracts are crucial in the world of cryptocurrencies and decentralized apps. There's a service that automatically sets up front-end applications when specific blockchain events happen. However, this only works if the smart contracts have a push interface. If not, this service won't function. This helps developers adapt swiftly to changes in their app needs.

This automation cuts down on the time and work needed for manual deployment. It also guarantees that the front-end stays updated with the newest blockchain events or decisions made in governance.

## Use Case

Let's consider a scenario where a developer wants to deploy their frontend application, MyWebApp, to Spheron. They want the deployment process to be automatic, decentralized, and secure. Here's how they can achieve this using the Spheron Site Deployer Service:

### Step 1: Set up the Spheron Site Deployer Service

* Clone the repo: [https://github.com/spheronFdn/spheron-site-deployer-service.git](https://github.com/spheronFdn/spheron-site-deployer-service.git)
    
* Go inside the project directory and install dependencies:
    

### Step 2: Configure the Deployment Settings

Configures the deployment settings in the .env file, specifying the Ethereum private key, channel address, Spheron access token, project name, and custom environment variables. Also, you need to specify the Git repository URL containing the frontend code that you want to deploy.

```javascript
# 🔑 Ethereum Private Key for signing transactions and data
PRIVATE_KEY=xxxx

# 📡 Channel Address for listening to notifications
LISTEN_TO_CHANNEL=xxxx

# 🔧 Spheron Access Token for authentication and access to Spheron services
SPHERON_ACESS_TOKEN=xxxx

# 🌐 GitHub URL for the project repository
PROJECT_GITHUB_URL=xxxx

# 📛 Name of the project
PROJECT_NAME=Spheron-Site-Deployer

# 🌐 Custom Environment Variables for the Web Application
ENV_VAR1=xxxx
ENV_VAR2=xxxx
ENV_VAR3=xxxx
```

### Step 3: Create a Free Spheron Network Account

1. Visit Spheron Network: [https://spheron.network/](https://github.com/spheronFdn/spheron-site-deployer-service.git).
    
2. On the Spheron homepage, locate and click the **"Free Trial"** button.
    
3. You'll be directed to a login/signup page. Choose your preferred authentication method: GitHub account, GitLab account, or Bitbucket account.
    
4. Follow the prompts to authenticate your account securely. This step ensures safe access to the Spheron Network platform.
    
5. After successful authentication, you'll be guided to a confirmation page confirming the completion of your account setup.
    

### Step 4: Create an Access Token

Access Tokens can be created and managed from inside your account settings.

1. Go to your profile icon in your Spheron dashboard app and click on it.
    
2. Click on **settings** from the image above to go to your settings page and navigate to the Tokens in your Account Settings.
    
3. Click **Create** to open a new Access Token.
    
4. Enter a descriptive name choose the scope from the list of Organizations in the drop-down menu select an expiration date for the token, and click Create Token.
    

The scope ensures that only your specified Organization can use an Access Token. Once you've created an Access Token, securely store the value, as it will not be shown again.

### Step 5: Learn about deployments from the [Spheron site SDK docs](https://docs.spheron.network/sdk/site/).

The Site SDK is a npm package that provides support for working with Spheron Site organizations.

### Step 6: Add domain configurations post-deployment or automate them using the SDK. Reference: [Spheron domain documentation](https://docs.spheron.network/static/projects/domain/).

By default, Spheron provides a subdomain when a project is deployed. **E.g.,** [**subdomain.spheron.app**](https://github.com/spheronFdn/spheron-site-deployer-service.git) You can point your domain either to an environment or a particular deployment from an environment.

### Step 7: Start the server

Finally, run the server using the command `node main.js`. You now have a local server that listens for Push protocol notifications to trigger web app deployments on decentralized storage via Spheron.

## Why Run a Local Server?

Running a local server for the Spheron Site Deployer Service is critical for two main reasons:

### 1\. Security

Your private key, which grants you full control over your blockchain assets, remains confidential and secure on your local machine. Cloud servers can pose risks of unauthorized access, breaches, and insufficient encryption, potentially compromising the security of your private key.

### 2\. Decentralization

In alignment with the Web3 ethos, maintaining your keys locally promotes a decentralized architecture, reducing reliance on centralized cloud services. This enhances trustlessness and resilience in your operational model, aligning with the core principles of blockchain technology.

## Conclusion

In conclusion, Spheron's Site Deployer Service offers a great approach to web application deployment by leveraging the power of blockchain technology. By utilizing a local server and avoiding centralized clouds, this service prioritizes security and decentralization, aligning with the core values of Web3.

We hope this blog has provided valuable insights into the Spheron Site Deployer Service and its potential to transform web application development. Whether you're a seasoned developer or just starting out, this tool offers exciting possibilities for streamlining your workflow and enhancing the security of your projects.

For help, discussions, or any other queries, you can [join the Spheron community](https://community.spheron.network/). Our active community is a great place to learn more about the Spheron Site Deployer Service, ask questions, and share your experiences.

## References

* [Spheron Site SDK Guide](https://docs.spheron.network/sdk/site/)
    
* [PUSH Docs for receiving notifications](https://push.org/docs/notifications/build/stream-notifications/)
    
* [Github Repository for Use Case](https://github.com/spheronFdn/spheron-site-deployer-service)