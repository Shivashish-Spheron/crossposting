---
title: "Best Practices for LLM Inference Performance Monitoring"
seoTitle: "Best Practices for LLM Inference Performance Monitoring"
seoDescription: "This guide delves into LLM inference performance monitoring, explaining how inference works, the metrics used to measure an LLM’s speed, and the performance"
datePublished: Mon Jun 10 2024 18:30:00 GMT+0000 (Coordinated Universal Time)
cuid: clxkbufsx001w09la2xnb8gng
slug: best-practices-for-llm-inference-performance-monitoring
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1718703674533/a98b8f4d-9456-401c-8e56-795fed5b7461.png
tags: ai, artificial-intelligence, performance, monitoring, best-practices, blockchain, web3, gpu, spheron, llm

---

With a growing number of large language models (LLMs) available, selecting the right model is crucial for the success of your generative AI strategy. An incorrect choice can lead to significant time and resource wastage and potentially a premature conclusion that AI cannot enhance your organization’s efficiency and productivity.

There are several methods to determine an LLM’s capabilities, such as benchmarking, as detailed in our previous guide. However, one of the most applicable to real-world use is measuring a model’s inference—how quickly it generates responses. This guide delves into LLM inference performance monitoring, explaining how inference works, the metrics used to measure an LLM’s speed, and the performance of some of the most popular models on the market.

## What is LLM Inference Performance Monitoring, and Why is it Important?

LLM inference is entering a prompt and generating a response from an LLM. It involves the language model drawing conclusions or making predictions to generate an appropriate output based on the patterns and relationships learned during training.

LLM inference performance monitoring measures a model's speed and response times. This is essential for assessing an LLM’s efficiency, reliability, and consistency—critical factors in determining its ability to perform in real-world scenarios and provide the intended value within an acceptable timeframe. Without proper evaluation means, organizations and individuals face blind spots. They might incorrectly assess the suitability of a language model, leading to wasted time and resources as the model proves unsuitable for its intended use case.

## How LLM Inference Works

It is important to know how an LLM performs inference to understand the metrics used to measure a model’s latency. This process involves two stages: the prefill phase and the decoding phase.

In the prefill phase, the LLM processes the text from a user’s input prompt by converting it into a series of prompts or input tokens. A token represents a word or a portion of a word. A token is approximately 0.75 words or four characters in the English language. The tokenizer, which divides text into tokens, varies between models. Each token is then turned into a vector embedding, a numerical representation that the model can understand and use to make inferences. The LLM processes these embeddings to generate an appropriate output for the user.

During the decoding phase, the LLM generates a series of vector embeddings representing its response to the input prompt. These are converted into completion or output tokens, which are generated one at a time until the model reaches a stopping criterion, such as a token limit or a stop word. At this point, a special end token is generated to signal the end of token generation. As LLMs generate one token per forward propagation, the number of propagations required to complete a response equals the number of completion tokens.

## Important LLM Inference Performance Metrics

Latency and throughput are key metrics to consider when evaluating the inference capabilities of a large language model.

#### Latency

Latency measures the time taken for an LLM to generate a response to a user’s prompt. It provides a way to evaluate a language model’s speed and is crucial for forming a user’s impression of how fast or efficient a generative AI application is. Low latency is particularly important for real-time interactions, such as chatbots and AI copilots, but less so for offline processes. Several ways to measure latency include:

* **Time To First Token (TTFT):** The time it takes for the user to start receiving a response after entering their prompt. TTFT is influenced by factors like network speed, input sequence length, and model size.
    
* **Time Per Output Token (TPOT):** The average time it takes to generate a completion token for each user query. Also referred to as inter-token latency (ITL).
    
* **Total Generation Time:** The end-to-end latency from when a prompt is entered to when the user receives the completed output. This can be calculated as follows:
    
    Total Generation Time=TTFT+(TPOT×number of generated tokens)\\text{Total Generation Time} = \\text{TTFT} + (\\text{TPOT} \\times \\text{number of generated tokens})Total Generation Time=TTFT+(TPOT×number of generated tokens)
    

An LLM’s total generation time varies based on factors such as output length, prefill time, and queuing time. Additionally, the concept of a cold start—when an LLM is invoked after being inactive—affects latency measurements, particularly TTFT and total generation time. It’s crucial to note whether inference monitoring results specify whether they include cold start time.

#### Throughput

Throughput measures how many requests an LLM can process or how much output it can produce in a given time span. Throughput is typically measured in:

* **Requests per Second:** Dependent on the model’s total generation time and how many requests are made simultaneously.
    
* **Tokens per Second:** A more common metric for measuring throughput, it can refer to either total tokens per second (both input and output tokens) or output tokens per second (only generated completion tokens).
    

Total tokens per second is considered the more definitive measure of model throughput, while output tokens per second is more relevant for real-time applications.

#### Request Batching

One effective method to increase an LLM’s throughput is batching, which involves collecting multiple inputs to process simultaneously. This approach makes efficient use of a GPU and improves throughput but can increase latency as users wait for the batch to process. Types of batching techniques include:

* **Static Batching:** Multiple prompts are gathered, and responses are generated when all requests in the batch are complete.
    
* **Continuous Batching:** Also known as in-flight batching, this method groups requests at the iteration level. Once a request is completed, a new one replaces it, enhancing compute efficiency.
    

Understanding and effectively monitoring LLM inference performance is critical for deploying the right model to meet your needs, ensuring efficiency, reliability, and consistency in real-world applications.

## Challenges of LLM Inference Performance Monitoring

Monitoring the inference performance of [large language models (LLMs)](https://en.wikipedia.org/wiki/Large_language_model) is crucial for understanding metrics such as latency and throughput. However, obtaining this data can be challenging due to several factors:

1. **Lack of Testing Consistency**: Differences in how inference tests are conducted can significantly impact the results. Variables such as the type and quantity of GPUs used, the number and nature of prompts, and whether the inference is conducted locally or through an API can all affect a model’s inference metrics. These inconsistencies make it difficult to perform like-for-like comparisons, as tests are often conducted under varying conditions.
    
2. **Different Token Lengths per Model**: Inference performance tests typically use token-based metrics like tokens per second. However, token lengths can vary between different LLMs, making it challenging to directly compare metrics across different models.
    
3. **Lack of Data**: In some cases, inference metrics may not be available for certain models because they haven’t been published by their vendors or sufficiently tested by independent researchers.
    

## How Do Popular LLMs Perform on These Metrics?

Having discussed the challenges of measuring LLM inference performance, let's examine how some popular models score on various inference metrics. AI research hub Artificial Analysis publishes ongoing performance and benchmark tests for widely used LLMs, focusing on three key metrics:

* **Throughput (tokens per second)**
    
* **Latency (total response time, TRT)**: The time it takes to output 100 tokens.
    
* **Latency (time to first chunk, TFCR)**: Used instead of TFTT because some API hosts send out chunks of tokens instead of individually.
    

For most models, the TRT and TFCR metrics are the mean average across multiple API hosts, except for Gemini Pro, Claude 2.0, and Mistral Medium. For the three OpenAI GPT models, the average is derived from OpenAI and Azure, while for Mixtral 8x7B and Llama 2 Chat, it’s based on eight and nine API hosting providers, respectively.

Here are some key results:

| Model | Throughput (tokens per second) | Latency (TRT) (seconds) | Latency (TFCR) (seconds) |
| --- | --- | --- | --- |
| Mixtral 8x7B | 95 | 2.66 | 0.6 |
| GPT-3.5 Turbo | 92 | 1.85 | 0.65 |
| Gemini Pro | 86 | 3.6 | 2.6 |
| Llama 2 Chat (70B) | 82 | 3.16 | 0.88 |
| Claude 2.0 | 27 | 4.8 | 0.9 |
| GPT-4 | 22 | 7.35 | 1.9 |
| GPT-4 Turbo | 20 | 7.05 | 1.05 |
| Mistral Medium | 19 | 6.2 | 0.3 |

Artificial Analysis also includes other measurements such as latency and throughput over time and inference costs. The site GPT For Work monitors the performance of APIs for several models from OpenAI and Anthropic, publishing average latency over a 48-hour period based on generating a maximum of 512 tokens, a temperature of 0.7, at 10-minute intervals, from three locations.

A more comprehensive study by machine learning operations organization Predera focuses on the Mistral Instruct and Llama 2 models, testing both 7B and 70B models. This study measures:

* Throughput (tokens per second)
    
* Throughput (requests per second)
    
* Average latency (seconds)
    
* Average latency per token (seconds)
    
* Average latency per output token (seconds)
    
* Total time (seconds)
    

Inference is performed using varying numbers of [NVIDIA L4 Tensor Core GPUs](https://www.nvidia.com/en-in/data-center/l4/), providing insights into each LLM’s scalability. Results are based on feeding each model 1,000 prompts.

#### 1 x L4 GPU

| Model | Throughput (tokens per second) | Throughput (requests per second) | Average latency (seconds) | Average latency per token (seconds) | Average latency per output token (seconds) | Total time (seconds) |
| --- | --- | --- | --- | --- | --- | --- |
| Llama2-7B | 558.54 | 1.17 | 449.88 | 1.71 | 10.87 | 897.23 |
| Mistral-7B-instruct | 915.48 | 1.89 | 277.19 | 0.97 | 7.12 | 552.44 |

#### 2 x L4 GPUs

| Model | Throughput (tokens per second) | Throughput (requests per second) | Average latency (seconds) | Average latency per token (seconds) | Average latency per output token (seconds) | Total time (seconds) |
| --- | --- | --- | --- | --- | --- | --- |
| Llama2-7B | 1265.17 | 2.65 | 179.85 | 0.63 | 3.81 | 397.65 |
| Mistral-7B-instruct | 1625.08 | 3.35 | 153.09 | 0.50 | 2.65 | 339.51 |

#### 4 x L4 GPUs

| Model | Throughput (tokens per second) | Throughput (requests per second) | Average latency (seconds) | Average latency per token (seconds) | Average latency per output token (seconds) | Total time (seconds) |
| --- | --- | --- | --- | --- | --- | --- |
| Llama2-7B | 1489.99 | 3.12 | 147.36 | 0.48 | 2.57 | 324.71 |
| Mistral-7B-instruct | 1742.70 | 3.59 | 136.49 | 0.44 | 2.68 | 285.03 |

#### 8 x L4 GPUs

| Model | Throughput (tokens per second) | Throughput (requests per second) | Average latency (seconds) | Average latency per token (seconds) | Average latency per output token (seconds) | Total time (seconds) |
| --- | --- | --- | --- | --- | --- | --- |
| Llama2-7B | 1401.18 | 2.93 | 153.09 | 0.50 | 2.65 | 339.51 |
| Mistral-7B-instruct | 1570.70 | 3.24 | 149.67 | 0.48 | 2.90 | 316.74 |
| Llama2-70B | – | 1.00 | 475.59 | 1.62 | 9.21 | 996.86 |

These results show that inference metrics improve as more GPUs are utilized up to a point. Performance tends to degrade beyond four GPUs, indicating that the models are only scalable to a certain extent. The [Llama2-70B](https://ollama.com/library/llama2:70b) model is included only for the 8-GPU configuration due to its large parameter size, requiring sufficient GPU space to store its parameters.

## Compute-Bound vs. Memory-Bound Inference

Inference speed is heavily influenced by both the characteristics of the hardware instance on which a model runs and the nature of the model itself. A model or a phase of a model that demands significant computational resources will be constrained by different factors compared to one that requires extensive data transfer between memory and storage. Thus, the hardware's computing speed and memory availability are crucial determinants of inference speed. When these factors restrict inference speed, it is described as either compute-bound or memory-bound inference.

### Compute-Bound Inference

Compute-bound inference occurs when the computational capabilities of the hardware instance limit the inference speed. The type of processing unit used, such as a CPU or GPU, dictates the maximum speed at which calculations can be performed. Even with the most advanced software optimization and request batching techniques, a model's performance is ultimately capped by the processing speed of the hardware. The nature of the calculations required by a model also influences its ability to fully utilize the processor's compute power.

For instance, the prefill phase of a large language model (LLM) is typically compute-bound. During this phase, the speed is primarily determined by the processing power of the GPU. The prefill phase can process tokens in parallel, allowing the instance to leverage the full computational capacity of the hardware. GPUs, which are designed for parallel processing, are particularly effective in this context.

### Memory-Bound Inference

On the other hand, memory-bound inference is when the inference speed is constrained by the available memory or the memory bandwidth of the instance. Different processors have varying data transfer speeds, and instances can be equipped with different amounts of random-access memory (RAM). The size of the model, as well as the inputs and outputs, also play a significant role. Processing large language models (LLMs) involves substantial memory and memory bandwidth because a vast amount of data needs to be loaded from storage to the instance and back, often multiple times.

The decoding phase of inference is generally considered memory-bound. This phase involves sequential calculations for each output token. Typically, key-value (KV) caching stores data after each token prediction, preventing GPU redundant calculations. Consequently, the inference speed during the decode phase is limited by the time it takes to load token prediction data from the prefill or previous decode phases into the instance memory. In such cases, upgrading to a faster GPU will not significantly improve performance unless the GPU also has higher data transfer speeds.

### Identifying Your Bottleneck

If you find your inference speed lacking, it is crucial to identify the bottleneck. Without pinpointing the bottleneck, you risk choosing ineffective solutions that yield minimal performance gains or incur unnecessary costs. For example, upgrading from an NVIDIA A100 with 80 GB of memory to an H100 with the same memory capacity would be an expensive choice with little improvement if your operation is memory-bound. That's why on-demand DePIN for GPU is the need of the hour.

To address these growing resource needs, [Spheron](https://www.spheron.network/) has created a groundbreaking global compute network that ensures the efficient, cost-effective, and equitable distribution of GPU resources. Now, anyone can earn passive returns by lending their excess GPU power to Spheron Network – and become a vital part of the decentralized AI revolution!

[**Become a Spheron Compute Provider**](https://b4t4v7fj3cd.typeform.com/spheronnode?typeform-source=www.spheron.network)

[Spheron’s decentralized market](https://b4t4v7fj3cd.typeform.com/spheronnode?typeform-source=www.spheron.network) connects you to a worldwide user base ready to utilize the provider's excess compute power, no matter where they are.

## Spheron’s Decentralized Compute Network

At the heart of Spheron's protocol lies the Decentralized Compute Network (DCN), a distributed framework where independent providers supply GPU and compute resources. This network ensures resilience, scalability, and accessibility, catering to the diverse needs of AI and ML projects. Central to the DCN is the Matchmaking Engine, designed to connect GPU users with providers efficiently. In the meantime, we encourage you to [**review the whitepaper in full**](https://spheron.network/whitepaper).

## Conclusion

Inference performance monitoring provides valuable insights into an LLM’s speed and effectively compares models. However, selecting the most appropriate model for your organization’s long-term objectives should not rely solely on inference metrics. The latency and throughput figures can be influenced by various factors, such as the type and number of GPUs used and the nature of the prompt during tests. Additionally, different recorded metrics can complicate a comprehensive understanding of a model’s capabilities.

Furthermore, benchmarking tests like HumanEval and MMLU, which assess specific skills such as coding abilities and natural language understanding, offer additional insights into a model's performance. Combining these benchmarks with inference speed measurements provides a robust strategy for identifying the best LLM for your needs.

## Join Spheron's Private Testnet and Get Complimentary Credits for your Projects

As a developer, you now have the opportunity to build on Spheron's cutting-edge technology using free credits during our private testnet phase. This is your chance to experience the benefits of decentralized computing firsthand at no cost to you.

If you're an AI researcher, deep learning expert, machine learning professional, or large language model enthusiast, we want to hear from you! Participating in our private testnet will give you early access to Spheron's robust capabilities and receive complimentary credits to help bring your projects to life.

Don't miss out on this exciting opportunity to revolutionize how you develop and deploy applications. Sign up now by filling out this form: [https://b4t4v7fj3cd.typeform.com/to/Jp58YQB2](https://b4t4v7fj3cd.typeform.com/to/Jp58YQB2)

Join us in pushing the boundaries of what's possible with decentralized computing. We look forward to working with you!