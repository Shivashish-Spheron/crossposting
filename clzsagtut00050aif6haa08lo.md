---
title: "Llama 3.1 In-Depth Analysis: Cutting Through the Noise"
seoTitle: "Llama 3.1 In-Depth Analysis: Cutting Through the Noise"
seoDescription: "The Llama 3.1 405B model generated a lot of buzz, but it didn’t fully register with us until Andrej Karpathy’s tweet brought it to our attention. As a co-fo"
datePublished: Tue Aug 13 2024 10:37:42 GMT+0000 (Coordinated Universal Time)
cuid: clzsagtut00050aif6haa08lo
slug: llama-31-in-depth-analysis-cutting-through-the-noise
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1723549374155/e3744dfa-f048-4c5e-a3cc-5373be557866.png
tags: blockchain, meta, web3, gpu, decentralization, spheron, llama, llama31, llama-31

---

The Llama 3.1 405B model generated a lot of buzz, but it didn’t fully register with us until Andrej Karpathy’s tweet brought it to our attention. As a co-founder of OpenAI with deep roots in AI safety, he's worth following closely.

%[https://x.com/karpathy/status/1815842603377779140] 

His mention of Llama 3.1 prompted us to explore this model further. [The paper is a whopping 92 pages—no easy feat](https://scontent.fblr2-2.fna.fbcdn.net/v/t39.2365-6/453304228_1160109801904614_7143520450792086005_n.pdf?_nc_cat=108&ccb=1-7&_nc_sid=3c67a6&_nc_ohc=7M_zSsIlAVkQ7kNvgFwF5jM&_nc_ht=scontent.fblr2-2.fna&oh=00_AYD-s7cAtRDnd6vFX7WlgVZgUWj3LiGp_Cbr2qy6ieZk2A&oe=66C0DFC7). Llama 3.1 comes in three sizes, but we will focus primarily on the largest and most powerful: the 405-billion parameter model. Meta wasn’t exaggerating when they claimed it rivals top-tier language models like GPT-4.

If you’re curious, you can try Llama 3.1 for free at Hugging Face: [Hugging Chat](https://huggingface.co/chat/).

## **Benchmark Analysis**

Here is how Llama 3.1 405B compares to [GPT-4](https://openai.com/index/gpt-4/), [GPT-4o](https://openai.com/index/hello-gpt-4o/), and [Claude 3.5 Sonnet](https://www.anthropic.com/news/claude-3-5-sonnet) on traditional benchmarks.

[![](https://scontent.fblr2-2.fna.fbcdn.net/v/t39.2365-6/451735590_1030734788570365_1093008500142144333_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=2ovZcvV65NcQ7kNvgFDGUpE&_nc_ht=scontent.fblr2-2.fna&oh=00_AYBsEj7TAqBt8aWcs9A2tvCL706QIvW-OMGX1FD46mPewQ&oe=66D55DFE align="left")](https://ai.meta.com/blog/meta-llama-3-1/)

Here is how [Gemma 2 9B IT](https://huggingface.co/google/gemma-2-9b-it), [Mistral 7B Instruct](https://mistral.ai/news/announcing-mistral-7b/), [Llama 3.1 70B](https://huggingface.co/meta-llama/Meta-Llama-3.1-70B), [Mixtral 8x22b](https://huggingface.co/mistralai/Mixtral-8x22B-v0.1) Instruct, and GPT 3.5 Turbo are on traditional benchmarks.

[![](https://scontent.fblr2-2.fna.fbcdn.net/v/t39.2365-6/452673884_1646111879501055_1352920258421649752_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=4elzBLQr1qgQ7kNvgHtWnrC&_nc_ht=scontent.fblr2-2.fna&oh=00_AYDxQa4Qh2VLF2OsCpXvKUswKYdEY6GM-fK0GbuKjya3lg&oe=66D57BA8 align="left")](https://ai.meta.com/blog/meta-llama-3-1/)

### **Benchmark Comparison in Numbers - LLaMA 3.1 (405B) vs. Other LLMs:**

---

### **General Performance**

* **MMLU (0-shot, CoT):** LLaMA 3.1 (405B) scores **88.6**, outperforming most models, including GPT-4 (85.4) and Nemotron 4 (78.7). GPT-4 Omni and Claude 3.5 Sonnet score slightly higher at **88.7** and **88.3**, respectively.
    
* **MMLU PRO (5-shot, CoT):** LLaMA 3.1 (405B) scores **73.3**, surpassing Nemotron 4 (62.7) and GPT-4 (64.8). Claude 3.5 Sonnet scores the highest at **77.0**.
    
* **IFEval:** LLaMA 3.1 (405B) scores **88.6**, leading Nemotron 4 (85.1) and GPT-4 (84.3). Claude 3.5 Sonnet edges slightly higher with a score of **88.0**.
    

### **Code Generation**

* **HumanEval (0-shot):** LLaMA 3.1 (405B) scores **89.0**, surpassing GPT-4 (86.6) and Nemotron 4 (80.9). Claude's 3.5 Sonnet scores the highest at **92.0**.
    
* **MBPP EvalPlus (base) (0-shot):** LLaMA 3.1 (405B) scores **88.6**, outperforming Nemotron 4 (72.8) and GPT-4 (83.6). Claude 3.5 Sonnet takes the lead with **90.5**.
    

### **Mathematics**

* **GSM8K (8-shot, CoT):** LLaMA 3.1 (405B) scores **96.8**, leading Nemotron 4 (92.3) and GPT-4 (94.2). Claude 3.5 Sonnet matches GPT-4 Omni with a score of **96.4**.
    
* **MATH (0-shot, CoT):** LLaMA 3.1 (405B) scores **73.8**, ahead of Nemotron 4 (41.1) and GPT-4 (64.5). Claude 3.5 Sonnet scores **71.1**.
    

### **Reasoning**

* **ARC Challenge (0-shot):** LLaMA 3.1 (405B) scores **96.9**, outperforming Nemotron 4 (94.6) and GPT-4 (96.4). GPT-4 Omni and Claude 3.5 Sonnet lead with **96.7** each.
    
* **GPQA (0-shot, CoT):** LLaMA 3.1 (405B) scores **51.1**, significantly higher than GPT-4 (41.4) and Claude 3.5 Sonnet (59.4).
    

### **Tool Use**

* **BFCL:** LLaMA 3.1 (405B) scores **88.5**, slightly lower than GPT-4 Omni (88.3) and Claude 3.5 Sonnet (90.2).
    
* **Nexus:** LLaMA 3.1 (405B) scores **58.7**, leading GPT-4 (50.3) and Nemotron 4 (45.7). GPT-4 Omni performs better with **56.1**.
    

### **Long Context**

* **ZeroSCROLLS/QuALITY:** LLaMA 3.1 (405B) scores **95.2**, on par with GPT-4 Omni and Claude 3.5 Sonnet, all scoring **90.5**.
    
* **InfiniteBench/**[**En.MC**](http://En.MC)**:** LLaMA 3.1 (405B) scores **83.4**, leading GPT-4 (72.1) but lower than GPT-4 Omni (82.5).
    
* **NIH/Multi-needle:** LLaMA 3.1 (405B) scores **98.1**, outperforming GPT-4 Omni and GPT-4 Omni (100.0), and Claude 3.5 Sonnet with **90.8**.
    

### **Multilingual**

* **Multilingual MGSM (0-shot):** LLaMA 3.1 (405B) scores **91.6**, surpassing Nemotron 4 (85.9) and GPT-4 (85.9). GPT-4 Omni and Claude 3.5 Sonnet both perform slightly higher with **90.5**.
    

While these benchmarks don’t fully capture the nuanced differences between the models, they show that Meta’s new "open-source" model is at least on par with GPT-4, if not superior. However, it lacks the advanced speech input and output features of GPT-4 Omni, which isn’t widely accessible yet.

We now have a downloadable model as good as—or better than—GPT-4, which many thought would take years to develop. Meta continues to argue that this series of models follows a "responsible path" toward artificial general intelligence (AGI). We remain skeptical about the "responsible" aspect.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1723541137742/a5a0cdfa-450f-4466-afbb-d4dbcbb5e8a2.png align="center")

## **Open-Source Claim**

According to the official open-source initiative, true open-source AI must include details about the training data’s provenance. The Llama 3.1 paper, however, only mentions that the data comes "from a variety of data sources," which falls short of the true open-source definition.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1723541193649/c5340e5c-eb6c-49e7-8d27-ac4109ec1901.png align="center")

<mark>We Created our dataset for pre-training, which involved collecting data from diverse sources, encompassing knowledge up to the end of 2023, as stated in the Llama 3.1 paper.</mark>

Even if another entity had the budget, it couldn’t replicate Llama 3.1 without knowing the exact data Meta used. Keep this in mind when Meta touts its commitment to open-source AI.

Although disappointed by the lack of transparency, we understand the challenges. According to a recent [New York Times article, acquiring LLM training data is increasingly difficult](https://www.nytimes.com/2024/07/19/technology/ai-data-restrictions.html). Platforms like Reddit and Twitter now charge for their data, and Meta likely didn’t have permission for all the data they used. But that’s a topic for another time.

## **AI Enhancing AI**

One recurring theme in the paper is how language models enhance the performance of other language models. For instance, Llama 2 was utilized to filter the data for training Llama 3. This is just one example; there are many more, making it plausible that Llama 3.1 is contributing to the development of Llama 4.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1723541451778/b39119a5-5972-4aaa-bd07-b746d46ec3b8.png align="center")

<mark>“To train a quality classifier based on Llama 2, we created a dataset of cleaned web documents, outlined quality criteria, and instructed Llama 2’s chat model to evaluate whether the documents met these criteria.”</mark>

This approach could be seen as an intelligence explosion, but it appears to be a methodical process of using AI to refine AI. While this isn’t a novel concept—many new models employ similar techniques—Llama 3.1 does it differently. They trained a code expert model to identify the highest quality human annotations for code.

## **Scaling Laws for Performance**

The paper offers insights into their process, down to the scaling laws they developed for next-token prediction loss and benchmark performance. Given their flop budget, they predicted how long it would take to run the GPUs to achieve the desired benchmark performance, and their predictions were remarkably accurate.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1723543261117/e8b07916-148f-43bb-92dd-033df1f12443.png align="center")

<mark>“This approach enables us to predict downstream task performance given a specific number of training flops for compute-optimal models.” according to the Llama 3.1 paper.</mark>

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1723541597010/9e51ed62-3570-44c0-b2c2-7df67410dfd5.png align="center")

## **Infrastructure, Scaling, and Data**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1723541668482/36377f19-1137-4bcb-b07b-bce8801230b7.png align="center")

The level of detail regarding infrastructure, scaling, and data is impressive. Llama 3.1 405B was trained on 16,000 H100 GPUs, each running at 700W TDP with 80GB HBM3, utilizing Meta’s Grand Teton AI server platform. The paper also discusses challenges like network oversubscription, load balancing, and power grid constraints due to temperature fluctuations.

They meticulously cleaned the data, eliminating overly apologetic tones, excessive emojis, and other unwanted elements. We suspect a similar approach was taken when training Elon Musk’s Grok LLM by [x.ai](http://x.ai), which is known for its sassy attitude and lack of apologies.

## **Reasoning and Mathematics**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1723541723448/abad3e49-8336-4346-8cac-94a3f284facf.png align="center")

For reasoning and mathematics, the paper defines reasoning as <mark>"the ability to perform multi-step computations and arrive at the correct final answer."</mark> However, they acknowledge a shortage of ground truth chains of thought in the training data, which are crucial for guiding the model through multi-step reasoning processes.

They also employed models like Llama 3 to verify reasoning steps, filtering out incorrect chains of thought in the training data. They used techniques like Monte Carlo research to generate valid reasoning traces for the most challenging prompts.

## **Adversarial Testing and Performance**

Llama 405B performs well but falls short compared to Claude 3.5 Sonnet in text generation. The paper notes that adversarial tests significantly degrade performance, which suggests that the model isn’t truly "thinking" about the questions.

<mark>“For mathematical reasoning and question answering, however, the adversarial performances are substantially lower than the non-adversarial performances.”</mark> as stated in the Llama 3.1 paper.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1723541802150/21d4349e-08a6-4ad9-8cb2-a8ffb5ec96fd.png align="center")

## **Data Contamination Issues**

The paper highlights significant data contamination in traditional benchmarks, which affects performance estimates. They found that contamination was a pervasive issue even with a higher threshold for word overlap between training data and test sets.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1723543723936/86059b99-705e-47b5-9589-730737254b21.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1723544638188/0f1c9929-1132-48ee-8b50-4d01aa27e17d.png align="center")

The contamination scores in the table actually downplay the issue. They omitted benchmarks from this chart when the clean set had too few examples or when the performance gains observed after cleaning the dataset were highly erratic. They also discussed the MMLU. Even when they set a higher threshold of an eight-word overlap between the training and test data, the contamination scores were so high that it was impossible to accurately estimate the performance gains. As a result, they couldn't properly gauge the extent to which contamination affected the MMLU scores.

## **Long-Context Capabilities**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1723541927488/1f2d75a8-8666-44e7-bc96-a5b8d0107768.png align="center")

Llama 405B excels in long-context tasks, with a context length of 128k tokens—equivalent to about 100,000 words or 200 pages. It outperforms GPT-4, GPT-4o, and Claude 3.5 Sonnet in tasks requiring extensive context analysis.

![None](https://miro.medium.com/v2/resize:fit:700/1*1q-AvHfe81j75wBDbf7Yqg.png align="left")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1723544561363/4c695d7e-a689-424f-866a-04bae7cac5e2.png align="center")

They used "InfiniteBENCH," a benchmark designed to test language models in superlong contexts, and Llama 3.1 significantly outperformed its rivals.

[![data_pie.png](https://github.com/OpenBMB/InfiniteBench/blob/main/figs/data_pie.png?raw=true align="left")](https://github.com/OpenBMB/InfiniteBench/blob/main/figs/data_pie.png)

Compared to other benchmarks, InfinityBENCH is 10 times longer than traditional benchmarking datasets and covers diverse domains.

## **Human Comparisons and Transparency**

The paper includes several head-to-head comparisons with GPT-4, where Llama 3.1 sometimes falls short. It’s commendable that Meta is transparent about these results, even when they aren’t favorable.

![](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F209c78ac-3fc7-466f-91ea-4d0ab4beb504_1243x511.png align="left")

## **Safety Enhancements and Vulnerabilities**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1723542044922/c41120ce-0fc7-4cce-8bb7-61571bcaa4e4.png align="center")

Meta claims Llama 3 has a significantly lower violation rate than its competitors, with minimal false refusals. They also admit Llama 3 is more susceptible to prompt injections than GPT-4 or Gemini Pro but performs better than models like Vicuna.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1723544138037/e4ba70ed-4750-47ac-b8fc-e6ecc4a97499.png align="center")

## **Pre-Release Rigor**

Meta’s pre-release checks were thorough, with subject matter experts evaluating operational plans for potential vulnerabilities. Thanks to extensive data filtering, the analysis showed no significant uplift in the ability to create harmful content when using Llama 3.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1723544247301/1defd1b8-8199-45e0-9147-b35d5a938a17.png align="center")

<mark>"the operational plans generated by each team are evaluated by subject matter experts with domain expertise in biology, chemistry, and operational planning. Each plan is evaluated across four stages of potential attacks, generating scores for metrics such as scientific accuracy, detail, detection avoidance, and probability of success in scientific and operational execution."</mark>

## **Vision, Speech, and Video Capabilities**

The paper discusses Llama 3.1’s vision, speech, and video capabilities, which aren’t yet available. Meta argues that a compositional approach, using separate models, might be more efficient during inference.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1723544339054/1bc40be6-1dc0-48e9-9b28-b9bf69a69b0a.png align="center")

The final benchmark results show that Llama 3, with vision capabilities, is performing well but still trailing behind competitors like Claude 3.5 and GPT-4o in some areas.

They mention they are working on speech generation and understanding, so you should eventually be able to talk to Llama 3.1, similar to what was promised with GPT-4o.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1723544424550/aa63564d-b7f8-4924-bf36-3d155ded0560.png align="center")

## **Meta’s Conclusion and Future Outlook**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1723542204666/31e66067-8f24-4821-91af-51a79a44f4bd.png align="center")

Meta concludes by acknowledging that high-quality foundation models are still in their early stages, with substantial improvements on the horizon. They explored more complex architectures but found that the added complexity didn’t justify the marginal benefits.

They hope the release of Llama 3 will encourage the industry to embrace the open, responsible development of AGI. By avoiding overfitting on common benchmarks and using a separate team to process training data, they’ve ensured that Llama 3.1’s strong performance reflects actual capability rather than mere memorization.

Overall, Meta has done an impressive job with this model, and the prospect of Llama 4, which will require 10 times more computing power, is incredibly ambitious. Meta is poised to set new standards for open-source LLMs, and I’m eagerly anticipating what’s next. You can experience Llama 3.1 for yourself at Hugging Chat for free.