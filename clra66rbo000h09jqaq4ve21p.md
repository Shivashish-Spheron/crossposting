---
title: "Deploying Cloud Instances Made Easy: Explore the Compute Deployer Telegram Bot"
seoTitle: "Deploying Instances Easy: Explore the Compute Deployer Telegram Bot"
seoDescription: "Explore the Spheron Compute Deployer Telegram Bot, a revolutionary tool that simplifies the deployment of compute instances on the Spheron Compute platform."
datePublished: Sun Jan 28 2024 18:30:00 GMT+0000 (Coordinated Universal Time)
cuid: clra66rbo000h09jqaq4ve21p
slug: deploying-cloud-instances-made-easy-explore-the-compute-deployer-telegram-bot
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1704317372768/fd7fa202-416b-4448-9e32-4330777e2d09.png
tags: bot, deployment, deployment-automation, blockchain, telegram, web3, compute, telegram-bot, spheron

---

Cloud computing has opened numerous doors for both businesses and individuals. However, setting up computing resources can be a challenging and time-consuming task amidst the rising demand for scalable options. Spheron has come up with a solution - the Compute Deployer Telegram Bot. This tool streamlines the deployment of compute instances on their platform, making it simpler, safer, and more efficient.

As the world embraces decentralized cloud solutions, the Compute Deployer Telegram Bot marks a significant stride. This article aims to offer a step-by-step guide on effectively utilizing this service. Whether you're new to compute or an experienced developer, this article strives to equip you with the necessary knowledge to leverage Compute Deployer Telegram Bot.

## Spheron Network

Spheron Network is a PaaS designed for startups, optimizing scalability and minimizing infrastructural costs to boost growth and profitability. Spheron simplifies the compute deployment process, making it easy for developers to deploy their compute instances in just a matter of minutes. Spheron offers a suite of services that support blockchain applications, including computing services and storage.

With Spheron's user-friendly interface and robust infrastructure, users can focus on developing great apps and dapps without worrying about the hassle of setting up and managing servers. Spheron Network takes care of the technical details so developers can concentrate on what matters most - creating innovative and successful web applications.

## What is the Spheron Compute Deployer Telegram Bot?

The Spheron Compute Deployer Telegram Bot represents a revolutionary step in simplifying the deployment of compute instances on the Spheron Compute platform. Positioned at the intersection of user-friendliness and efficiency, this bot enables users to deploy compute resources seamlessly through the familiar interface of Telegram commands. This user-centric approach signifies a paradigm shift in cloud deployment, making it accessible and straightforward for novices and seasoned users.

At its core, the Spheron Compute Deployer Telegram Bot is a self-hosted server that establishes a robust connection with the Telegram bot created through BotFather. Users can initiate the deployment of compute instances with ease by issuing simple commands on Telegram. It seamlessly integrates with Spheron Compute APIs, facilitating deployment and fetching essential information to ensure a smooth and efficient user experience. The Spheron Compute Deployer Telegram Bot is about making cloud deployment a breeze, with no complications, just simple and efficient computing.

## Why did we build this?

We built the Spheron Compute Deployer Telegram Bot with a simple goal in mind – to make deploying compute instances on Spheron Compute easy and accessible for everyone. In the world of tech, things can get complicated, and we wanted to simplify the process, cutting through the jargon and intricate steps. Whether you're a tech whiz or just dipping your toes into cloud computing, we believe setting up your compute resources should be as straightforward as possible.

1. **Streamlined Deployment:** Simplify the process of deploying compute instances on Spheron Compute by leveraging the convenience of a Telegram bot interface.
    
2. **User-Friendly:** Create an intuitive and user-friendly experience for deploying compute instances, making it accessible to both beginners and experienced users.
    

## How to use it?

### Step 1: Set up the Compute Deployer Telegram Bot

* Clone the repo: [https://github.com/spheronFdn/compute-deployer-telegram-bot/tree/main](https://blog.devgenius.io/how-to-set-up-your-telegram-bot-using-botfather-fd1896d68c02)
    
* Then, go inside the project directory and run **npm install** to install dependencies.
    

### Step 2: Set up a Bot on Telegram

* Search @BotFatheron on Telegram and send **/start** or **/help** in the chat with BotFather.
    
* Follow [this guide](https://blog.devgenius.io/how-to-set-up-your-telegram-bot-using-botfather-fd1896d68c02) for a step-by-step process on how to set up the telegram bot.
    

### Step 3: Create an Access Token

Access Tokens can be created and managed from inside your account settings.

1\. Go to your profile icon in your Spheron dashboard app and click on it.

2\. Click on settings from the image above to go to your settings page and navigate to the Tokens in your Account Settings.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706502397289/69139a5f-5f16-43e7-af79-9ca3b536d8d8.png align="center")

3\. Click Create to open a new Access Token.

4\. Enter a descriptive name, choose the scope from the list of Organizations in the drop-down menu, select an expiration date for the token, and click Create Token.

The scope ensures that only your specified Organization can use an Access Token. Once you've created an Access Token, securely store the value, as it will not be shown again.

### Step 4: Configure the Deployment Settings

* You have to create a .env file in the client directory and add the bot token and the Spheron access token:
    
* You can follow the steps [here](https://docs.spheron.network/rest-api/#creating-an-access-token), to learn about how to create an access token on Spheron.
    

```dockerfile
# The port on which the Spheron Notification Service will run
PORT=xxxx

# Bot token for authorization
BOT_TOKEN=xxxx

# Spheron access token
SPHERON_ACCESS_TOKEN=xxxx
```

### Step 5: Create a Free Spheron Network Account

1. Visit Spheron Network: [https://spheron.network/](https://blog.devgenius.io/how-to-set-up-your-telegram-bot-using-botfather-fd1896d68c02).
    
2. On the Spheron homepage, locate and click the "Free Trial" button.
    
3. You'll be directed to a login/signup page. Choose your preferred authentication method: GitHub account, GitLab account, or Bitbucket account.
    
4. Follow the prompts to authenticate your account securely. This step ensures safe access to the Spheron Network platform. After successful authentication, you'll be guided to a confirmation page confirming the completion of your account setup.
    

## Deploying the Compute Deployer Telegram Bot on Spheron

### **Step 1: Set Default Platform for Docker Build**

**Note:** This step is necessary only for ARM-based processors. If you have other systems, you can skip this step.

Docker images built with Apple Silicon (or another ARM64-based architecture) can create issues when deploying the images to a Linux or Windows-based AMD64 environment. Before running the docker build command, run this command in your terminal:

```javascript
export DOCKER_DEFAULT_PLATFORM=linux/amd64
```

### **Step 2: Build and Run the Docker Image**

To build the docker image

1. Save the Dockerfile in the root directory of your compute deployer bot.
    
2. Open a terminal and navigate to your project's root directory.
    
3. Build the Docker image:
    

```javascript
docker build -t compute-deployer-bot
```

4\. Run a container based on the built image to test if everything is working properly:

```javascript
docker run -p 3000:3000 compute-deployer-bot
```

### **Step 3: Push the App to Docker Hub**

1. Create a repository on Docker Hub with the name `compute-deployer-bot`.
    
2. Log in to Docker Hub using:
    

```javascript
docker login -u YOUR-USER-NAME
```

3\. Tag the image:

```javascript
docker tag compute-deployer-bot  YOUR-USER-NAME/compute-deployer-bot
```

4\. Push the image to Docker Hub:

```javascript
docker push YOUR-USER-NAME/compute-deployer-bot
```

### **Step 4: Deploy on Spheron Compute**

1. Go to the Spheron platform, navigate the Spheron Compute dashboard, and click **"Compute."**
    
2. **Compute Type (Scale Hardware Resources):** Choose the compute you need from the options under "Compute Type." You can pick the one that suits your requirements.
    
    **NOTE:** Please schedule a team call to gain early access to the On Demand Type.
    
3. Select **"Import from Docker Registry,"** provide the following information, and click **Next**.
    
    * Cluster name
        
    * Docker image and tags
        
4. **Regions:** Next, If you have selected **No Scaling**, Select your preferred region for deployment. The container will be deployed in **Any** by default. Choosing a region closer to your users can improve performance and reduce latency. Spheron offers the following regions to choose from:
    
    * Us-east
        
    * Us-west
        
    * Us-central
        
    * Eu-west
        
    * Any
        
5. **Plans:** Next, Choose an instance plan that aligns with your requirements. Spheron Network will recommend a suitable plan according to the template, but you can customize it if needed from available plans or choose to **create custom plans**.
    
    **Note:** The pricing plans for the **manual scaling** option will be according to the selected regions, while the **no scaling option** will follow plans irrespective of regions.
    
6. Next, Configure storage: You have to choose **Ephemeral Storage** from the available options. Additionally, you get the option to choose **Persistent Storage**.
    
    * **Ephemeral storage** is called Volatile storage and is erased when the instance is restarted, redeployed, or shut down.
        
    * **Persistent storage** will not be erased unless the instance is closed. If choosing persistent storage, **specify the type of storage (HDD, SSD, NVMe) and Add mount point.**
        
7. You can add Additional Configuration, such as.
    
    * Choose a port policy mapping and specify the container and exposed ports (Choose from 80 or a random port). This is mandatory.
        
    * Set environment variables and secret environment variables if needed.
        
    * You can Add any Advanced configuration, such as specifying **commands and arguments.**
        
    * You can set up a **health checkup with a health check path and port.** Enabling a health check is crucial for various reasons, especially to ensure your service's smooth operation and availability. By setting up a health check, you will regularly receive email notifications if it goes down for any reason.
        
8. Review your settings and configurations. Click **"Deploy"** to initiate deployment.
    

### **Verification and Troubleshooting**

1. Wait for the instance to provision and access the app using the connection URL.
    
2. Check instance logs and events for any issues or errors.
    
3. Once the bot is up and running, you can enter **/start** in your telegram bot channel to get started.
    

## Conclusion

In conclusion, the Spheron Compute Deployer Telegram Bot is a testament to our commitment to simplifying and democratizing cloud deployment. We built this tool with the vision of providing a user-friendly gateway to the powerful capabilities of Spheron Compute. By streamlining the deployment process through the familiar interface of Telegram commands, we aimed to eliminate complexities and make compute instances accessible to all, regardless of technical expertise.

We hope this blog has provided valuable insights into the Spheron Compute Deployer Telegram Bot and its potential to transform the development of compute instances. Whether you're a seasoned developer or just starting out, this tool offers exciting possibilities for streamlining your workflow and simplifying the deployment process.