---
title: "How to Build an LLM from Scratch: A Step-by-Step Guide"
seoTitle: "How to Build an LLM from Scratch: A Step-by-Step Guide"
seoDescription: "This guide provides a detailed walkthrough of building your LLM from the ground up, covering architecture definition, data curation, training"
datePublished: Sat Jun 08 2024 18:30:00 GMT+0000 (Coordinated Universal Time)
cuid: clxhu855300060ami7kwjeys4
slug: how-to-build-an-llm-from-scratch-a-step-by-step-guide
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1718368287236/cd57c597-1890-439e-8349-17df269b167a.png
tags: artificial-intelligence, blockchain, deep-learning, web3, spheron, llm

---

Building a large language model (LLM) from scratch was a complex and resource-intensive endeavor, accessible only to large organizations with significant computational resources and highly skilled engineers. However, developing a custom LLM has become increasingly feasible with the expanding knowledge and resources available today. Organizations of all sizes can now leverage bespoke language models to create highly specialized generative AI applications, enhancing productivity, efficiency, and competitive edge.

This guide provides a detailed walkthrough of building your LLM from the ground up, covering architecture definition, data curation, training, and evaluation techniques.

## Determine the Use Case for Your LLM

Defining its purpose is the first and arguably most important step in building an LLM. This step is crucial for several reasons:

1. **Influence on Model Size**: The complexity of the use case determines the capability and size of the model, i.e., the number of parameters.
    
2. **Training Data Requirements**: More parameters require more training data.
    
3. **Computational Resources**: Understanding the use case helps estimate the necessary computational resources, such as memory and storage space.
    

Clearly defining the intended use case can clarify why building a custom LLM is preferable to fine-tuning an existing base model. Key reasons for creating your own LLM include:

* **Domain-Specificity**: Training the LLM with industry-specific data that aligns with your organization’s operations and workflow.
    
* **Greater Data Security**: Incorporating sensitive or proprietary information without concerns about data storage and usage in open-source or proprietary models.
    
* **Ownership and Control**: Retaining control over confidential data allows continuous improvement of your LLM as knowledge grows and needs to evolve.
    

## Create Your Model Architecture

After defining the use case, the next step is to define the neural network's architecture, the core engine of your model that determines its capabilities and performance.

#### Transformer Architecture

The transformer architecture is the best choice for building [LLMs](https://www.spheron.network/) due to its ability to:

* Capture underlying patterns and relationships in data.
    
* Handle long-range dependencies in text.
    
* Process input of variable lengths efficiently with its self-attention mechanism, which allows parallel input processing.
    

Since its introduction in 2017, the transformer has become the state-of-the-art neural network architecture incorporated into leading LLMs. Previously, developing transformer components required significant time and specialized knowledge. Today, frameworks like PyTorch and TensorFlow provide these components out of the box.

* [**PyTorch**](https://pytorch.org/): Developed by Meta, it is known for its simplicity and flexibility, making it ideal for prototyping.
    
* [**TensorFlow**](https://www.tensorflow.org/): Created by Google, offering a comprehensive ecosystem for scalable, production-ready machine learning models.
    

## Creating the Transformer’s Components

#### Embedding Layer

The embedding layer converts input into vector representations for efficient processing. This involves:

1. **Tokenization**: Breaking down input into tokens, often sub-word tokens of approximately four characters.
    
2. **Integer Assignment**: Assign each token an integer ID and save it in a vocabulary dictionary.
    
3. **Vector Conversion**: Converting each integer into a multi-dimensional vector, each token feature is represented by a vector dimension.
    

Transformers have two embedding layers: one in the encoder for input embeddings and one in the decoder for output embeddings.

#### Positional Encoder

The transformer generates positional encodings and adds them to each embedding to track token positions within a sequence. This approach allows parallel token processing and better handling of long-range dependencies.

#### Self-Attention Mechanism

The self-attention mechanism is the most crucial component of the transformer, responsible for comparing embeddings to determine their similarity and semantic relevance. It generates a weighted input representation, capturing relationships between tokens to calculate the most probable output.

At each self-attention layer, the input is projected across several smaller dimensional spaces known as heads, referred to as multi-head attention. Each head focuses on different aspects of the input sequence in parallel, developing a richer understanding of the data. The original self-attention mechanism has eight heads, but the number can vary based on objectives and available computational resources.

The encoder and decoder contain self-attention components: the encoder has one multi-head attention layer, while the decoder has two.

#### Feed-Forward Network

This layer captures higher-level features of the input sequence to recognize intricate underlying relationships. It consists of three sub-layers:

1. **First Linear Layer**: This layer projects input onto a higher-dimensional space (e.g., 512 to 2048 in the original transformer).
    
2. **Non-Linear Activation Function**: Introduces non-linearity to help learn more realistic relationships. A common activation function is the [Rectified Linear Unit (ReLU).](https://en.wikipedia.org/wiki/Rectifier_(neural_networks))
    
3. **Second Linear Layer**: This transforms the higher-dimensional representation back to its original dimensionality, compressing additional information while retaining relevant aspects.
    

#### Normalization Layers

Normalization ensures input embeddings fall within a reasonable range, stabilizing the model and mitigating vanishing or exploding gradients. Transformers use layer normalization, normalizing the output for each token at every layer, preserving relationships between token aspects, and not interfering with the self-attention mechanism.

#### Residual Connections

Residual connections feed the output of one layer directly into the input of another, improving data flow through the transformer. These connections prevent information loss, enabling faster and more effective training. During forward propagation, residual connections preserve the original data, and during backward propagation, they help gradients flow more easily through the network, mitigating vanishing gradients.

## Assembling the Encoder and Decoder

After creating the individual components of the transformer, the next step is to assemble them into the encoder and decoder.

#### Encoder

The encoder takes the input sequence and converts it into a weighted embedding that the decoder can use to generate output. The encoder is constructed as follows:

1. **Embedding Layer**: Converts the input tokens into vector representations.
    
2. **Positional Encoder**: Adds positional information to the embeddings to maintain the order of tokens.
    
3. **Residual Connection**: Feeds into a normalization layer.
    
4. **Self-Attention Mechanism**: Compares each embedding against others to determine their similarity and relevance.
    
5. **Normalization Layer**: Ensures stable training by normalizing the output of the self-attention mechanism.
    
6. **Residual Connection**: Feeds into another normalization layer.
    
7. **Feed-Forward Network**: Captures higher-level features of the input sequence.
    
8. **Normalization Layer**: Ensures the output remains within a reasonable range.
    

#### Decoder

The decoder takes the weighted embedding produced by the encoder to generate output, i.e., the tokens with the highest probability based on the input sequence. The decoder's architecture is similar to the encoder's, with a few key differences:

1. **Two Self-Attention Layers**: The decoder has an additional self-attention layer compared to the encoder.
    
2. **Two Types of Self-Attention**:
    
    * **Masked Multi-Head Attention**: Uses causal masking to prevent comparisons against future tokens.
        
    * **Encoder-Decoder Multi-Head Attention**: Each output token calculates attention scores against all input tokens better to establish the relationship between the input and output. This cross-attention mechanism also employs causal masking to avoid influence from future output tokens.
        

The decoder structure is as follows:

1. **Embedding Layer**: Converts the output tokens into vector representations.
    
2. **Positional Encoder**: Adds positional information to the embeddings.
    
3. **Residual Connection**: Feeds into a normalization layer.
    
4. **Masked Self-Attention Mechanism**: Ensures the model doesn't see future tokens.
    
5. **Normalization Layer**: Stabilizes the output of the masked self-attention mechanism.
    
6. **Residual Connection**: Feeds into another normalization layer.
    
7. **Encoder-Decoder Self-Attention Mechanism**: Establishes relationships between input and output tokens.
    
8. **Normalization Layer**: Ensures stable training by normalizing the output.
    
9. **Residual Connection**: Feeds into another normalization layer.
    
10. **Feed-Forward Network**: Captures higher-level features.
    
11. **Normalization Layer**: Maintains stability in the output.
    

## Combining the Encoder and Decoder to Complete the Transformer

Having defined the components and assembled the encoder and decoder, you can combine them to produce a complete transformer model. Transformers typically contain multiple encoders and decoders stacked in equal numbers, such as six each in the original transformer. Stacking encoders and decoders in this manner enhances the transformer's capabilities, allowing each layer to capture different characteristics and underlying patterns from the input, thereby improving the LLM's performance.

## Data Curation

Once your LLM is built, the next critical step is compiling and curating the data for training.

Data quality is paramount in building an effective LLM. While model architecture, training time, and techniques can be adjusted to enhance performance, poor-quality data cannot be compensated. Consequences of low-quality training data include:

* **Inaccuracy**: A model trained on incorrect data will produce inaccurate answers.
    
* **Bias**: The model will learn any inherent bias in the data.
    
* **Unpredictability**: The model may produce incoherent or nonsensical answers, making it difficult to diagnose issues.
    
* **Poor Resource Utilization**: Poor-quality data prolongs training, leading to higher computational, personnel, and energy costs.
    

In addition to high-quality data, vast amounts of data are required for the model to learn linguistic and semantic relationships effectively for natural language processing tasks. Generally, the more performant and capable the LLM needs to be, the more parameters it requires, and consequently, the more data must be curated.

To illustrate, here are a few existing LLMs and the amount of data used to train them:

| Model | \# of Parameters | \# of Tokens |
| --- | --- | --- |
| GPT-3 | 175 billion | 0.5 trillion |
| Llama 2 | 70 billion | 2 trillion |
| Falcon 180B | 180 billion | 3.5 trillion |

For context, 100,000 tokens are roughly equivalent to 75,000 words or an entire novel. Thus, GPT-3, for instance, was trained on the equivalent of 5 million novels' worth of data.

## Characteristics of a High-Quality Dataset

When curating training data for your LLM, it’s essential to consider several key characteristics to ensure high quality:

* **Filtered for Inaccuracies**: Ensure the data is accurate and reliable.
    
* **Minimal Biases and Harmful Speech**: Avoid data that could introduce biases or contain harmful language.
    
* **Cleaned Data**: Filter for:
    
    * Misspellings
        
    * Cross-domain homographs
        
    * Spelling variations
        
    * Contractions
        
    * Punctuation
        
    * Boilerplate text
        
    * Markup (e.g., HTML)
        
    * Non-textual components (e.g., emojis)
        
* **Deduplication**: Remove repeated information to prevent bias amplification.
    
* **Privacy Redaction**: Eliminate confidential or sensitive data.
    
* **Diverse Data**: Include a wide range of formats and subjects (e.g., academic writing, prose, website text, coding samples, mathematics).
    

An essential part of creating an effective training dataset is reserving a portion of the curated data for evaluating the model. Using the same data for both training and evaluation risks overfitting, where the model becomes too familiar with the training data and fails to generalize to new data.

## Where Can You Source Data for Training an LLM?

To source training data for your language model, you can draw from several sources:

* **Existing Public Datasets**: Previously used data available for public use. Prominent examples include:
    
    * **The Common Crawl**: A dataset containing terabytes of raw web data from billions of pages, with variations like RefinedWeb and C4 (Colossal Cleaned Crawled Corpus).
        
    * **The Pile**: A popular text corpus containing data from 22 sources across five categories:
        
        * Academic Writing (e.g., arXiv)
            
        * Online or Scraped Resources (e.g., Wikipedia)
            
        * Prose (e.g., Project Gutenberg)
            
        * Dialog (e.g., YouTube subtitles)
            
        * Miscellaneous (e.g., GitHub)
            
    * **StarCoder**: Nearly 800GB of coding samples in various programming languages.
        
    * **Hugging Face**: An online resource hub with over 100,000 public datasets.
        
* **Private Datasets**: Personally curated datasets created in-house or purchased from specialized organizations.
    
* **Directly from the Internet**: Scraping data directly from websites is an option, though it's often ill-advised due to the potential for inaccuracies, biases, confidential data, and data ownership issues.
    

## Training Your Custom LLM

Training an LLM involves passing vast amounts of textual data through its neural network to initialize its parameters (weights and biases). This process includes two main steps: forward and backward propagation.

**Forward Propagation**: Training data is fed into the LLM, which learns language patterns and semantics to accurately predict output. Each layer's output serves as the input to the next layer, culminating in the final output layer generating a predicted output based on the input sequence and learned parameters.

![](https://files.codingninjas.in/article_images/understanding-forward-propagation-0-1640175094.webp align="left")

Source- [link](https://www.youtube.com/watch?v=Tb23YtZ92AE)

**Backward Propagation**: The LLM's parameters are updated based on prediction errors. Gradients, indicating how many parameters should be adjusted to increase accuracy, are propagated backward through the network. Each layer's parameters are adjusted to minimize the loss function, which calculates the difference between the target and actual output.

[![Frame-13](https://media.geeksforgeeks.org/wp-content/uploads/20240217152156/Frame-13.png align="left")](https://www.geeksforgeeks.org/backpropagation-in-neural-network/)

This iterative process continues over multiple batches of training data and several epochs (complete dataset passes) until the model’s parameters converge to maximize accuracy.

## How Long Does It Take to Train an LLM from Scratch?

The training duration for an LLM varies significantly based on several factors:

* The complexity of the desired use case
    
* The amount, complexity, and quality of available training data
    
* Available computational resources
    

Training for a simple task on a small dataset may take a few hours, while complex tasks with large datasets could take months. Mitigating underfitting (insufficient training) and overfitting (excessive training) is crucial. The best time to stop training is when the LLM consistently produces accurate predictions on unseen data.

## LLM Training Techniques

**Parallelization**: Distributing training tasks across multiple GPUs to expedite training times and utilize the parallel processing abilities of GPUs effectively. Techniques include:

* **Data Parallelization**: Divides training data into shards distributed across GPUs.
    
* **Tensor Parallelization**: Splits matrix multiplications into smaller calculations performed simultaneously on multiple GPUs.
    
* **Pipeline Parallelization**: Distributes transformer layers across GPUs for parallel processing.
    
* **Model Parallelization**: Distributes the model across GPUs, using the same data for each part of the model.
    

**Gradient Checkpointing**: Reduces memory requirements by storing only a subset of intermediate activations at defined checkpoints during forward propagation. Only the subset needs recalculating during backward propagation, balancing memory savings with processing overhead.

## LLM Hyperparameters

[Hyperparameters](https://blog.spheron.network/best-practices-for-llm-hyperparameter-tuning), set before training and unchanged by the training data, influence the LLM's training behavior. Tuning hyperparameters is crucial for aligning the LLM with expectations and use cases. Notable hyperparameters include:

* **Batch Size**: The number of instances from the training data fed into the model at each timestep. Larger batches use more memory but speed up training, while smaller batches use less memory but take longer.
    
* **Learning Rate**: The speed at which the LLM updates in response to its loss function. A higher learning rate expedites training but may cause instability and overfitting, while a lower rate is more stable but lengthens training.
    
* **Temperature**: Adjusts the range of possible outputs to control the LLM's creativity. Lower values generate more predictable output, while higher values increase randomness and creativity.
    

## Fine-Tuning Your LLM

After initial training with larger, general-purpose datasets, fine-tuning prepares the LLM for specific use cases. Fine-tuning methods include:

* **Full Fine-Tuning** Updates all base model parameters, creating a new version with altered weighting. It is comprehensive but resource-intensive.
    
* **Transfer Learning** leverages the model’s pre-trained knowledge, freezing many or all base LLM layers and fine-tuning with a smaller, task-specific dataset. It is less time-consuming and resource-intensive than full fine-tuning.
    

## Evaluating Your Bespoke LLM

After training and fine-tuning your LLM, it’s crucial to test whether it performs as expected for its intended use case. This step determines if the LLM is ready for deployment or requires further training. Use previously unseen datasets that reflect real-world scenarios the LLM will encounter for an accurate evaluation. These datasets should differ from those used during training to avoid overfitting and ensure the model captures genuine underlying patterns.

## LLM Benchmarks

An objective method to evaluate your bespoke LLM is through benchmarks: standardized tests developed by the AI research and development community. Benchmarks provide a consistent way to assess LLM performance and compare it against existing language models. Each benchmark includes its own dataset, which helps avoid overfitting by ensuring the evaluation data differs from the training data.

Some widely used benchmarks for evaluating LLM performance include:

* **ARC (AI2 Reasoning Challenge)**: Evaluate knowledge and reasoning skills through question-answer (QA) tasks.
    
* **HellaSwag**: Tests commonsense reasoning and natural language inference (NLI) capabilities using sentence completion exercises.
    
* [**MMLU (Massive Multitask Language Understanding)**](https://paperswithcode.com/dataset/mmlu): Consists of 15,908 questions across 57 tasks to measure natural language understanding (NLU).
    
* **TruthfulQA**: Measures the model’s ability to generate truthful answers, assessing its tendency to "hallucinate."
    
* **GSM8K**: Evaluates multi-step mathematical abilities with 8,500 grade-school-level math word problems.
    
* **HumanEval**: Assesses the LLM’s ability to generate functionally correct code.
    
* **MT Bench**: Evaluates the LLM’s effectiveness in engaging in multi-turn dialogues, similar to chatbot interactions.
    

## Conclusion

In summary, building an LLM from scratch involves several key stages:

1. **Determining the Use Case**: Define your custom language model's purpose and specific application.
    
2. **Creating Your Model Architecture**: Develop and assemble the individual components to create a transformer model.
    
3. **Data Curation**: Source and curate the data necessary for training your model.
    
4. **Training**: Conduct pre-training and fine-tuning of your model to optimize performance.
    
5. **Evaluation**: Test your model’s functionality and overall performance using benchmarks to ensure it meets the intended objectives.
    

Understanding these stages provides a realistic perspective on the resources and effort required to develop a bespoke LLM. While the barriers to entry for creating a language model from scratch have been significantly lowered, it remains a considerable undertaking. Therefore, it’s essential to determine whether building an LLM is necessary for your needs or if an existing solution can provide the same benefits.

## Join Spheron's Private Testnet and Get Complimentary Credits for your Projects

As a developer, you now have the opportunity to build on Spheron's cutting-edge technology using free credits during our private testnet phase. This is your chance to experience the benefits of decentralized computing firsthand at no cost to you.

If you're an AI researcher, deep learning expert, machine learning professional, or large language model enthusiast, we want to hear from you! Participating in our private testnet will give you early access to Spheron's robust capabilities and receive complimentary credits to help bring your projects to life.

Don't miss out on this exciting opportunity to revolutionize how you develop and deploy applications. Sign up now by filling out this form: [https://b4t4v7fj3cd.typeform.com/to/Jp58YQB2](https://b4t4v7fj3cd.typeform.com/to/Jp58YQB2)

Join us in pushing the boundaries of what's possible with decentralized computing. We look forward to working with you!