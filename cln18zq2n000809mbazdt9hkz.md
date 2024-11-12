---
title: "Simplifying Comprehensive IPNS Management With Spheron Network"
seoTitle: "Making IPNS Management Easier with Spheron Network"
seoDescription: "Explore the benefits of IPNS and the user-friendly features of the Spheron Network to effortlessly keep your content updated without dealing complexities"
datePublished: Wed Sep 27 2023 04:30:09 GMT+0000 (Coordinated Universal Time)
cuid: cln18zq2n000809mbazdt9hkz
slug: simplifying-comprehensive-ipns-management-with-spheron-network
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1695629110337/4edfbaf5-f53b-42ac-a453-cca2ecd729d5.png
tags: dns, web3, decentralization, ipfs, spheron

---

The [InterPlanetary Name System (IPNS)](https://docs.ipfs.tech/concepts/ipns/) creates mutable addresses on the [InterPlanetary File System (IPFS)](https://docs.ipfs.tech/concepts/what-is-ipfs/). Its primary function is to handle the issue of changing content addresses in a content-addressed system like IPFS. Whenever content is updated on IPFS, a new [Unique Content Identifier (CID)](https://docs.ipfs.tech/concepts/content-addressing/) is generated. This means that if you want to point to the latest version of the content, the CID needs to be updated every time the content changes.

IPNS addresses this issue by creating a [mutable address](https://docs.ipfs.tech/concepts/file-systems/) that always points to the latest version of the content. It allows for the replacement of the non-human-friendly CID with a human-friendly label. Each IPFS peer has its own unique public key, which is used to generate an IPNS name. **An IPNS name is the hash of a public key. It is associated with an IPNS record containing the content path (/ipfs/CID) it links to and other information such as the expiration, the version number, and a cryptographic signature signed by the corresponding private key. IPNS records are self-certifying, containing all the information necessary to certify their authenticity.** 

In this blog, we'll dive deep into the capabilities of IPNS and its integration into Spheron Network, exploring potential applications.

## What is Spheron Network?

[Spheron Network](https://spheron.network/) is a next-generation PaaS that offers low-cost and seamless access to Web3 infrastructure across multiple chains. It is explicitly designed to serve a broader audience, including startups, developers, and organizations looking to scale their infrastructure.

Spheron harnesses the power of blockchain technology to provide secure and scalable solutions, simplifying the hosting and deployment of dApps while reducing the learning curve. By combining IPFS storage, Filecoin, and Arweave, Spheron ensures a seamless yet affordable experience. In addition to web hosting, compute, and storage capabilities, Spheron offers many features to enhance productivity and enable stakeholders to reach new heights while prioritizing privacy, security, and reliability.

## Spheron Network’s Comprehensive IPNS Management Capabilities

Spheron Network has unveiled its latest addition: the [**"Storage" organization**](https://docs.spheron.network/sdk/storage-v2/) type, **designed to enhance user's data management experience. The Storage organization has specialized tools and features tailored to streamline data handling.**

With the help of Buckets for storage organization. Spheron Network enables users to logically group and organize their uploaded data. Each bucket lets users attach custom domains, facilitating seamless data sharing through their preferred domain names. Additionally, Users can create IPNS (InterPlanetary Name System) records within buckets to exert finer control over data accessibility. As part of this transition, the Spheron team seamlessly migrated IPFS Dedicated Gateways to the Storage organization for those with existing gateways. 

Spheron Network provides a set of functions and capabilities for working with IPNS (InterPlanetary Name System),  Here's what [Spheron Network can do with IPNS](https://docs.spheron.network/sdk/storage-v2/#ipns-records):

### 1\. Add IPNS Record:

The `addBucketIpnsRecord` function is used to create a new IPNS record for a bucket. It takes a `uploadId` parameter, which specifies the ID of the upload to which the IPNS record should point.

```typescript
const ipnsRecord: IpnsRecord = await client.addBucketIpnsRecord(bucketId, uploadId);
```

The `addBucketIpnsRecord` function takes two parameters:

* `bucketId`: The ID of the bucket to which the IPNS record should belong.
    
* `uploadId`: The ID of the upload to which the IPNS record should point.
    

### 2\. Update IPNS Record:

The `updateBucketIpnsRecord` function is used to update an existing IPNS record of a bucket. It takes a `uploadId` parameter, which specifies the ID of the upload to which the IPNS record should point.

```javascript
const ipnsRecord: IpnsRecord = await client.updateBucketIpnsRecord(bucketId, ipnsRecordId, uploadId);
```

The `updateBucketIpnsRecord` function takes three parameters:

* `bucketId`: The ID of the bucket whose IPNS record you want to update.
    
* `ipnsRecordId`: The ID of the IPNS record you want to update.
    
* `uploadId`: The ID of the upload to which the IPNS record should point.
    

### 3\. Get IPNS Records:

The `getBucketIpnsRecords` function is used to retrieve all IPNS records that have been published for a specified bucket. It returns an `IpnsRecord` object, each representing a single IPNS record.

```javascript
const ipnsRecords: IpnsRecord[] = await client.getBucketIpnsRecords(bucketId);
```

The `getBucketIpnsRecords` function takes one parameter:

* `bucketId`: The ID of the bucket whose IPNS records you want to retrieve.
    

This action makes the content accessible via a human-readable IPNS link, even if the underlying IPFS content changes.

### 4\. Get Specific IPNS Record:

The `getBucketIpnsRecord` function is used to retrieve a specific IPNS record from a bucket. It returns a single `IpnsRecord` object representing the requested IPNS record.

```javascript
const ipnsRecord: IpnsRecord = await client.getBucketIpnsRecord(bucketId, ipnsRecordId);
```

The `getBucketIpnsRecord` function takes two parameters:

* `bucketId`: The ID of the bucket whose IPNS record you want to retrieve.
    
* `ipnsRecordId`: The ID of the IPNS record you want to retrieve.
    

### 5\. Delete IPNS Record:

The `deleteBucketIpnsRecord` function is used to delete an IPNS record of a bucket.

```javascript
await client.deleteBucketIpnsRecord(bucketId, ipnsRecordId);
```

The `deleteBucketIpnsRecord` function takes two parameters:

* `bucketId`: The ID of the bucket whose IPNS record you want to delete.
    
* `ipnsRecordId`: The ID of the IPNS record you want to delete.
    

## Why do developers love to use IPNS Deployment?

Using IPNS deployment offers several benefits in certain scenarios. Here are some key advantages:

1. **Mutable Pointers:** IPNS allows you to create mutable pointers to immutable content in a decentralized network like IPFS. This means you can update the pointer to point to new content without changing the underlying CID. This is useful when you need to update the content frequently but want to maintain a consistent address to share with others.
    
2. **Consistency and Availability:** IPNS offers a tradeoff between consistency and availability. You can configure the validity period of the IPNS record, which affects the availability of the content. Longer validity veers towards availability, allowing the content to persist even without the private key holder signing a new record. On the other hand, shorter validity ensures consistency by resolving to the latest published IPNS record.
    
3. **Decentralized and Distributed:** IPNS create a static address that references a mutable content hash. It uses content-based addressing and distributed hash tables to ensure the reliability and availability of the content. This decentralized and distributed nature of IPNS makes it resilient to single points of failure and censorship.
    
4. **Reducing Gas Fees -** The process of updating an NFT's metadata usually involves updating the contract, which incurs gas fees. By using IPNS, you can effectively eliminate the need to update the contract when you want to update the NFT assets and metadata. Instead of storing the metadata in the contract, you would store an IPNS name pointing to the metadata. When you want to update the metadata, you simply change what the IPNS name points to. This doesn't require updating the contract and, therefore doesn't incur gas fees.
    
5. **Integration with DNS:** IPNS can be integrated with DNS to support DNS binding and provide traditional domain names. This allows you to use human-readable domain names while ensuring synchronized content across platforms. This integration can also benefit search engine optimization (SEO) by providing stable and consistent addresses for your content.
    

## Spheron Hosting and ENS

Spheron Network’s Hosting has the ability to facilitate the swift creation of websites, web applications, and native apps using IPFS/Filecoin. It incorporates essential features like privacy, encryption, and peer-to-peer functionality. Both the ENS and Spheron teams aspire to play a pivotal role in the infrastructure of Web 3.0, offering more capabilities to Web 3.0 developments. 

[**ENS provides**](https://ens.domains/) **a decentralized, censorship-resistant, and user-controlled domain naming system for websites, Dapps, and other decentralized web (Dweb) resources and services. Unlike DNS, which is managed by a central authority, ENS operates on smart contracts within the Ethereum blockchain.**

Consequently, Spheron Network’s Hosting technology is enhanced seamlessly to support the ENS domain name system. This enhancement empowers users with more convenient dApp deployment services. Now, users can effortlessly link an ENS domain name to their IPFS site and have their content automatically updated for future deployments, all thanks to Spheron Hosting's ENS domain name system compatibility.

The synergy between Hosting and ENS ensures that all Dweb users can truly embrace decentralization without relying on traditional centralized services.

## Maximizing Capabilities: IPNS + ENS 

The [Ethereum Name Service (ENS)](https://ens.domains/) serves as a decentralized, accessible, and expandable naming system rooted in the Ethereum blockchain. ENS's primary function is to link user-friendly names like **'name.eth'** to computer-readable identifiers, including Ethereum addresses, various cryptocurrency addresses, content hashes, and metadata.

Traditionally, we could associate it with the [IPFS hash](https://docs.ipfs.tech/concepts/hashing/) within ENS. However, the emergence of IPNS presents a superior option. Leveraging IPNS's mutable pointers, these two connections empower users to modify IPNS pointers without resetting the ENS linkage, which will save tons of gas fees for every update on Ethereum.

## How to add an ENS domain and use IPNS on Spheron Network

1. Follow this guide to learn how to add an ENS domain on Spheron Network successfully - [Guide to Connect Your Static Site with ENS Domain.](https://blog.spheron.network/guide-to-connect-your-static-site-with-ens-domain)
    
2. Follow the Spheron Network [documentation](https://docs.spheron.network/sdk/storage-v2/) to know more about IPNS.
    

## Conclusion

In summary, IPNS is a valuable tool in the world of decentralized content, providing a user-friendly and convenient method for naming and locating content on IPFS. Spheron Network takes this a step further by making it easier to create and oversee IPNS for your content. Thanks to the combined benefits of IPNS and the user-friendly features of the Spheron Network Platform, website admins can effortlessly keep their content updated without dealing with unnecessary complexities.

## Resources

* **Spheron IPNS Documentation -** [https://docs.spheron.network/sdk/storage-v2/#ipns-records](https://docs.spheron.network/sdk/storage-v2/#ipns-records)
    
* **Spheron ENS Documentation -** [https://docs.spheron.network/static/projects/ens/](https://docs.spheron.network/static/projects/ens/)
    
* **ENS Documentation -** [https://docs.ens.domains/dapp-developer-guide/resolving-names](https://docs.ens.domains/dapp-developer-guide/resolving-names)
    
* **IPNS Documentation -** [https://docs.ipfs.tech/concepts/ipns/](https://docs.ipfs.tech/concepts/ipns/)