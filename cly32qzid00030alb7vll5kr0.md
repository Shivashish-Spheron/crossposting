---
title: "Maximize Security Using NVIDIA Confidential Computing"
seoTitle: "Maximize Security Using NVIDIA Confidential Computing"
seoDescription: "NVIDIA Confidential Computing, provides a hardware-based solution to securely process data and code in use, preventing unauthorized access and modification."
datePublished: Sat Jun 29 2024 18:30:00 GMT+0000 (Coordinated Universal Time)
cuid: cly32qzid00030alb7vll5kr0
slug: maximize-security-using-nvidia-confidential-computing
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1719830810790/b6119b95-ff64-419a-b076-ef8573a44ed0.png
tags: blockchain, nvidia, web3, gpu, computing, decentralization, cybersecurity-1, spheron, confidential-compute

---

Recently, NVIDIA introduced a pioneering security feature within the Hopper architecture to safeguard sensitive data, AI models, and applications. This new feature, named [NVIDIA Confidential Computing](https://www.nvidia.com/en-us/data-center/solutions/confidential-computing/), provides a hardware-based solution to securely process data and code in use, preventing unauthorized access and modification.

Sensitive data is vulnerable to external attacks and internal threats, whether deployed on-premises, at the edge, or in the cloud. NVIDIA Confidential Computing ensures that your most critical data and code are secure while enjoying the advanced acceleration of NVIDIA H200 and H100 Tensor Core GPUs.

## **Understanding NVIDIA Confidential Computing**

In simple terms, "confidential computing" (CC) protects data-in-use by performing computation in a trusted execution environment (TEE) that is both hardware-based and attested.

The NVIDIA H200 and H100 GPUs feature a CVM (confidential virtual machine) TEE on the CPU, anchored in an on-die root of trust (RoT). When booted in CC-On mode, hardware protections are enabled to ensure the confidentiality and integrity of code and data. Here, "confidentiality" means preventing attackers from accessing data or code, and "integrity" means preventing modification during execution.

## **How It Works**

1. **Chain of Trust**: A secure and measured boot sequence establishes a chain of trust.
    
2. **Secure Connection**: An SPDM (Security Protocol and Data Model) session facilitates a secure connection to the driver in a CPU TEE.
    
3. **Attestation Report**: A cryptographically signed attestation report verifies system integrity.
    
4. **GPU Authentication**: The GPU must be authenticated as a legitimate NVIDIA GPU that supports confidential computing, involving a device-unique private key and a certified public key. The GPU must not be revoked for CC, and the attestation report must be verified.
    
5. **Secure Channel Establishment**: Upon successful verification, the NVIDIA driver in the CVM establishes a secure channel with the GPU hardware TEE using a session key to transfer data, perform computation, and retrieve results. Communication between the CVM and GPU occurs through a shared memory region outside the CVM, with AES-GCM encryption to prevent the host system from reading this communication.
    
6. **Memory Management**: The GPU copies and decrypts all inputs to its internal memory, running everything in plaintext while blocking direct access. Performance counters are disabled to prevent side-channel attacks.
    

This process extends a confidential computing environment from a CVM (or a secure enclave) to a GPU, with attestation, encrypted communication, and memory isolation.

## **Benefits and Positive Impacts**

NVIDIA Confidential Computing offers several significant benefits:

* **Hardware-Based Security and Isolation**: Achieve full isolation of virtual machines (VMs) in any environment—on-premises, at the edge, or in the cloud. The entire workload is secured with built-in hardware firewalls that offer unprecedented protection.
    
* **Verifiability with Device Attestation**: Ensure only authorized end users can deploy data and code for execution in the H200 or H100's TEE. Device attestation verifies the authenticity of the NVIDIA GPU, ensuring firmware integrity and proper updates.
    
* **Protection from Unauthorized Access**: Sensitive data, AI workloads, and intellectual property are protected, with confidentiality and integrity always preserved. Unauthorized entities—including the hypervisor, cloud provider, host operating system, and anyone with physical access—are blocked from viewing or modifying AI applications and data during execution.
    
* **No Application Code Change**: The confidential computing feature works seamlessly without requiring code changes for GPU-accelerated workloads.
    

Confidential computing-enabled GPUs open up a variety of use cases where security, privacy, and regulatory compliance are crucial. For example, intellectual property protection for proprietary AI models is possible even when distributed and deployed at scale on shared or remote infrastructure.

Privacy and confidentiality are preserved in AI training and inference, especially in industries like healthcare, finance, and the public sector, where data is sensitive and regulated. Secure collaboration between multiple parties is facilitated for building and improving AI models across participating sites, applicable to use cases like medical imaging, drug development, and fraud detection. Organizations, governments, and individuals can outsource AI workloads to a cloud provider while ensuring protection from the underlying infrastructure.

As the demand for GPU resources continues to surge, especially for AI and machine learning applications, ensuring the security and ease of access to these resources has become paramount.

[**Spheron’s**](https://www.spheron.network/) decentralized architecture aims to democratize access to the world’s untapped GPU resources and strongly emphasizes security and user convenience. Let’s unpack how Spheron protects your GPU resources and data and ensures that the future of decentralized compute is both efficient and secure.

*Interested in learning more about Spheron’s network capabilities and user benefits?*[***Review the whitepaper in full***](https://www.spheron.network/whitepaper/)*.*