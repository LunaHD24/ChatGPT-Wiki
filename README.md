# ChatGPT Wiki
This is a documentation about how to use ChatGPT as a 'smart' wiki to provide answers to user questions.

## Idea
The basic idea is to give ChatGPT a sort of instruction set on what it should provide as an answer. Basically a look-up table. This can for example be used in certain applications so the user doesn't have to contact the support if he has a question, instead he can just ask a question about the application which will be answered by ChatGPT (using the instruction set) to provide a senseful human-like answer. This could be implemented by making an API-Request to ChatGPT including the instruction set, adding the users question at the end.
Because of the character limit we have to come up with other solutions than just putting all the info into one prompt, as that would exceed this limit. I've listed two possible approaches below.

### Possible approaches:
1. If your dataset (including the user's question) doesn't exceed ChatGPT's character limit of 4096 characters you can just put the dataset at the end and add the users question to the end (as seen below).

**Input prompt:**

![Screenshot of an example dataset for ChatGPT](https://github.com/LunaHD24/ChatGPT-Wiki/blob/main/ressources/dataset1.png)

**ChatGPT's Answer:**

![Screenshot of an example answer to a question from ChatGPT](https://github.com/LunaHD24/ChatGPT-Wiki/blob/main/ressources/datasetAnswer1.png)
