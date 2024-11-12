---
title: "Exploring Metadata on the Decentralized Web: The Spheron Storage Guide"
seoTitle: "Exploring Metadata on the Decentralized Web: The Spheron Storage Guide"
seoDescription: "Explore a comprehensive guide, from understanding metadata's role to uploading, accessing, and displaying it using Spheron Storage and IPFS"
datePublished: Sun Dec 10 2023 04:30:12 GMT+0000 (Coordinated Universal Time)
cuid: clpyzktj4000008jubukq3mua
slug: exploring-metadata-on-the-decentralized-web-the-spheron-storage-guide
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1702045049652/a215f8ee-2c72-459c-92a4-69d4ca7e3349.png
tags: cloud, blockchain, storage, web3, metadata

---

## **Phase 1: Understanding the Role of Metadata**

The decentralized web, powered by technologies like [IPFS (InterPlanetary File System)](https://docs.ipfs.tech/concepts/what-is-ipfs/), is transforming the way we store and access data. However, efficient data management in a decentralized environment requires more than just uploading files. Metadata plays a crucial role in organizing, retrieving, and understanding the content on the decentralized web. In this guide, we’ll explore the significance of metadata and how to use Spheron Storage to manage it effectively.

## **What is Metadata?**

Metadata is data about data. It provides essential information about a file, making it easier to search, categorize, and understand. In a decentralized context, metadata can include details like file names, descriptions, creators, timestamps, and more. Without metadata, decentralized data would be akin to a library with books lacking titles and author names.

## **The Importance of Metadata**

### **1\. Efficient Data Retrieval**

Metadata acts as a map, guiding users to the exact location of the content they seek. Imagine searching for a specific image in a vast collection of decentralized files. Metadata allows you to find that image quickly by filtering based on criteria like keywords, dates, or file types.

### **2\. Content Understanding**

Metadata provides context to data. It explains what the file is, who created it, and when it was last modified. This context is vital, especially when dealing with content like [NFTs (Non-Fungible Tokens)](https://blog.spheron.network/understanding-nfts-exploring-the-world-of-non-fungible-tokens) or unique digital assets. Metadata turns an image file into a **“CryptoPunk #1234”** with a description, making it more valuable and informative.

### **3\. Dynamic Content**

Metadata can be dynamic, enabling real-time updates and interactions. For instance, metadata associated with an NFT can change based on its ownership, allowing the NFT to display the current owner’s name or auction details. This dynamic aspect adds versatility and functionality to decentralized applications.

## **Phase 2: Uploading Metadata with Spheron Storage**

### **Prerequisites**

Before we proceed, make sure you have the following:

* [Node.js](https://nodejs.org/en) installed on your computer.
    
* An authentication token from Spheron Storage, which you can obtain from your account. Refer to the doc [here](https://docs.spheron.network/rest-api/#creating-an-access-token) to create an access token at Spheron.
    

### **Uploading Metadata**

Now, let’s see how to upload metadata to IPFS using Spheron Storage. Create a `metadata.json` file with the required information according to your requirements.

### **Code Example**

```javascript
import { SpheronClient, ProtocolEnum } from "@spheron/storage";
import fetch from "node-fetch";
import chalk from "chalk";
import Table from "cli-table3";
import figlet from "figlet";

const token = "YOUR_AUTH_TOKEN";
const client = new SpheronClient({ token });
const filePath = "./metadata.json";

async function uploadFileToIPFS(configuration) {
  const uploadResponse = await client.upload(filePath, configuration);
  console.log(chalk.green(`🚀 File uploaded successfully with ID: ${uploadResponse.uploadId}`));
  return uploadResponse;
}
```

In this code, we import the necessary modules and set up the environment. Then, we define an asynchronous function to upload a JSON file (metadata) to IPFS using Spheron Storage.

## **Phase 3: Accessing and Displaying Metadata**

Now that we’ve uploaded metadata, let’s explore how to access and display it in a user-friendly manner.

### **Code Example**

```javascript
async function fetchFromIPFS(protocolLink) {
  const jsonFileUrl = `${protocolLink}/metadata.json`;
  console.log(chalk.magenta(`🚀 Link to the JSON Data uploaded: `), jsonFileUrl);  try {
    const response = await fetch(jsonFileUrl);

    if (!response.ok) {
      throw new Error(`HTTP error! Status: ${response.status}`);
    }

    const jsonData = await response.json();
    return jsonData;
  } catch (error) {
    console.error(chalk.red("❌ Error fetching data from IPFS:"), error);
    throw error;
  }
}

function displayHeading(text) {
  console.log(
    chalk.yellow(figlet.textSync(text, { horizontalLayout: 'full' }))
  );
}

function displayJsonAsTable(jsonData) {
  const table = new Table({
    head: [chalk.blue('Key'), chalk.blue('Value')],
    colWidths: [30, 70]
  });

  for (const key in jsonData) {
    if (jsonData.hasOwnProperty(key)) {
      table.push([key, jsonData[key]]);
    }
  }

  console.log(table.toString());
}

async () => {
  displayHeading("Spheron - Storage 🌐");
  try {
    // Define the configuration for the upload
    const configuration = {
      name: "metadata upload",
      protocol: ProtocolEnum.IPFS,
      onUploadInitiated: (uploadId) => {
        console.log(chalk.magenta(`🔗 Upload initiated with ID: ${uploadId}`));
      },
      onChunkUploaded: (uploadedSize, totalSize) => {
        console.log(chalk.blue(`📦 Uploaded chunk: ${uploadedSize}/${totalSize}`));
      },
    };

    const uploadResponse = await uploadFileToIPFS(configuration);

   // Log the upload information
    console.log(chalk.green(`📝 Upload Information:`));
    displayJsonAsTable(uploadResponse);

   const fetchedJsonData = await fetchFromIPFS(uploadResponse.protocolLink);
    console.log(chalk.green("✅ Fetched JSON data from the above link:"));
    displayJsonAsTable(fetchedJsonData);
  } catch (error) {
    console.error(chalk.red("❗ Error during the process:"), error);
  }
})();
```

This code section demonstrates how to fetch metadata from IPFS and display it in the CLI using visual enhancements like ASCII art headings and tabulated data.

**You can find the full code and usage examples there for reference.**

**GitHub Repository:** [**Spheron Storage Example**](https://github.com/Giri-Spheron/Uploading-Metadata-with-Spheron-Storage)

In this guide, we’ve explored the importance of metadata in the decentralized web and learned how to upload, access, and display metadata using Spheron Storage. Metadata empowers decentralized applications with efficient data management and contextual understanding. Whether you’re dealing with NFTs, dynamic content, or any decentralized data, metadata is the key to unlocking its full potential on the decentralized web.

Happy metadata management on the decentralized web! 🌐