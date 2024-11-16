# Exploring and comparing different LLMs


## Introduction

- Different types of LLMs in the current landscape.


## Understand different types of LLMs

Large Language Models (LLMs) can have multiple categorizations based on their architecture, training data, and use case. Understanding these differences will help our startup select the right model for the scenario, and understand how to test, iterate, and improve performance.

There are many different types of LLM models, your choice of model depends on what you aim to use them for, your data, how much you're ready to pay and more.

Depending on if you aim to use the models for text, audio, video, image generation and so on, you might opt for a different type of model.

- **Audio and speech recognition**. For this purpose, Whisper-type models are a great choice as they're general-purpose and aimed at speech recognition. It's trained on diverse audio and can perform multilingual speech recognition.
  
- **Image generation**. For image generation, DALL-E and Midjourney are two very known choices. DALL-E is offered by Azure OpenAI.
  
- **Text generation**. Most models are trained on text generation and you have a large variety of choices from GPT-3.5 to GPT-4. They come at different costs with GPT-4 being the most expensive. 

Selecting a model means you get some basic capabilities, that might not be enough however. Often you have company specific data that you somehow need to tell the LLM about. There are a few different choices on how to approach that, more on that in the upcoming sections.

### Foundation Models versus LLMs

The term Foundation Model was [coined by Stanford researchers](https://arxiv.org/abs/2108.07258?WT.mc_id=academic-105485-koreyst) and defined as an AI model that follows some criteria, such as:

- **They are trained using unsupervised learning or self-supervised learning**
- **They are very large models** 
- **They are normally intended to serve as a ‘foundation’ for other models**
![Foundation Models versus LLMs](./images/FoundationModel.png?WT.mc_id=academic-105485-koreyst)



To further clarify this distinction, let’s take ChatGPT as an example. To build the first version of ChatGPT, a model called GPT-3.5 served as the foundation model. This means that OpenAI used some chat-specific data to create a tuned version of GPT-3.5 that was specialized in performing well in conversational scenarios, such as chatbots.

![Foundation Model](./images/Multimodal.png?WT.mc_id=academic-105485-koreyst)

Image source: [2108.07258.pdf (arxiv.org)](https://arxiv.org/pdf/2108.07258.pdf?WT.mc_id=academic-105485-koreyst)

### Open Source versus Proprietary Models

Another way to categorize LLMs is whether they are open source or proprietary.

Open-source models are models that are made available to the public and can be used by anyone. They are often made available by the company that created them, or by the research community. Examples of popular open source models include [Alpaca](https://crfm.stanford.edu/2023/03/13/alpaca.html?WT.mc_id=academic-105485-koreyst), [Bloom](https://sapling.ai/llm/bloom?WT.mc_id=academic-105485-koreyst) and [LLaMA](https://sapling.ai/llm/llama?WT.mc_id=academic-105485-koreyst).

Proprietary models are models that are owned by a company and are not made available to the public. These models are often optimized for production use. Examples of popular proprietary models include [OpenAI models](https://platform.openai.com/docs/models/overview?WT.mc_id=academic-105485-koreyst), [Google Bard](https://sapling.ai/llm/bard?WT.mc_id=academic-105485-koreyst) or [Claude 2](https://www.anthropic.com/index/claude-2?WT.mc_id=academic-105485-koreyst).

###  Image generation 

Image generation models are models that generate images. These models are often used for image editing, image synthesis, and image translation. Image generation models are often trained on large datasets of images, such as [LAION-5B](https://laion.ai/blog/laion-5b/?WT.mc_id=academic-105485-koreyst), and can be used to generate new images or to edit existing images with inpainting, super-resolution, and colorization techniques. Examples include [DALL-E-3](https://openai.com/dall-e-3?WT.mc_id=academic-105485-koreyst) and [Stable Diffusion models](https://github.com/Stability-AI/StableDiffusion?WT.mc_id=academic-105485-koreyst).

![Image generation](./images/Image.png?WT.mc_id=academic-105485-koreyst)

###  Text & code generation 

Text and code generation models are models that generate text or code. These models are often used for text summarization, translation, and question answering. Text generation models are often trained on large datasets of text, such as [BookCorpus](https://www.cv-foundation.org/openaccess/content_iccv_2015/html/Zhu_Aligning_Books_and_ICCV_2015_paper.html?WT.mc_id=academic-105485-koreyst), and can be used to generate new text, or to answer questions. Code generation models, like [CodeParrot](https://huggingface.co/codeparrot?WT.mc_id=academic-105485-koreyst), are often trained on large datasets of code, such as GitHub, and can be used to generate new code, or to fix bugs in existing code.

 ![Text and code generation](./images/Text.png?WT.mc_id=academic-105485-koreyst)


## Improving LLM results

- **Prompt engineering with context**. The idea is to provide enough context when you prompt to ensure you get the responses you need.

- **Retrieval Augmented Generation, RAG**. Your data might exist in a database or web endpoint for example, to ensure this data, or a subset of it, is included at the time of prompting, you can fetch the relevant data and make that part of the user's prompt.

- **Fine-tuned model**. Here, you trained the model further on your own data which leads to the model being more exact and responsive to your needs but might be costly.

![LLMs deployment](./images/Deploy.png?WT.mc_id=academic-105485-koreyst)

Img source: [Four Ways that Enterprises Deploy LLMs | Fiddler AI Blog](https://www.fiddler.ai/blog/four-ways-that-enterprises-deploy-llms?WT.mc_id=academic-105485-koreyst)

### Prompt Engineering with Context

Pre-trained LLMs work very well on generalized natural language tasks, even by calling them with a short prompt, like a sentence to complete or a question – the so-called “zero-shot” learning.

However, the more the user can frame their query, with a detailed request and examples – the Context – the more accurate and closest to user’s expectations the answer will be. In this case, we talk about “one-shot” learning if the prompt includes only one example and “few shot learning” if it includes multiple examples.
Prompt engineering with context is the most cost-effective approach to kick-off with.

### Retrieval Augmented Generation (RAG)

LLMs have the limitation that they can use only the data that has been used during their training to generate an answer. This means that they don’t know anything about the facts that happened after their training process, and they cannot access non-public information (like company data).
This can be overcome through RAG, a technique that augments prompt with external data in the form of chunks of documents, considering prompt length limits. This is supported by Vector database tools (like [Azure Vector Search](https://learn.microsoft.com/azure/search/vector-search-overview?WT.mc_id=academic-105485-koreyst)) that retrieve the useful chunks from varied pre-defined data sources and add them to the prompt Context.

This technique is very helpful when a business doesn’t have enough data, enough time, or resources to fine-tune an LLM, but still wishes to improve performance on a specific workload and reduce risks of fabrications, i.e., mystification of reality or harmful content.  

### Fine-tuned model

Fine-tuning is a process that leverages transfer learning to ‘adapt’ the model to a downstream task or to solve a specific problem. Differently from few-shot learning and RAG, it results in a new model being generated, with updated weights and biases. It requires a set of training examples consisting of a single input (the prompt) and its associated output (the completion).
This would be the preferred approach if:

- **Using fine-tuned models**. A business would like to use fine-tuned less capable models (like embedding models) rather than high performance models, resulting in a more cost effective and fast solution.

- **Considering latency**. Latency is important for a specific use-case, so it’s not possible to use very long prompts or the number of examples that should be learned from the model doesn’t fit with the prompt length limit.

- **Staying up to date**. A business has a lot of high-quality data and ground truth labels and the resources required to maintain this data up to date over time.

### Trained model

Training an LLM from scratch is without a doubt the most difficult and the most complex approach to adopt, requiring massive amounts of data, skilled resources, and appropriate computational power. This option should be considered only in a scenario where a business has a domain-specific use case and a large amount of domain-centric data.

## Knowledge check

What could be a good approach to improve LLM completion results?

1. Prompt engineering with context
1. RAG
1. Fine-tuned model

A:3, if you have the time and resources and high quality data, fine-tuning is the better option to stay up to date. However, if you're looking at improving things and you're lacking time it's worth considering RAG first.
