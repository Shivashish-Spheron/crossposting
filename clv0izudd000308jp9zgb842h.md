---
title: "Small language models are not just the latest trend but the next big thing in AI"
seoTitle: "Small language models are not just the trend but the next big thing"
seoDescription: "In the AI industry, tech giants have been competing to build increasingly larger language models. However, a new trend has emerged: small language models."
datePublished: Sat Apr 13 2024 18:30:00 GMT+0000 (Coordinated Universal Time)
cuid: clv0izudd000308jp9zgb842h
slug: small-language-models-are-not-just-the-latest-trend-but-the-next-big-thing-in-ai
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1713159421173/7c3eb022-a55a-4a75-ac0e-a5b46a87589c.png
tags: ai, artificial-intelligence, cloud-computing, blockchain, web3, decentralization, spheron, large-language-models

---

In the AI industry, tech giants have been competing to build increasingly larger language models. However, a new trend has emerged: small language models (SLMs) are gaining popularity. As progress in large language models (LLMs) appears to plateau, researchers and developers are focusing on SLMs. These AI models are compact, efficient, and highly adaptable, challenging the idea that bigger is always better. SLMs are expected to revolutionize AI development.

## **Is the demand for LLM degrees reaching a plateau?**

According to recent performance comparisons by [Vellum](https://www.vellum.ai/llm-leaderboard) and [HuggingFace](https://huggingface.co/spaces/HuggingFaceH4/open_llm_leaderboard), the gap between LLMs is narrowing rapidly. This trend is particularly noticeable in certain areas, such as multi-choice questions, reasoning, and math problems, where there are minimal differences in performance between the top models. For instance, in multi-choice questions, Claude 3 Opus, GPT-4, and Gemini Ultra all score above 83%, while in reasoning tasks, Claude 3 Opus, GPT-4, and Gemini 1.5 Pro exceed 92% accuracy.

Interestingly, even smaller models like Mixtral 8x7B and Llama 2 – 70B are showing promising results in specific areas, such as reasoning and multi-choice questions, where they outperform some of their larger counterparts. This suggests that model size may not be the only determining factor in performance and that other aspects, such as architecture, training data, and fine-tuning techniques, could play a significant role.

The latest research papers announcing new LLMs all point in the same direction: "If you just look empirically, the last dozen or so articles that come out, they're kind of all in the same general territory as GPT-4," says Gary Marcus, the former head of Uber AI and author of "Rebooting AI," a book about building trustworthy AI. 

"According to Marcus, while some language models are slightly better than GPT-4, there has not been a significant improvement in over a year. This raises the question of whether large language models are reaching their limits regarding performance. If this trend continues, it may significantly impact the future development and usage of language models. Developers may need to focus on developing more efficient and specialized architectures, rather than just increasing model size."

## **The LLM approach has certain limitations that should be considered**

Language Models with Large Amounts of Parameters (LLMs) are undeniably powerful. However, there are significant drawbacks to using them. LLMs require enormous data for training, which requires billions or trillions of parameters. As a result, the training process is extremely resource-intensive, and the computational power and energy consumption required to train and run LLMs are staggering. This leads to high costs, making it difficult for smaller organizations or individuals to engage in core LLM development. At an MIT event last year, OpenAI CEO Sam Altman revealed that the cost of training GPT-4 was at least $100M. 

Furthermore, the complexity of the tools and techniques required to work with LLMs presents a steep learning curve for developers, further limiting accessibility. The development cycle for machine learning models is also quite long, from training to building and deploying models, which slows development and experimentation. A recent paper from the University of Cambridge shows that companies can spend [90 days or longer deploying a single machine-learning model.](https://dl.acm.org/doi/fullHtml/10.1145/3533378#Bib0005)

LLMs, or Language Models, have a significant issue with generating outputs that seem plausible but are not factual. This is because they are trained to predict the next most likely word based on patterns in the training data rather than having a true understanding of the information. As a result, LLMs can confidently produce false statements, make up facts, or combine unrelated concepts in nonsensical ways. Detecting and mitigating these "hallucinations" is an ongoing challenge in developing reliable and trustworthy language models.

According to Marcus, if you're using LLMs for high-stakes problems, you don't want to insult your customers, get bad medical information, or use them to drive a car and take risks. Therefore, it is still a problem.

LLMs' scale and black-box nature can also make them challenging to interpret and debug, which is crucial for building trust in the model's outputs. Bias in the training data and algorithms can lead to unfair, inaccurate, or even harmful outputs. Techniques to make LLMs "safe" and reliable can also [reduce their effectiveness](https://venturebeat.com/ai/google-suspends-geminis-ability-to-generate-people-after-numerous-woke-inaccuracies/), as seen with Google Gemini. Additionally, the centralized nature of LLMs raises concerns about the concentration of power and control in the hands of a few large tech companies.

## **Small Language Models (SLMs)**

Small Language Models (SLMs) are simplified versions of large language models (LLMs) with fewer parameters and simpler designs. They require less data and training time, taking only minutes or a few hours, as opposed to days for LLMs. This makes SLMs more efficient and easier to implement on-site or on smaller devices.

One of the main advantages of SLMs is their suitability for specific applications. Due to their focused scope and requirement for less data, they can be fine-tuned for particular domains or tasks more easily than large, general-purpose models. This customization allows companies to create SLMs that are highly effective for their specific needs, such as sentiment analysis, named entity recognition, or domain-specific question answering. The specialized nature of SLMs can lead to improved performance and efficiency in these targeted applications compared to using a more general model.

SLMs, or "smaller language models," have several benefits over larger models regarding privacy and security. Due to their smaller codebase and simpler architecture, SLMs are easier to audit and less likely to have unintended vulnerabilities. This makes them a better choice for applications that handle sensitive data, such as healthcare or finance. Data breaches could have severe consequences in these industries, so it's essential to use models that minimize the risk of exposure.

Another advantage of SLMs is their reduced computational requirements. This means they can run on devices or on-premises servers, reducing the need for cloud infrastructure. Local processing can further improve data security and reduce the risk of exposure during data transfer.

Moreover, SLMs are less prone to undetected hallucinations within their specific domain compared to LLMs. SLMs are typically trained on a narrower and more targeted dataset specific to their intended domain or application. This helps the model learn the patterns, vocabulary, and information that are most relevant to its task. With fewer parameters and a more streamlined architecture, SLMs are also less prone to capturing and amplifying noise or errors in the training data.

According to Clem Delangue, CEO of the AI startup HuggingFace, [up to 99% of use cases](https://www.linkedin.com/posts/clementdelangue_ive-said-it-and-will-say-it-again-1-activity-7112524134395318273-T3z6/) could be addressed using SLMs. HuggingFace, whose platform enables developers to build, train, and deploy machine learning models, recently announced a [strategic partnership with Google](https://huggingface.co/blog/google-cloud-model-garden). As a result, HuggingFace has been integrated into [Google's Vertex AI](https://huggingface.co/blog/google-cloud-model-garden), allowing developers to deploy thousands of models quickly through the Google Vertex Model Garden.

### **"Gemma" by Google**

Google initially lost out to OpenAI in developing large language models (LLMs), but it is now actively pursuing the opportunity in small language models (SLMs). In February, [Google launched Gemma, a series of SLMs](https://blog.google/technology/developers/gemma-open-models/) that are efficient and user-friendly and can run on everyday devices such as smartphones, tablets, and laptops without requiring special hardware or extensive optimization.

Since its release, Gemma has been downloaded more than 400,000 times on HuggingFace, and some exciting projects are already emerging. For example, Cerule is a powerful image and language model that combines Gemma 2B with Google's SigLIP. It has been trained on a vast dataset of images and text and uses highly efficient data selection techniques to achieve [high performance without requiring](https://huggingface.co/Tensoic/Cerule-v0.1) a lot of data or computation. This makes it well-suited for emerging edge computing use cases.

Another example is [CodeGemma](https://huggingface.co/blog/codegemma), a specialized version of Gemma that focuses on coding and mathematical reasoning. CodeGemma offers three different models tailored for various coding-related activities, making advanced coding tools more accessible and efficient for developers. 

### **The transformative potential of small language models**

As the AI community continues to explore the potential of small language models (SLMs), the advantages of faster development cycles, improved efficiency, and the ability to customize models to specific needs become increasingly apparent. SLMs have the potential to make AI accessible to more people and drive innovation across industries by enabling cost-effective and targeted solutions. The deployment of SLMs at the edge opens up new possibilities for real-time, personalized, and secure applications in various sectors such as finance, entertainment, automotive systems, education, e-commerce, and healthcare.

By processing data locally and reducing reliance on cloud infrastructure, edge computing with SLMs enables faster response times, improved data privacy, and enhanced user experiences. This decentralized approach to AI has the potential to transform the way businesses and consumers interact with technology, creating more personalized and intuitive experiences in the real world. As larger language models (LLMs) face challenges related to computational resources and potentially hit performance plateaus, the rise of SLMs promises to keep the AI ecosystem evolving at an impressive pace.