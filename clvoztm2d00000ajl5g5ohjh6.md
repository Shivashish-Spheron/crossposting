---
title: "Nvidia's Blackwell: What You Need To Know About The Next Generation Of GPUs"
seoTitle: "What You Need To Know About The Next Generation 
Of Nvidia GPU"
seoDescription: "Ideal for gaming, AI research, and enterprise use cases, Blackwell sets a new standard in GPU technology. Stay ahead in the competitive GPU race with Nvidia"
datePublished: Thu May 02 2024 08:37:34 GMT+0000 (Coordinated Universal Time)
cuid: clvoztm2d00000ajl5g5ohjh6
slug: nvidias-blackwell-what-you-need-to-know-about-the-next-generation-of-gpus
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1714638726519/fd33a2e8-92d8-4fb5-bf83-4732c284cc75.png
tags: ai, artificial-intelligence, nvidia, web3, gpu, spheron, blackwell

---

Nvidia revealed its newest GPU lineup during [GTC 2024](https://www.nvidia.com/gtc/), which they’ve named Blackwell. It highlights multiple high-level alterations in hardware architecture, design, and pricing.

The initial release from the Blackwell line, GB200, is anticipated to be available later this year. With the huge success of Nvidia’s “Ampere” and “Hopper” series, this next generation of chips with 2 reticle-sized GPUs, the Blackwell gen, is set to take the stage this year.

![](https://lh7-us.googleusercontent.com/ROY5Cngu9yIJ-7m_PyEk0ycSkPZ6oEUr0vjj4bTWOibQ1p_1WAoHPhwFDZWBt-_XRzhWYZs1hrBZuiCMx0Abuq2mH9xAB7i_9KI2GRzJB5dy5vfhN4oF3p1ep7VKcawHEyt6PkhB6MxGytS_-8gvWBE align="left")

In 2023, Nvidia held an [impressive 82% share](https://www.investing.com/academy/statistics/nvidia-facts-and-statistics/) of the GPU market. The company’s revenue skyrocketed by 265% compared to the previous year, primarily driven by robust sales of AI chips designed for servers, notably the “Hopper” series like the H100. The latest chips can drive revenue to extraordinary levels.

## Blackwell’s transformative tech

Blackwell has launched six new cutting-edge technologies to revolutionize the GPU industry. These technologies include a custom-built four-nanometer manufacturing process developed by Taiwan Semiconductor Manufacturing Co. Ltd, which will form the basis of its next-generation GPU. This GPU features two-reticle-limit GPU dies connected by a 10-terabyte-per-second chip-to-chip link, creating a single, unified GPU.

Furthermore, Nvidia has unveiled its second-generation Transformer Engine, which incorporates micro-tensor scaling support and dynamic range management algorithms integrated within the Nvidia TensorTT-LLM and NeMo Megatron frameworks. These upgrades enable the support of larger computing algorithms, and AI model sizes with four-bit floating point AI inference, making it one of the most advanced technologies in the field.

The chips incorporate the [fifth-generation NVLink](https://www.nvidia.com/en-us/data-center/nvlink/) network switch to provide up to 1.8 terabits per second of bidirectional throughput per GPU. This switch provides faster communications among up to 576 GPUs in one node, which can power more complex LLMs than possible.

## **Look Inside the Technological Architecture**

[![](https://cdn.hashnode.com/res/hashnode/image/upload/v1714636381251/fd0846a7-2c35-4c2f-a9b4-bd8edc58035a.png align="center")](https://resources.nvidia.com/en-us-blackwell-architecture)

### **1\. A New Class of AI Superchips**

The Blackwell-architecture GPUs boast an impressive 208 billion transistors manufactured using a cutting-edge custom-built TSMC 4NP process. Each Blackwell product is equipped with two reticle-limited dies, seamlessly connected by a lightning-fast 10 terabytes per second (TB/s) chip-to-chip interconnect, resulting in a unified single GPU that's second to none.

### **2\. Second-Generation Transformer Engine**

The second-generation Transformer Engine uses custom [Blackwell Tensor Core](https://www.nvidia.com/en-in/data-center/tensor-cores/) technology combined with NVIDIA® TensorRT™-LLM and NeMo™ Framework innovations to accelerate inference and training for large language models (LLMs) and Mixture-of-Experts (MoE) models.

To supercharge inference of MoE models, [Blackwell Tensor Cores](https://www.nvidia.com/en-in/data-center/tensor-cores/) add new precisions, including new community-defined microscaling formats, giving high accuracy and ease of replacement for larger precisions. The Blackwell Transformer Engine utilizes fine-grain scaling techniques called micro-tensor scaling, to optimize performance and accuracy enabling 4-bit floating point (FP4) AI. This doubles the performance and size of next-generation models that memory can support while maintaining high accuracy.

### **3\. Secure AI**

Blackwell is the ultimate solution for safeguarding sensitive data and AI models from unauthorized access. It boasts the industry's first TEE-I/O capable GPU, providing the most performant confidential compute solution with TEE-I/O capable hosts and inline protection over NVIDIA® NVLink®. Blackwell's Confidential Computing offers nearly identical throughput performance compared to unencrypted modes, ensuring that even the largest models can be secured in a performant way. Enterprises can now confidently protect their AI intellectual property (IP) while enabling confidential AI training, inference, and federated learning.

### **4\. NVLink and NVLink Switch**

Swift and seamless communication among every [GPU](https://www.spheron.network/) within a server cluster is crucial to unlocking the full potential of exascale computing and trillion-parameter AI models. NVIDIA's fifth-generation NVLink interconnect is here to deliver that. With the ability to scale up to 576 GPUs, it unleashes accelerated performance for trillion- and multi-trillion-parameter AI models.

The [NVIDIA NVLink Switch Chip](https://www.nvidia.com/en-in/data-center/nvlink/) is the key to this breakthrough, with its capability to enable 130TB/s of GPU bandwidth in one NVL72 NVLink domain. And with 4X bandwidth efficiency and NVIDIA Scalable Hierarchical Aggregation and Reduction Protocol (SHARP)™ FP8 support, it's a game-changer. Not to mention, the NVIDIA NVLink Switch Chip supports clusters beyond a single server at the same impressive 1.8TB/s interconnect. Multi-server clusters with NVLink scale GPU communications are balanced with increased computing so that NVL72 can support 9X GPU throughput compared to a single eight-GPU system.

### **5\. Decompression Engine**

CPUs have been the norm for compute in the world of data analytics and database workflows. However, accelerated data science offers a game-changing opportunity to enhance the performance of end-to-end analytics significantly. This can lead to faster value generation and reduced costs. It is important to note that databases, such as Apache Spark, play a vital role in managing, processing, and analyzing vast data for data analytics.

Blackwell’s Decompression Engine and ability to access massive amounts of memory in the [NVIDIA Grace™ CPU](https://www.nvidia.com/en-in/data-center/grace-cpu/) over a high-speed link—900 gigabytes per second (GB/s) of bidirectional bandwidth—accelerate the full pipeline of database queries for the highest performance in data analytics and data science. It supports the latest compression formats like LZ4, Snappy, and Deflate.

### **6\. Reliability, Availability, and Serviceability (RAS) Engine**

Blackwell has taken a step further by integrating a dedicated Reliability, Availability, and Serviceability (RAS) Engine into its system. This RAS Engine, powered by NVIDIA's AI, can identify potential faults that might occur early on, thereby reducing downtime. It continuously monitors thousands of data points across hardware and software to predict and intercept sources of downtime and inefficiency. With this AI-powered predictive-management feature, Blackwell builds intelligent resilience that saves time, energy, and computing costs.

NVIDIA's RAS Engine provides in-depth diagnostic information to identify areas of concern and plan maintenance. This engine is designed to reduce turnaround time by quickly localizing the source of issues and facilitating effective remediation, thereby minimizing downtime.

## B100 Configuration

The B100 is an outstanding accelerator specifically designed to enhance computing performance drastically. Boasting an 8Gbps HBM3E memory clock, this device ensures lightning-fast data processing. With a whopping 8TB per second memory bandwidth, it can efficiently handle vast amounts of data. The accelerator comes equipped with 192GB of VRAM, divided into two 96GB units, allowing it to handle even the most complex tasks easily.

In addition, the B100 features NVLink 5, which enables data transfers of up to 1800GB per second, and PCIe 6.0, which adds another 256GB per second. This guarantees seamless communication with other components, making it an incredibly reliable tool for enhancing computing operations. Built with 208 billion transistors (2x104B), this accelerator is a force to be reckoned with.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1714636717920/e5c392c7-c5d7-4200-aea4-a08146cbbd45.png align="center")

Operating with a total power draw of 700W, the B100 is surprisingly energy-efficient, thanks to its TSMC 4NP manufacturing process. It uses the SXM-Next interface for connectivity and is based on the Blackwell architecture, which makes it an incredibly powerful tool for boosting computing performance with efficiency and speed. Moreover, the B100 is compatible with air cooling, making it a flexible option for deployment without the need for advanced cooling systems.

## B200 Configuration

It is important to note that the B200 and B100 models are extremely alike in terms of their technical specifications and performance. Both models have been engineered as discrete accelerators for advanced computing tasks, equipped with an 8Gbps HBM3E memory clock to ensure rapid data processing. They boast a memory bandwidth of 8TB per second and 192GB of VRAM divided into two 96GB units, making them highly proficient at handling complex tasks that require extensive data processing.

Regarding Tensor operations, which are essential for mathematical processing and deep learning tasks, the B200 model has a clear advantage over B100. It has proven to be superior in many areas, including 9 PFLOPS for FP4 Dense Tensor calculations, 4.5 P(FL)OPS for INT8/FP8 Dense Tensor, 2.2 PFLOPS for FP16 Dense Tensor, 1.1 PFLOPS for TF32 Dense Tensor, and 40 TFLOPS for FP64 Dense Tensor operations. This clearly shows that the B200 model is the preferable choice for those seeking higher efficiency and power in advanced computing tasks, especially in AI and deep learning fields.

Furthermore, both models feature robust connectivity options, including NVLink 5 at 1800GB/sec and PCIe 6.0 at 256GB/sec, ensuring seamless data transfer capabilities. With a GPU transistor count of 208 billion (2x104B), they demonstrate the high level of technological sophistication embedded in their design. Despite their powerful performance, they maintain a total power consumption of 1000W, reflecting their energy-efficient design achieved through the TSMC 4NP manufacturing process.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1714636811156/5c5da15c-3a7f-42dc-8313-4acb88dc19f7.png align="center")

When comparing these two models, it is evident that their similarities extend across most technical aspects, including their Tensor flops performance. However, the B200 model has proven to be the superior choice for those seeking higher efficiency and power in advanced computing tasks, especially in AI and deep learning fields.

## GB200 Configuration

The GB200 is an absolute powerhouse, featuring the Grace Blackwell Superchip that runs at a blazing fast 8Gbps with HBM3E memory clock. It has an enormous memory bandwidth of 2x8TB per second and 384GB of VRAM configured as 2x2x96GB, making it more capable of handling demanding high-level computing tasks.

Its robust connectivity boasts 2x NVLink 5 interfaces for 1800GB per second data transfer and 2x PCIe 6.0 connections, adding 256GB per second. The core of the GB200 comprises two “Blackwell GPUs,” each with 416 billion transistors, indicating immense complexity and power. Despite its capabilities, it has a low power draw of just 2700W, thanks to the powerful TSMC 4NP manufacturing process.

The GB200 requires liquid cooling to operate efficiently and safely under heavy loads. Its Superchip interface and the Grace + Blackwell architecture make it a powerful tool for advanced computing needs, offering unmatched performance and efficiency.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1714636929745/16e6b45c-d458-4d12-901d-9bbd027aba3f.png align="center")

Jensen, CEO of Nvidia, described the scenario, the efficiency, and the power of different GPUs in training a GPT-4 model with 1.8 trillion parameters. Training such a model on A100 GPUs would require a massive setup of 25,000 units and take approximately 3 to 5 months to complete. In contrast, utilizing H100 GPUs for the same task significantly reduces the hardware requirement to 8,000 GPUs, with the training time narrowing to around 3 months. The B100 GPUs further optimize this process, needing only 2,000 GPUs to achieve the same goal within a similar timeframe of about 3 months. This comparison determines the potency of this GPU technology, showcasing the B100’s superior efficiency and capability in handling extensive AI model training tasks within a condensed period.

## Nvidia B100 vs. B200 vs. GB200

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1714637427553/41152e57-4c2f-459d-869b-402d55ab8388.png align="center")

## Conclusion

With groundbreaking technologies like the second-gen Transformer Engine, enhanced security measures, improved reliability via RAS engines, and efficient decompression engines, Blackwell delivers tangible benefits for various applications ranging from gaming to enterprise use cases centered around artificial intelligence (AI). Specifically, integrating fourth-order tensor cores allows for unparalleled improvements in AI computational density, delivering better performance and energy efficiency simultaneously.

Among the three configurations presented – B100, B200, and GB200 - users may find varying suitability depending on their specific requirements. While all three offer remarkable performance gains, there appears to be a tradeoff between raw performance and energy efficiency.

As enterprises adopt increasingly sophisticated AI solutions, Nvidia's Blackwell family stands poised to become an integral infrastructure driving innovation and growth. By capitalizing on past achievements and introducing novel architectural designs, Nvidia positions itself competitively against rivals vying for dominance in the rapidly evolving GPU space.