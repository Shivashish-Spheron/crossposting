---
title: "Deploy Your Next.js Application on Spheron Network: With and Without APIs"
seoTitle: "Deploying Next.js Apps on Spheron: A Decentralized Hosting Guide"
seoDescription: "Learn how to deploy Next.js applications on the Spheron Network, a next-gen PaaS offering decentralized hosting."
datePublished: Sun Aug 27 2023 05:30:09 GMT+0000 (Coordinated Universal Time)
cuid: cllt0hhci000109l7e2q1d8dw
slug: deploy-your-nextjs-application-on-spheron-network-with-and-without-apis
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1693030507277/49c3ab4c-5b8a-40bf-8930-cd22a84a34da.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1693030624231/a46367a2-eddc-4240-b0a6-7bdde620cedc.png
tags: apis, nextjs, web3, decentralization, spheron

---

# Introduction

Next.js, a popular web framework built on top of React, offers developers powerful tools for building efficient and feature-rich web applications. Deploying these applications on the Spheron Network provides a decentralized and scalable environment for hosting. In this blog, we'll walk you through the process of deploying both static Next.js applications without APIs and with APIs on the Spheron Network.

## What is Spheron Network?

Spheron Network is a next-generation PaaS that offers low-cost and seamless access to Web3 infrastructure across multiple chains. It is explicitly designed to serve a broader audience, including startups, developers, and organizations looking to scale their infrastructure.

Spheron harnesses the power of blockchain technology to provide secure and scalable solutions, simplifying the hosting and deployment of dApps while reducing the learning curve. By combining IPFS storage, Filecoin, and Arweave, Spheron ensures a seamless yet affordable experience. In addition to web hosting, compute, and storage capabilities, Spheron offers many features to enhance productivity and enable stakeholders to reach new heights while prioritizing privacy, security, and reliability.

## How to Deploy Next.js apps with Spheron?

There are two ways to deploy your Next.js applications on Spheron Network, depending on whether your application is static or dynamic.

## 1\. Deploying a Static Next.js Site with Spheron Network

If your Next.js app does not require APIs, you can smoothly deploy it with Spheron Network's Site feature.

To get started with deploying your static Next.js app, follow these steps:

### **Step 1: Set Up Your Next.js Project**

* Create a new Next.js project:
    

```basic
npx create-next-app my-next-app
```

```basic
cd my-next-app //Change into the project directory:
```

Build your application and ensure that it is ready for deployment.

* Push your Next.js app to Github, allowing Spheron to gain access to your project for deployment.
    

### **Step 2: Configure Your Next.js Project for Decentralized Storage Deployment**

To seamlessly deploy your Next.js app without manual intervention, you have to make a few modifications to facilitate successful deployment:

In your `next.config.js` file, incorporate the following configuration:

```javascript
module.exports = {
  images: {
    loader: 'akamai',
    path: '',
  },
  trailingSlash: true,
}
```

If you encounter this error during deployment via Spheron: **"Error: Image Optimization using Next.js'** default loader is incompatible with **'next export'**, resolve it by adding the following image configuration:

```javascript
json
{
  "loader": "akamai",
  "path": ""
}
```

The `trailingSlash: true` configuration will rectify any routing refresh issues within IPFS. If you notice missing images in alternate routes, update your `next.config.js` file with the following configuration:

```javascript
const isProd = process.env.NODE_ENV === "production";
module.exports = {
  ...,
  assetPrefix: isProd ? "https://your-domain.com" : "",
}
```

### **Step 3: Create a Free Spheron Network Account**

1. Visit Spheron Network: [https://spheron.network/](https://spheron.network/).
    
2. On the Spheron homepage, locate and click the **"Free Trial"** button.
    
3. You'll be directed to a login/signup page. **Choose your preferred authentication method: GitHub account, GitLab account, or Bitbucket account.**
    
4. Follow the prompts to authenticate your account securely. This step ensures safe access to the Spheron Network platform.
    
5. After successful authentication, you'll be guided to a confirmation page confirming the completion of your account setup.
    

### **Step 4: Creating an Organization**

1. Upon logging in, you'll be directed to the Create Organization page, where you can give your organization a name, username, and an Avatar. Ensure the **"Web App"** option is selected from the drop-down menu at the top right corner. Click **“Save”**.
    
2. Next, you'll be taken to the Web App Dashboard. Click the **"New Project"** button.
    

### **Step 5: Deploy Your Project Using the Spheron Platform UI**

1. Select your preferred Git provider from the options and authorize Spheron to access your repositories.
    
2. Choose your Next.js repository from the list of available repositories.
    
3. Select the protocol you want to use for deployment. **As of now, Spheron supports Arweave, Filecoin, and IPFS**.
    
4. Provide details about the branch you want to deploy and the build commands that are already going to be prefilled, but if you are using different commands than default, then **the following settings can be configured:**
    

![](https://lh6.googleusercontent.com/D1Dc_Htt7d_a0LVtfvWUvYNkT1nxw3Ebz3MKC0dywcfJ6qywAmCYSJBTDFBIDgh-7oXltiaKxeJdrEXrkunv8fAZCAngNZeOmXLMbYcS8TLfDwlQMkXndQqPdV0A9s06XZrwnBti3M7X6dv4bfCtS88 align="left")

* **Framework:** Spheron will automatically pick the framework for you, but if it doesn't, choose Next.js.
    
* **Branch to deploy from:** Select the branch you want to deploy from the dropdown menu.
    
* **Root directory:** If you have a monorepo app structure, enter the root directory of your application.
    
* **Install command:** By default, it is `yarn install` , but you have the flexibility to select either Yarn or npm based on your preference.
    
* **Build command:** Set this to `next build && next export`*.* This command is required for deploying your application to IPFS, Arweave, or Filecoin. Do not change the command unless you are sure of what you are doing.
    
* **Publish directory:** Set this to **out**.
    
* **Environment variables:** Add environment variables that are required for your application.
    
* **Node engine:** Set by default. Change the node engine if needed.
    

5\. Click the **"Deploy"** button to initiate the deployment process.

By following these steps, you'll successfully deploy your Next.js project using the Spheron platform, taking full advantage of decentralized storage options.

**Note:** The first time you want to deploy your project, you need to do it manually through the dashboard. But after that, Spheron makes things easier. From the next time onwards, when you make any new changes and save them, Spheron will automatically trigger a new build and deployment of your project with those changes. This happens every time you push new changes to your project on GitHub, GitLab, or Bitbucket.

## 2\. Deploying a Dynamic Next.js Application on Spheron Network

If your Next.js app requires APIs, you can deploy it via Spheron Compute.

To get started with deploying your dynamic Next.js app on Spheron Compute, follow these steps:

### **Prerequisites**

* A DockerHub account
    
* Node.js installed
    
* Familiarity with Docker and Next.js
    

### **Step 1: Create a Next App**

1\. Start by creating a new Next.js project using the command:

```typescript
npx create-next-app nextapp
cd nextapp //Change into the project directory
```

2\. Create a new file named `hello.js` inside the `pages/api` directory with the following code:

```javascript
export default function handler(req, res) {
  res.status(200).json({ message: "Hello, World!" });
}
```

3\. Launch the development server:

```typescript
npm run dev
```

Open your web browser and navigate to [http://localhost:3000/api/hello](http://localhost:3000/api/hello) to see the JSON response: `{"message": "Hello, World!"}`.

### **Step 2: Create a Dockerfile**

Create a Dockerfile in the root directory of your Next.js app with the following content:

\# Use an official Node.js runtime as the base image

`FROM node:14-alpine`

\# Set the working directory in the container

`WORKDIR /app`

\# Copy the package.json and package-lock.json files to the container

`COPY package*.json ./`

\# Install dependencies

`RUN npm install`

\# Copy the app's source code to the container

`COPY . .`

\# Build the Next.js app

`RUN npm run build`

\# Expose the port that Next.js runs on

`EXPOSE 3000`

\# Run the Next.js app

`CMD ["npm", "start"]`

### **Step 3: Set Default Platform for Docker Build**

**Note:** This step is necessary only for ARM-based processors. If you have other systems, you can skip this step.

Docker images built with Apple Silicon (or another ARM64-based architecture) can create issues when deploying the images to a Linux or Windows-based AMD64 environment. Before running the docker build command, run this command in your terminal:

```typescript
export DOCKER_DEFAULT_PLATFORM=linux/amd64
```

### **Step 4: Build and Run the Docker Image**

To build the docker image

1. Save the Dockerfile in the root directory of your Next.js app.
    
2. Open a terminal and navigate to your project's root directory.
    
3. Build the Docker image:
    

```typescript
docker build -t nextapp
```

4\. Run a container based on the built image to test if everything is working properly:

```typescript
docker run -p 3000:3000 nextapp
```

### **Step 5: Push the App to Docker Hub**

1. Create a repository on Docker Hub with the name `nextapp`.
    
2. Log in to Docker Hub using:
    

```typescript
docker login -u YOUR-USER-NAME
```

3\. Tag the image:

```typescript
docker tag nextapp YOUR-USER-NAME/nextapp
```

4\. Push the image to Docker Hub:

```typescript
docker push YOUR-USER-NAME/nextapp
```

### **Step 6: Deploy on Spheron Compute**

1. Access the Spheron platform and navigate to the upper right corner, where you'll find the **"Compute"** option from the drop-down menu. Once there, click on **"New Cluster"** on the page.
    
2. Select **"Import from Docker Registry"** provide the following information, and click **Next**.
    
    * Cluster name
        
    * Docker image and tags
        
3. **Scaling (Scale Hardware Resources):** Spheron gives you different options to consider for scaling computational resources allocated to an instance. This can help you match the needs of your application.
    
    * **Manual Scaling -** Resources can be manually scaled. You have the power to adjust the amount of hardware resources your application needs according to the requirements. Manual scaling is currently in alpha access. To access this feature, please follow the process outlined in the [documentation](https://docs.spheron.network/compute/scaling/manual/).
        
    * **Auto Scaling -**  This is like having an intelligent assistant that adapts to changes without you needing to intervene. Spheron automatically adjusts the hardware resources based on the demands of your application. This exciting feature is not yet live and is coming soon.
        
    * **No Scaling -** Resources can't be scaled after the deployment. **Currently, this option is available for the scaling section.**
        
4. **Regions:** Next, If you have selected **No Scaling**, Select your preferred region for deployment. The container will be deployed in **Any** by default. Choosing a region closer to your users can improve performance and reduce latency. Spheron offers the following regions to choose from:
    
    * US-east
        
    * US-west
        
    * US-central
        
    * EU-west
        
    * Any
        

**Note:**

* For **Manual Scaling** deployments, we only have **eu-east** region live right now.
    
* It is recommended to select **Any** region for no scaling option to get higher chances of successful deployment as it will deploy on any providers in the network.
    

**5\. Plans:** Next, Choose an instance plan that aligns with your requirements. Spheron Network will recommend a suitable plan according to the template, but you can customize it if needed from available plans or choose to **create custom plans**.

**Note:** The pricing plans for the manual scaling option will be according to the selected regions, while the no scaling option will follow plans irrespective of regions.

**6\. Next, Configure storage:** You have to choose **Ephemeral Storage** from the available options. Additionally, you get the option to choose **Persistent Storage**.

* **Ephemeral storage** is called Volatile storage and is erased when the instance is restarted, redeployed, or shut down.
    
* **Persistent storage** will not be erased unless the instance is closed. If choosing persistent storage, specify the type of storage (HDD, SSD, NVMe) and Add mount point.
    

7\. You can add Additional Configurations, such as.

* Choose a port policy mapping and specify the **container port and exposed port (Choose from 80 or random port). This is mandatory.**
    
* Set **environment variables** and **secret environment** variables if needed.
    
* You can Add any Advanced configuration, such as specifying commands and arguments.
    
* You can set up a **health checkup with a health check path and port**. Enabling a health check is crucial for various reasons, especially to ensure your service's smooth operation and availability. **By setting up a health check, you will regularly receive email notifications if it goes down for any reason.**
    

8\. Review your settings and configurations. Click **"Deploy"** to initiate deployment.

### **Verification and Troubleshooting**

1. Wait for the instance to provision and access the app using the connection URL.
    
2. Check instance logs and events for any issues or errors.
    

Following these steps, you can create a Next.js app, containerize it with Docker, push it to Docker Hub, and deploy it on Spheron Compute.

## Benefits of Deploying your app on the Spheron network

Deploying your app on Spheron Network has many benefits, including:

1. **Decentralized deployment:** Spheron Network allows developers to deploy their applications to a decentralized network. This means your app is not dependent on a single centralized server, making it more resilient to failures and attacks.
    
2. **Continuous deployment:** Spheron offers continuous deployment for static next.js apps, which means your application will be automatically deployed whenever you push changes to your repository. This can significantly speed up the development process and allow for quick rollouts of new features and bug fixes to your app.
    
3. **Preview Mode:** Next.js apps deployed on Spheron can be viewed in Preview Mode, which allows you to see how the app will look and function before it is deployed to a live environment.
    
4. **Static site rendering:** Next.js apps deployed on Spheron can take advantage of static site rendering, which can improve performance and SEO.
    
5. **Custom domain:** After deploying a Next.js app on Spheron, it will automatically be assigned a **.**[**spheron.app**](http://spheron.app) domain. However, you can also add a custom domain of your choice.
    
6. **Developer-friendly features:** Spheron offers various developer-friendly features like AI code generation SpheronGPT, and scaling capabilities, enabling a seamless development experience.
    
7. **Support and documentation:** Spheron provides comprehensive documentation and support, helping you navigate any challenges you may face during deployment and development.
    
8. **Support for various web frameworks:** Spheron Network supports various web frameworks, including static websites, React, Vue, Next.js, Next.js web apps, and dapps. This means that developers can deploy their apps regardless of their web framework.
    
9. **A complete suite of services:** Spheron Network offers a complete suite of services that support blockchain applications. This includes hosting, storage, and computing services, making it a one-stop shop for developers and businesses who want to deploy their dApps.
    

## Conclusion

Deploying Next.js applications on the Spheron Network offers a decentralized and efficient hosting solution. Whether you're deploying a static Next.js application without APIs or a more complex application with APIs, following the steps outlined in this blog will help you harness the power of Spheron for seamless and scalable deployments. Explore the possibilities of Next.js and Spheron Network to build and deploy your web applications with confidence.

## Resources

**Spheron Network Documentation :**

1. [https://docs.spheron.network/server-guide/nextjs/](https://docs.spheron.network/server-guide/nextjs/)
    
2. [https://docs.spheron.network/framework-guide/deploy-next/](https://docs.spheron.network/framework-guide/deploy-next/)