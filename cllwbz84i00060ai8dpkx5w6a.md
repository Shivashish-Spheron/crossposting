---
title: "Deploy Your React Apps Within Minutes with Spheron Network"
seoTitle: "Streamline React App Deployment with Spheron Network"
seoDescription: "Benefit from continuous deployment, custom domains, and advanced features for a seamless development experience."
datePublished: Tue Aug 29 2023 13:15:11 GMT+0000 (Coordinated Universal Time)
cuid: cllwbz84i00060ai8dpkx5w6a
slug: deploy-your-react-apps-within-minutes-with-spheron-network
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1693293910292/d60ead59-bed7-46c2-b475-afb8314f7ae6.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1693295384463/8f270896-ed40-4e28-ba7c-eeb3e20f9e8e.png
tags: deployment, reactjs, web3, decentralization, spheron

---

# Introduction

[React](https://react.dev/) has become a widely popular JavaScript library for building modern, dynamic user interfaces for web applications. Its component-based architecture, virtual DOM, and efficient rendering make it a top choice for developers creating responsive and interactive web experiences. When it comes to deploying React apps, Spheron Network provides an easy way to host and deploy your React apps by providing a simple and easy UI to deploy your codebase from your Git repository directly onto the servers. With [Spheron network](https://spheron.network/), you don’t need to worry about anything - Spheron handles everything behind the scenes, so you can focus solely on developing great features.

By following this guide, you will be able to deploy your React app in less than a minute, benefiting from features such as continuous deployment and custom domain setup. So let's get started!

## What is Spheron Network?

Spheron Network is a next-generation PaaS that offers low-cost and seamless access to Web3 infrastructure across multiple chains. It is explicitly designed to serve a broader audience, including startups, developers, and organizations looking to scale their infrastructure. 

Spheron harnesses the power of blockchain technology to provide secure and scalable solutions, simplifying the hosting and deployment of dApps while reducing the learning curve. By combining IPFS storage, Filecoin, and Arweave, Spheron ensures a seamless yet affordable experience. In addition to web hosting, compute, and storage capabilities, Spheron offers many features to enhance productivity and enable stakeholders to reach new heights while prioritizing privacy, security, and reliability.

## How to Deploy React App with Spheron?

You can follow these steps to deploy your React Apps on Spheron.

### Step 1. Create a React Application

**You may skip this step if you already have a functioning React app.**

Make sure you have Node.js and the npm package manager installed.

* Open your terminal and enter the following command to create your React app
    

```typescript
npx create-react-app my-app
```

*  Navigate to your application 
    

```typescript
cd my-app
```

* Start your react project.
    

```typescript
npm start
```

Go to [**http://localhost:3000**](http://localhost:3000) in your browser and you will see the default create-react-app application. Develop your application, ensuring it's ready for deployment.

* Push your React app to Github, which will allow Spheron to gain access to your project for deployment. 
    

### Step 2: Create a Free Spheron Network Account

1. Visit Spheron Network: [https://spheron.network/](https://spheron.network/)
    
2. On the Spheron homepage, locate and click the **"Free Trial"** button.
    
3. You'll be directed to a login/signup page. **Choose your preferred authentication method: GitHub account, GitLab account, or Bitbucket account.**
    
4. Follow the provided prompts to authenticate your chosen account securely. This step ensures safe access to the Spheron Network platform.
    
5. After successful authentication, you'll be guided to a confirmation page confirming the completion of your account setup.
    

### Step 3: Creating an Organization

1. Upon logging in, you'll be directed to a page to create your organization's name, username, and Avatar. Ensure the "Web App" option is selected from the drop-down menu at the top right corner. And click **“Save”**.
    
2. Next, you'll be taken to a new page. Click the **"New Project"** button.
    

### Step 4: Deploying your React App With Sphron Platform UI

1. Next, You will see a new page. Select your preferred Git provider from the options and authorize Spheron to access your React application's repository.
    
2. Choose your React repository from the list of available repositories.
    
3. Select the protocol you want to use for deployment. As of now, **Spheron supports Arweave, Filecoin, and IPFS.**
    
4. Provide details about the branch you want to deploy and the build commands that are already going to be prefilled, but if you are using different commands than default, then the following settings can be configured:
    

![](https://lh6.googleusercontent.com/CuSgiqgOoSl5aLTw9rXmlIfQEVe9etSjMjVjiTW9snMRhQzzyNkuMag07IWCHv8jc_mYKv_Ua76Qn6k3s00jyxH87XRUTGDnrGRqFlOfG2AlVfkfazy59GdYopV9wu-ft996IOxXbwJMecbc-LfTHt8 align="left")

* **Framework:** Spheron has the capability to automatically pick the framework for you, but if it doesn't, choose Create React App.
    
* **Branch to deploy from:** Select the branch you want to deploy from the dropdown menu.
    
* **Root directory:** If you have a monorepo app structure, enter the root directory of your application.
    
* **Install command:** By default, it is `yarn install` , but you have the flexibility to select either `Yarn` or `npm` based on your preference.
    
* **Build command:** By default it is to `yarn build`,  but you have the flexibility to select either `Yarn` or `npm` based on your preference.
    
* **Publish directory:** Set this to *build*
    
* **Environment variables:** Add any environment variables that you want to set before building your application.
    
* **Node engine:** Change the node engine of your deployment if needed.
    

1. Click the **"Deploy"** button to initiate the deployment process.
    

That's it! Your React application will now be deployed to the selected protocol using the Spheron Platform UI.

**Note :** The first time you want to deploy your project, you need to do it manually through the dashboard. But after that, Spheron makes things easier. From the next time onwards, when you make any new changes and save them, Spheron will automatically triggers a new build and deployment of your project with those changes. This happens every time you push new changes to your project on GitHub, GitLab, or Bitbucket.

## Benefits of Deploying React App with Spheron Network

Deploying a React app with Spheron offers many benefits, including:

1. **Custom deployment environment:** Spheron provides a custom deployment environment for React apps, which can be tailored to your needs. This means you can choose the specific configurations that best suit your project. This helps reduce bugs and issues that arise due to environment inconsistencies.
    
2. **Continuous deployment:** Spheron offers continuous deployment, which means your application will be automatically deployed whenever you push changes to your repository. This can significantly speed up the development process and allows for quick rollouts of new features and bug fixes to your app. 
    
3. **Preview Mode:** React apps deployed on Spheron can be viewed in Preview Mode, which allows you to see how the app will look and function before it is deployed to a live environment
    
4. **Static site rendering:** React apps deployed on Spheron can take advantage of static site rendering, which can improve performance and SEO.
    
5. **Custom domain:** After deploying a React app on Spheron, it will automatically be assigned a .[spheron.app](http://spheron.app) domain. However, you can also add a custom domain of your choice.
    
6. **Built-in SSL:** Spheron provides built-in SSL encryption for all domains, which ensures that data transmitted between your app and your users' browsers is secure. This is especially important for apps that handle sensitive user data.
    
7. **Developer-friendly features:** Spheron offers various developer-friendly features like AI code generation SpheronGPT, and scaling capabilities, enabling a seamless development experience.
    
8. **Reliable support and documentation:** Spheron provides comprehensive documentation and support, helping you navigate any challenges you may face during deployment and development.
    
9. **Integration with other Spheron features:** By deploying your React app on Spheron, you can benefit from other features offered by the Spheron platform, enhancing the functionality of your app.
    

# Conclusion

In conclusion, deploying your React app with Spheron Network offers a streamlined and efficient way to bring your web application to life. With its user-friendly interface and support for cutting-edge features, Spheron simplifies the deployment process while providing many benefits. From continuous deployment and custom domain setup to static site rendering and built-in SSL encryption, Spheron empowers developers to focus on crafting exceptional user experiences without being bogged down by complex deployment procedures.

By choosing Spheron, you're ensuring the successful deployment of your React app and unlocking a range of features that enhance productivity, scalability, and security. 

Explore the [Spheron Guide](https://docs.spheron.network/) to start your journey toward hassle-free deployment and development.

# Resources

1. Spheron React Guide: [https://docs.spheron.network/framework-guide/deploy-react/](https://docs.spheron.network/framework-guide/deploy-react/)
    
2. React Documentation: [https://react.dev/learn](https://react.dev/learn)