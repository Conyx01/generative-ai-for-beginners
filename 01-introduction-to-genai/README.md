# Introduction to Generative AI and Large Language Models

Generative AI is artificial intelligence capable of generating text, images and other types of content. What makes it a fantastic technology is that it democratizes AI, anyone can use it with as little as a text prompt, a sentence written in a natural language. 

## Introduction

 will cover:

* Generative AI and how we landed on the current technology landscape.
* Inner working of a large language model.
* Main capabilities and practical use cases of Large Language Models.

## Learning Goals

After completing this, you will understand:

* What generative AI is and how Large Language Models work.
* How you can leverage large language models for different use cases, with a focus on education scenarios.

##
To start, let’s define some basic concepts and terminology.

## How did we get Generative AI?

Despite the extraordinary *hype* created lately by the announcement of generative AI models, this technology is decades in the making, with the first research efforts dating back to 60s.

Backing up a bit, the  very first prototypes of AI consisted of typewritten chatbots, relying on a knowledge base extracted from a group of experts and represented into a computer. Answers were triggered by keywords appearing in the input text.
However, this did not scale well.

### A statistical approach to AI: Machine Learning

in the 90s, the application of a statistical approach to text analysis led to the development of new algorithms – machine learning - able to learn patterns from data, without being explicitly programmed. This approach allows a machine to simulate human language understanding: a statistical model is trained on text-label pairings, enabling the model to classify unknown input text with a pre-defined label representing the intention of the message.

### Neural networks and modern virtual assistants

In more recent times, the technological evolution of the hardware, capable of handling larger amounts of data and more complex computations, encouraged research in the AI fields, leading to the development of advanced machine learning algorithms – called neural networks or deep learning algorithms.

Neural networks significantly enhanced natural language processing, enabling the representation of the meaning of text in a more meaningful way, valuing the context of a word in a sentence.

### Present day, Generative AI

So that’s how we came to Generative AI today, which can be seen as a subset of deep learning.

![AI, ML, DL and Generative AI](./images/AI-diagram.png?WT.mc_id=academic-105485-koreyst)

*Transformers* – overcame the limits of RNNs, being able to get much longer sequences of text as input. Transformers are based on the attention mechanism, enabling the model to give different weights to the inputs it receives, ‘paying more attention’ where the most relevant information is concentrated, regardless of their order in the text sequence.

generative AI models – also known as Large Language Models (LLMs), since they work with textual inputs and outputs. These models are trained ona huge amount of unlabeled data from:

- books
- articles
- websites
  
## How do large language models work?

* **Tokenizer, text to numbers**: Large Language Models receive a text as input and generate a text as output. However, being statistical models, they work much better with numbers than text sequences. That’s why every input to the model is processed by a tokenizer, before being used by the core model.
  
*  A token is a chunk of text – consisting of a variable number of characters, so the tokenizer's main task is splitting the input into an array of tokens. 
![Example of tokenization](./images/tokenizer-example.png?WT.mc_id=academic-105485-koreyst)

* **Predicting output tokens** 

* **Selection process, probability distribution** 

## 

The input of a large language model is known as prompt, while the output is known as completion.  let’s just say that a prompt may include:

* An **instruction** specifying the type of output we expect from the model. This instruction sometimes might embed some examples or some additional data.

    1. Summarization of an article, book, product reviews and more, along with extraction of insights from unstructured data.
    
    ![Example of summarization](./images/summarization-example.png?WT.mc_id=academic-105485-koreyst)

    <br>
    
    <br>


* A chunk of **code** together with the ask of explaining and documenting it, or a comment asking to generate a piece of code performing a specific task.

![Coding example](./images/coding-example.png?WT.mc_id=academic-105485-koreyst)

<br>

## Knowledge check

What's true about large language models?

1. You get the exact same response every time.
1. It does things perfectly, great at adding numbers, produce working code etc.
1. The response may vary despite using the same prompt. It's also great at giving you a first draft of something, be it text or code. But you need to improve on the results.

