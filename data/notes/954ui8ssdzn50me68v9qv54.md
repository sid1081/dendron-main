## Design

### SP.Message Renderer.Step 1- _1.5 weeks_

The general idea here would be to create a RAG based system, where in we store the `messageJSON` along with some `metadata`(description of the messageJSON) in a vector database and then test the validity of the retrival and generation capabilites of the LLM.

This step won't have an interactive experience like that of an assistant. It will *only* have the core functionality of outputting a `msgJSON` given a prompt. It will be a CLI tool that one can run locally.

### Step 2 - _1 week_

During this week we will build out an evaluation systems where we will take 20 msgJSONs from the system that we create ourselves using a `prompt` and then we will provide the same prompt to the LLM and test the validity of the results. 

> Based on what we find, we will increase the number of examples of msgJSONs our vector database or pivot to a different approach like `fineTuning`. If we find that we might need to rethink the structure of the `msgJSON` to better leverage the LLMs abilities to _only_ alter the **style** and **text** of the message, we might have to re-think the `messageJSON` structure and change the way the rendering application works to accommodate for this change in structure - **PIVOT CAN TAKE UPTO 3 WEEKS**

### Step 3 - _2 weeks_

Assuming that the RAG approach works, we will then build out an assistant type experience to generate the `msgJSON`. This _may_ entail building out a service that can maintain conversation context / state so multiple clients can interact with it. We _may_ implement streaming responses using OpenAI's streaming API.

### Step 4 - _? weeks_

We will then build out the front-end integrations within portal to integrate with this message rendering service. The integration will be a chat like experience where in you can have a conversation with an "agent" to build you a message. 

### Setting expectations

- What percentage of customer messages do you want the AI renderer to automate?

- How much quicker are customers able to setup messages?

- How much human labor does the chatbot save?

- What is the customer sentiment and feedback for this system?


### Milestone planning

- End customer review of message quality

- Cost: how much it costs / inference

### Maintenance

