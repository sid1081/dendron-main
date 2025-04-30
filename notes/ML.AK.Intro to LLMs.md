---
id: obuonjuhcj0tlex3qqgzzyg
title: Intro to LLMs
desc: ''
updated: 1740001542785
created: 1739407566715
url: 'https://www.youtube.com/watch?v=zjkBMFhNj_g&ab_channel=AndrejKarpathy'
---

### Intro to LLMS

- A LLM is just two files - a parameter file(140GB) and an executable(500 lines of code), eg: Llama-2-70B is the Lllama 2.0 model released by Meta which is trained on 70 B paramters. 

- The parameteres are essentially the weights or the paramaters of this neural network that is a LLM.

- Llama is an open source; the weights, the architecture and the executable were released by Meta.

- Chat GPT never released the model architecture so you don't have access to that model.

- Model inference is when you just run the model on your macbook.

- Model training is a lot more involved.

- This LLAMA model is essentially just a next word prediction model. This might seem trivial, but being able to predic the next word(s) can be very powerful since if the objective is to be a next word predicion model, eg to be able to predict the next word about Ruth Handler, you need to parse a lot of information and you end up /learning/ a lot in the process. _All of this knowledge is being compressed into the weights of the neural network ??_. - The neural network isn't actually memorizing the data but instead storing complicated patterns and learning deeper patterns and each weight contributes to understanding multiple concepts.

- First, about "inference" - this just means using the trained model to generate text, as opposed to training it. When you use ChatGPT or when Claude responds to you, that's inference.

- The text generation process works like this:

    - The model looks at the input text (like your question)

    - It predicts what word is most likely to come next

    - It adds that word to the sequence

    - Then it uses the updated sequence to predict the next word

    - This process repeats until it completes the response

    - The phrase "dreams internet documents" is a colorful way of saying that the model recreates text patterns similar to its training data (which includes many internet documents). It's not literally dreaming or remembering specific documents - instead, it has learned patterns from millions of texts and can generate new text following similar patterns.

### There are three main parts of building a model - **training**, **inference** and **fine-tuning**.

    - Training involves firstly scraping the internet for loads of text, of the magnitude of 10TB. After scraping all of this data, the model is trained on this data and all of this data is then _compressed_ into the paramters and weights of the neural network. The LLAMA 2.0 model for instance has 70B parameters which is around 140GB of data. So you can think that the compression that takes place is some sort of lossy compression where all of the data is sort of compressed into these parameters. Training is the most expensive part of the process where a huge GPU cluster is leveraged for over 12 days(for LLAMA) and costs 2M dollars.

    - Inference is the most straightforward part. When interacting with a model, the model performs inference and responds to your queries.

    - Fine-Tuning is the step after inference where the model turns from being a next word prediction model to some sort of assistant.

### How does it work?

    - We don't know really. We know in full detail what the architecture of the neural network looks like and what math is performed at each step, but we still don't know _how_ these parameters/nodes which are dispersed through the neural network interact with each other.

    - We know that they build some sort of knowledge base but it's a bit strange. We know that it works _emperically_, and we know how to fine-tune models and make them better based on evaluation tests.

### Fine-Tuning

    - We first come up with the labeling instructions for the fine tuning job, and then hire people or use scale.ai to perform these labeling tasks where they maybe compile 100,000 questions and answer type forms.

    - These forms are very high quality.

    - The model is then trained on these forms(training takes approx 1 day) and it then subscribes to the structure of these forms and turns in to an assistant.

    - You can then run a lot of evalutaions on this assistant and go back to the first step again to imporove the model based on your evaluations.

### Scaling Laws

    - The performance of the model is governed by N - **number of parameters in the network** and `D` - **amount of text** it's trained on.

    - So far, there is not upper bound on the performance so in theory we could just keep scaling.

    - Algorithmic improvements would be a plus but in theory we can just keep getting better with more **time** and more **compute**.
    
### Tool use

    - Tool use is another reason why these LLMs are becoming so capable. Being able to use tools like browsers, calculators, graphing libraries, image generation libraries etc empowers the LLMS to perform complex tasks like humans would.
    