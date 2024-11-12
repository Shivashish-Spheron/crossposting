---
title: "Unleash the Power of IPFS with Spheron Compute: A Step-by-Step Guide to Whitelabeling Your Own IPFS Gateway with Custom Domains"
seoTitle: "Step-by-Step Guide Whitelabeling Your IPFS Gateway with Custom Domain"
seoDescription: "Spheron simplifies this process by allowing you to set up your IPFS node using Spheron Compute and whitelabel the gateway using your custom domain."
datePublished: Fri Apr 21 2023 13:46:36 GMT+0000 (Coordinated Universal Time)
cuid: clgqluvk900060aldg5qk41db
slug: unleash-the-power-of-ipfs-with-spheron-compute-a-step-by-step-guide-to-whitelabeling-your-own-ipfs-gateway-with-custom-domains
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1682084696250/9235e1e6-3787-41a3-98cb-be704a25f3e7.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1682084777678/7b837020-3136-43ad-9adf-21f790bcdfca.png
tags: cloud, web-development, webdev, web3, ipfs

---

Are you new to the tech community and wondering how to access content on the IPFS network using your domain name? Spheron simplifies this process by allowing you to use customized URLs for IPFS Gateway services. In this article, we will guide you through setting up an IPFS node using Spheron Compute and using your custom domain to Whitelabel IPFS Gateway.

## How to set up an IPFS Node using Spheron Compute?

Setting up an IPFS node using Spheron Compute is a straightforward process. With Spheron Compute, you can quickly deploy an IPFS node and access its features like IPFS Web Interface and IPFS Gateway.

To get started, follow these simple steps:

1. Go to the Compute section in Spheron.
    
2. Create a new cluster by clicking on the "New Cluster" button.
    
3. Click on the "Select from marketplace app" button for fast-track deployment.
    
4. Select the IPFS template from the marketplace.
    
5. Choose your instance plan and click on the "Deploy" button.
    

Once your IPFS node is up and running, you can upload files to IPFS via WebUI or HTTP-Client, and access files using IPFS Gateway. Let’s take a look at how that works.

## Upload files to IPFS

### Using IPFS WebUI

If you are new to IPFS, you might wonder how to manage your files on the network. Luckily, IPFS provides an easy-to-use Web interface that makes it simple for anyone to add, pin, and share files. Whether you're a developer or a less experienced user, the interface has all the functionality you need to get started.

By default, the IPFS Web interface is configured on port 5001. To access the IPFS Web interface, simply click on the URL corresponding to internal port 5001 from your instance page. Then, add '/webui' to the end of the URL, and you're ready to go! With the IPFS Web interface, you can easily manage your content on the IPFS network.

### Using IPFS Client SDK

[![Showing Upload URL for IPFS node](https://res.cloudinary.com/practicaldev/image/fetch/s--C-mWUhTW--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/a3hkkfcmwnjrut1qwak1.png align="left")](https://res.cloudinary.com/practicaldev/image/fetch/s--C-mWUhTW--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/a3hkkfcmwnjrut1qwak1.png)

The `ipfs-http-client` is a powerful package that simplifies the entire process, allowing you to effortlessly upload files to your IPFS node from your app with just a few simple steps.

* First, install the package by running `npm install ipfs-http-client`.
    
* Then, use the create method to connect to your IPFS node. Replace with your IPFS node URL corresponding to internal port 5001.
    

```javascript
const ipfs = create({
    url: `http://${your-ipfs-url}/api/v0`,
});
```

* With the version and id methods, you can easily retrieve information about your node.
    

```javascript
const version = await ipfs.version();
const id = await ipfs.id();
```

* Finally, use the add method to upload files directly to your node.
    

```javascript
const uploadedFile = await ipfs.add(file, {
    progress: (prog) => console.log(`received: ${prog}`),
});

const fileHash = uploadedFile.cid.toString();
```

If you're looking for a helpful reference to guide you through the setup, check out this [**example**](https://github.com/aayushmahapatra/IPFS-uploader/blob/main/src/App.js).

### Access files using IPFS Gateway

If you are looking for a way to easily access content stored on the IPFS network without installing any special software, IPFS Gateway has got you covered! As a user, you can use the Gateway to access content via HTTP requests. It acts as a bridge between the IPFS network and the traditional internet, making it easy to access content from anywhere.

By default, the IPFS gateway is configured on port 8080. To start, click on the URL corresponding to internal port 8080 from your instance page. Once you're there, you can copy the CID of your file, add the prefix `/ipfs/your-cid` to the end of the URL, and voila! You can now access your file directly from the IPFS network. It's that simple!

[![Showing Gateway link of IPFS node](https://res.cloudinary.com/practicaldev/image/fetch/s--gnGC0e8I--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/ae78m599bas2d7x7tsul.png align="left")](https://res.cloudinary.com/practicaldev/image/fetch/s--gnGC0e8I--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/ae78m599bas2d7x7tsul.png)

## How to use your custom domain to Whitelabel IPFS Gateway using Spheron Compute?

Are you ready to take your IPFS Gateway experience to the next level? With Spheron, setting up your custom domain to whitelabel your Gateway is simple and easy. Just navigate to the Domains tab within the platform and unleash your creativity! Add your favorite domain or subdomain and select the instance where you want it to point. With just one click, you're on your way to a personalized IPFS Gateway experience.

Once you've added your domain, it's time to sit back and wait for the magic to happen. Usually, it only takes a few minutes for the domain records to propagate - some things are worth waiting for! But once your records have propagated, it's time to click Verify within Spheron to confirm your customized domain is connected to your instance.

And voila! Your custom domain is now set up and ready to go. Get ready to share and access your IPFS content with your customized domain name, all in a secure and decentralized manner. With Spheron, you don't have to be a tech genius to set up your custom domain to whitelabel IPFS Gateway. It's a straightforward process that anyone can enjoy.

You can visit [**https://dnschecker.org/**](https://dnschecker.org/) to verify if your DNS is propagated.

## Benefits of using Spheron Compute for Whitelabeling

Spheron Compute simplifies the process, offering a range of benefits for users. Here are some reasons why you should consider using Spheron Compute for whitelabeling:

### HTTPS

With Spheron, users can enjoy a secure and encrypted connection to the IPFS network, ensuring their content stays safe and protected from prying eyes.

### Ownership

Spheron allows users to deploy their own IPFS nodes. That provides users more ownership over their content. They can add their custom domains and fully control how their content is served.

### Custom domains

Spheron allows users to access content on the IPFS network using their customized domain name. That means you can brand your IPFS Gateway to match your business or personal identity.

### Pay-as-you-use Model

Spheron Compute is available on a pay-as-you-use basis, which means users can scale their usage up or down as required without incurring additional costs. That makes it an affordable and flexible option for anyone accessing content on the IPFS network.

**So why wait? Sign up for Spheron today and use your domain to whitelabel IPFS Gateway to personalize your experience!** 🚀