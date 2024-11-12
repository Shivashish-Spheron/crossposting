---
title: "Deploy Your Angular Apps Seamlessly With Spheron Network"
seoTitle: "Step-by-Step Guide for Angular App Deployment with Spheron Network"
seoDescription: "Discover how Spheron Network simplifies the deployment of Angular apps, offering a seamless and efficient solution for your web applications."
datePublished: Fri Sep 01 2023 12:35:09 GMT+0000 (Coordinated Universal Time)
cuid: clm0kva3m000b08jz2dasgvgn
slug: deploy-your-angular-apps-seamlessly-with-spheron-network
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1693298336621/7211bc30-3714-48ae-afc0-8e30089cfb8c.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1693300341633/b36b35cd-1f64-41ee-af67-fa4efe7720cf.png
tags: deployment, angularjs, web3, decentralization, spheron

---

# Introduction

In today's fast-paced digital landscape, deploying web applications is crucial to sharing your innovative creations with the world. [Angular](https://angular.io/), a popular front-end framework, empowers developers to build dynamic and feature-rich web applications. When it comes to deploying Angular apps, there are several options available that can be tedious and time-consuming deployments of your Angular app. Still, one seamless option is available, the [Spheron Network](https://spheron.network/). Spheron is a powerful platform that allows you to easily deploy and manage your Angular projects with just a few clicks.

By following this guide, you will be able to deploy your Angular app in less than a minute, benefiting from features such as continuous deployment and custom domain setup. So let's get started!

## What is Spheron Network?

Spheron Network is a next-generation PaaS that offers low-cost and seamless access to Web3 infrastructure across multiple chains. It is explicitly designed to serve a broader audience, including startups, developers, and organizations looking to scale their infrastructure.

Spheron harnesses the power of blockchain technology to provide secure and scalable solutions, simplifying the hosting and deployment of dApps while reducing the learning curve. By combining IPFS storage, Filecoin, and Arweave, Spheron ensures a seamless yet affordable experience. In addition to web hosting, compute, and storage capabilities, Spheron offers many features to enhance productivity and enable stakeholders to reach new heights while prioritizing privacy, security, and reliability.

## How to Deploy Angular App with Spheron?

You can follow these steps to deploy your Angular Apps on Spheron.

### Step 1. Create an Angular Application

**You may skip this step if you already have a functioning Angular app.**

Make sure you have Node.js and the npm package manager installed.

* Install the Angular CLI globally on your system via:
    

```typescript
npm install -g @angular/cli
```

* Let’s create an angular project using the command below.
    

```typescript
ng new your-app-name
```

This process will create a simple application in the folder you named. The application will have all the tools to work with the commands you give through the Angular CLI. It might take a little while because the computer needs to get all the necessary parts to make the app work.

* The next step is to enter the directory of the app you are working on
    

```typescript
cd your-app-name
```

* Start your angular project.
    

```typescript
ng serve --open
```

The Angular project will start and open immediately in your browser once the preview on [**http://localhost:4200/**](http://localhost:4200/) is ready. By default, `ng serve` serves the application locally on port 4200, but this can be changed using a command line argument: `ng serve --port=8080`.

* Push your React app to Github, which will allow Spheron to gain access to your project for deployment.
    

### Step 2: Create a Free Spheron Network Account

1. Visit Spheron Network: [https://spheron.network/](https://spheron.network/)
    
2. On the Spheron homepage, locate and click the **"Free Trial"** button.
    
3. You'll be directed to a login/signup page. **Choose your preferred authentication method: GitHub account, GitLab account, or Bitbucket account.**
    
4. Follow the provided prompts to authenticate your chosen account securely. This step ensures safe access to the Spheron Network platform.
    
5. After successful authentication, you'll be guided to a confirmation page confirming the completion of your account setup.
    

### Step 3: Create an Organization

1. Upon logging in, you'll be directed to a page to create your organization's name, username, and Avatar. Ensure the "Web App" option is selected from the drop-down menu at the top right corner. And click **“Save”**.
    
2. Next, you'll be taken to a new page. Click the **"New Project"** button.
    

### Step 4: Deploying your Angular App With Sphron Platform UI

Next, You will see a new page. Select your preferred Git provider from the options and authorize Spheron to access your Angular application's repository.

1. Choose your Angular repository from the list of available repositories.
    
2. Select the protocol you want to use for deployment. As of now, **Spheron supports Arweave, Filecoin, and IPFS**.
    
3. Provide details about the branch you want to deploy and the build commands that are already going to be prefilled, but if you are using different commands than default, then the following settings can be configured:
    

![](https://lh6.googleusercontent.com/Y6gvCiUCaBawxv3GJU6YcFMYyxD3K-4h6whPxYL1K94lrsr5SHJ5HSEpU5rMc2FAw_2-5Jn_UNe9rYP5mJOELgbiVj0grmrp_ratXLbNcyc3fsNifZIXA54i-iJpLdSCSMdXuI0vsqHabo177kQIQBU align="center")

* **Framework:** Spheron has the capability to automatically pick the framework for you, but if it doesn't, choose Angular.
    
* **Branch to deploy from:** Select the branch you want to deploy from the dropdown menu.
    
* **Root directory:** If you have a monorepo app structure, enter the root directory of your application.
    
* **Install command:** By default, it is `yarn install` , but you have the flexibility to select either `Yarn` or `npm` based on your preference.
    
* **Build command:** By default it is to `yarn build`,  but you have the flexibility to select either `Yarn` or `npm` based on your preference.
    
* **Publish directory:** Set this to **dist/{app-name}**, where {app-name} is the name of your app in your package.json file.
    
* **Environment variables:** Add any environment variables that you want to set before building your application.
    
* **Node engine:** Change the node engine of your deployment if needed.
    

5.Click the **"Deploy"** button to initiate the deployment process.

That's it! Your Angular application will now be deployed to the selected protocol using the Spheron Platform UI.

**Note:** The first time you want to deploy your project, you need to do it manually through the dashboard. But after that, Spheron makes things easier. From the next time onwards, when you make any new changes and save them, Spheron will automatically trigger a new build and deployment of your project with those changes. This happens every time you push new changes to your project on GitHub, GitLab, or Bitbucket.

## Benefits of Deploying Angular App with Spheron Network

Deploying an Angular app with Spheron offers many benefits, including:

1. **Custom deployment environment:** Spheron provides a custom deployment environment for Angular apps, which can be tailored to your needs. This means you can choose the specific configurations that best suit your project. This can help to reduce bugs and issues that might arise due to environment inconsistencies.
    
2. **Continuous deployment:** Spheron offers continuous deployment, which means your application will be automatically deployed whenever you push changes to your repository. This can significantly speed up the development process and allows for quick rollouts of new features and bug fixes to your app.
    
3. **Preview Mode:** Angular apps deployed on Spheron can be viewed in Preview Mode, which allows you to see how the app will look and function before it is deployed to a live environment
    
4. **Static site rendering:** Angular apps deployed on Spheron can take advantage of static site rendering, which can improve performance and SEO.
    
5. **Custom domain:** After deploying an Angular app on Spheron, it will automatically be assigned a .[spheron.app](http://spheron.app) domain. However, you can also add a custom domain of your choice.
    
6. **Built-in SSL:** Spheron provides built-in SSL encryption for all domains, which ensures that data transmitted between your app and your users' browsers is secure. This is especially important for apps that handle sensitive user data.
    
7. **Developer-friendly features:** Spheron offers various developer-friendly features like AI code generation SpheronGPT, and scaling capabilities, enabling a seamless development experience.
    
8. **Support and documentation:** Spheron provides comprehensive documentation and support, helping you navigate any challenges you may face during deployment and development.
    
9. **Benefiting with other Spheron features:** By deploying your Angular app on Spheron, you can benefit from other features offered by the Spheron platform, enhancing the functionality of your app.
    

# Conclusion

In conclusion, deploying your Angular app with the Spheron Network offers a seamless and efficient solution for sharing your web application with the world. With its low costs, Web3 infrastructure access, and support for multiple chains, Spheron provides a powerful platform for startups, developers, and organizations to scale their infrastructure.

By harnessing the power of blockchain technology, Spheron ensures secure and scalable solutions while simplifying the deployment process. Additionally, Spheron offers features such as continuous deployment, custom domain setup, and static site rendering, which enhance productivity and improve the user experience. With Spheron's user-friendly interface and marketplace, deploying your Angular app has never been easier.

So, if you're looking for a reliable and effective solution for deploying your Angular app, Spheron Network is the way to go.

# Resources

1. Spheron Angular Guide: [https://docs.spheron.network/framework-guide/deploy-angular/](https://docs.spheron.network/framework-guide/deploy-angular/)
    
2. Angular Documentation: [https://angular.io/docs](https://angular.io/docs)