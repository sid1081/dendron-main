---
id: j2o2nxc1xp89rdhyg323cdk
title: Step 1
desc: ''
updated: 1746646210806
created: 1746045460266
---

### AWS Updates

We are going to have store the `metadata` in Knowledge Base. The `metadata` is also going to include the s3 url. We will use an LLM to fetch the appropriate metadata, based on user prompt and then use the url and make changes to the template in memory.

### Other Updates

It seems like Claude does a very good job with manipulting the msgJSON based on prompts. An alternative solution could be to use pinecone as the vector database and Anthropic's API to do the prompt rendering and computation.