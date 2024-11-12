---
title: "Incognfto: A Private NFT Gallery"
seoTitle: "Incognfto: A Private NFT Gallery"
seoDescription: "Incognfto is a groundbreaking NFT platform utilizing Spheron Network & Lit Protocol for secure, private NFT minting, and reshaping IP protection."
datePublished: Mon Jul 31 2023 14:30:42 GMT+0000 (Coordinated Universal Time)
cuid: clkqywmpe000b09l2bh6h5xeq
slug: incognfto-a-private-nft-gallery
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1690811846059/882e6ca6-9e6e-407e-9486-fc9fee31f08e.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1690812713019/87805396-220a-4106-81e4-2e41c85b7564.png
tags: security, accessibility, privacy, ipfs, nft

---

In the fast-evolving NFT landscape, data security, intellectual property protection, and privacy concerns are crucial. We built [Incognfto](https://github.com/spheronFdn/incognfto/blob/main/README.md) to address these challenges by offering a solution that allows NFT owners to mint and enjoy their assets securely. Leveraging [**Spheron Network**](https://spheron.network/) and **Lit Protocol**, Incognfto ensures exclusive access to NFTs for rightful owners while maintaining ownership control and privacy.

Our vision is to prioritize security, privatization, and an enriched NFT experience for owners, artists, collectors, and enthusiasts. By harnessing the Lit Protocol's advanced encryption and programmable signing, Incognfto empowers users to manage sovereign identities and maintain client-side data encryption without relying on centralized key custodians. This innovative approach sets a new standard for NFT ownership, enhancing security and privacy in the dynamic world of NFTs.

## What is Lit Protocol?

[Lit Protocol](https://litprotocol.com/) is a distributed key management network that offers encryption and programmable signing services based on threshold cryptography. It enables various use cases, including DeFi, infrastructure, sovereign data, Web3 social, gaming, and token gating for Web2 apps, providing developers with a versatile toolkit for enhancing security, privacy, and access control in the blockchain and decentralized space.

## NFT Gallery vs Incognfto Private Gallery

To illustrate how Incognfto stands out as a superior option compared to other NFT galleries, we have prepared a helpful comparison chart for your better understanding.

<table><tbody><tr><td colspan="1" rowspan="1"><p><strong>Feature</strong></p></td><td colspan="1" rowspan="1"><p><strong>Public NFT Gallery</strong></p></td><td colspan="1" rowspan="1"><p><strong>Incognfto</strong></p></td></tr><tr><td colspan="1" rowspan="1"><p><strong>Accessibility</strong></p></td><td colspan="1" rowspan="1"><p>Publicly accessible</p></td><td colspan="1" rowspan="1"><p>Privately accessible</p></td></tr><tr><td colspan="1" rowspan="1"><p><strong>Security</strong></p></td><td colspan="1" rowspan="1"><p>Less secure, as NFTs are on a public blockchain</p></td><td colspan="1" rowspan="1"><p>More secure, as NFTs are encrypted</p></td></tr><tr><td colspan="1" rowspan="1"><p><strong>Ownership control</strong></p></td><td colspan="1" rowspan="1"><p>Less control, viewable by anyone</p></td><td colspan="1" rowspan="1"><p>More control, viewable only by owners</p></td></tr><tr><td colspan="1" rowspan="1"><p><strong>Privacy</strong></p></td><td colspan="1" rowspan="1"><p>Less or no privacy</p></td><td colspan="1" rowspan="1"><p>More privacy</p></td></tr><tr><td colspan="1" rowspan="1"><p><strong>Community support</strong></p></td><td colspan="1" rowspan="1"><p>Less active community</p></td><td colspan="1" rowspan="1"><p>More active community</p></td></tr></tbody></table>

## How does it work?

![](https://lh5.googleusercontent.com/UJw7NdhCbQY_nbVd0RgSUx57J9GdyMHXlt1E3sNnnwqjG9XKIN9-rQuTNmoBc-0TOXRWANU976_5rvuj_V_F2sxPvb1WXl5mgTL7MeNwu4pZPG2ybDpzI8ix1vwhhJsd2wWslNF5ZJyfqU7-AvCfmr4 align="left")

Incognfto follows a straightforward workflow to ensure privacy and secure access to NFTs. Here's a high-level overview:

## 1\. Encryption: Safeguarding NFT Content

At the core of Incognfto's privacy measures is a robust encryption process that employs the Lit Protocol to ensure confidentiality and protection of NFT content from unauthorized access. The `encryptFile` function plays a vital role in this process, utilizing the encryptUpload function from the Spheron Browser SDK to encrypt NFT files before uploading them to IPFS. The process involves the following steps:

* First, the function checks if the Lit Node client is connected; if not, it establishes the connection.
    
* Second, it obtains an authentication signature (`authSig`) through LitJsSdk's `checkAndSignAuthMessage` method, ensuring user authentication and access validation during encryption.
    
* Third, the `createAccessControlCondition` function defines access control conditions, determining authorized users for decryption and data access.
    
* Fourth, the `encryptUpload` function has parameters like `authSig`, access control conditions, blockchain network, NFT file, Lit Node client instance, and additional configuration.
    
* Finally, the `encryptFile` function returns the encryption result, which may include the encrypted file's location or identifier.
    

```typescript
async encryptFile(id: string, file: any, configuration: any) {
   if (!this.litNodeClient) await this.connect();
   const authSig = await LitJsSdk.checkAndSignAuthMessage({ chain });
   const uploadRes = encryptUpload({
     authSig,
     accessControlConditions: createAccessControlCondition(id),
     chain,
     file,
     litNodeClient: this.litNodeClient,
     configuration,
   });
   return uploadRes;
 }
```

## 2\. Minting and Ownership: Creating Unique NFT Tokens

Once an NFT is encrypted on Incognfto, the platform mints it on the blockchain, creating a unique ownership token linked to the owner's wallet address. This token grants exclusive decryption and viewing privileges to the NFT's content, ensuring controlled access. To achieve this, Incognfto harnesses the robust access controls offered by the Lit Protocol. The `createAccessControlCondition` function takes an id parameter, representing the NFT's unique identifier, and constructs an access control condition using the Lit Protocol's schema. By implementing and leveraging access control conditions as shown in the provided code snippet, Incognfto ensures that only the rightful NFT owner can access and decrypt the locked data, enhancing security and privacy within the gallery while empowering NFT owners with full control over their digital assets.

```typescript
const client = new LitJsSdk.LitNodeClient({});
const chain = "mumbai";


const createAccessControlCondition = (id: string) => {
 return [
   {
     contractAddress: process.env.REACT_APP_CONTRACT_ADDRESS,
     standardContractType: "ERC721",
     chain,
     method: "ownerOf",
     parameters: [id],
     returnValueTest: {
       comparator: "=",
       value: ":userAddress",
     },
   },
 ];
};
```

## 3\. Unlocking NFTs

Unlocking an NFT is a seamless experience for authorized users on Incognfto, as the platform verifies their access rights before decryption. The Lit Protocol's access control conditions are pivotal in determining who can access and decrypt the locked NFT data. The decryption process is handled by the `decryptFile` function, which ensures a secure connection with the Lit Node client and authenticates users with an authentication signature (`authSig`) from LIT Protocol's `checkAndSignAuthMessage` method. Using the authSig and IPFS CID, the decryptUpload function decrypts the NFT file, presenting the unlocked content to authorized users through the decryptFile function. This enables users to fully enjoy their NFTs within the private gallery, with complete ownership and control.

```typescript
async decryptFile(ipfsCid: string) {
   if (!this.litNodeClient) await this.connect();
   const authSig = await LitJsSdk.checkAndSignAuthMessage({ chain });
   const decryptedFile = await decryptUpload({
     authSig,
     ipfsCid,
     litNodeClient: this.litNodeClient,
   });
   return decryptedFile;
 }
```

## Benefits of Incognfto

**Enhanced Investment Security:** Investors holding valuable NFTs can rest assured knowing their assets are shielded from public scrutiny. Incognfto private gallery minimizes the risk of targeted attacks or unwanted attention that could potentially impact the value of the user holdings.

**Protecting Sensitive Information:** Some NFTs may contain sensitive information, such as personal data, legal documents, or confidential contracts. Incognfto private NFT gallery ensures that these private details remain hidden from the public eye, preventing potential misuse or unauthorized access.

**Securing Exclusive Collectibles:** Some NFTs are created as limited editions or exclusive collectibles. Incognfto private gallery ensures that these premium assets are viewable only by their rightful owners or a select group, preserving their rarity and exclusivity.

**Seamless Experience:** The user-friendly interface of Incognfto streamlines the process of uploading, minting, and unlocking NFTs within the private gallery.

## Conclusion

In conclusion, Incognfto offers a distinctive and secure solution, providing NFT owners with an unparalleled private gallery experience. With a strong focus on security, privacy, and ownership control, artists and collectors can trust that their NFTs remain exclusively accessible to them, thanks to Lit Protocol's access control mechanisms. Incognfto stands at the forefront of safeguarding valuable NFT assets, revolutionizing the NFT space with its user-friendly interface, open-source foundation, and dedication to privacy.

For any further questions or to explore more about Incognfto's functionalities, please don't hesitate to ask. We are enthusiastic about assisting and providing a deeper understanding of how Incognfto, backed by the powerful Lit Protocol, empowers NFT owners and enthusiasts on their journey through the dynamic and exciting world of NFTs. If you are eager to learn more, you can find additional information [here](https://github.com/spheronFdn/incognfto/blob/main/README.md).

# Resources

[**Incognfto Readme**](https://github.com/spheronFdn/incognfto/blob/main/README.md)

[**Spheron Browser SDK Documentation**](https://docs.spheron.network/sdk/browser/)

[**Spheron Storage SDK Documentation**](https://docs.spheron.network/sdk/storage/)

[**LIT Protocol Documentation**](https://developer.litprotocol.com/whatIsLit)