# ChatGPT Wiki
This is a documentation about how to use ChatGPT as a 'smart' wiki to provide answers to user questions.

## Idea
The basic idea is to give ChatGPT a sort of instruction set on what it should provide as an answer. Basically a look-up table. This can for example be used in certain applications so the user doesn't have to contact the support if he has a question, instead he can just ask a question about the application which will be answered by ChatGPT (using the instruction set) to provide a senseful human-like answer. This could be implemented by making an API-Request to ChatGPT including the instruction set, adding the users question at the end.
Because of the character limit we have to come up with other solutions than just putting all the info into one prompt, as that would exceed this limit. I've listed three possible approaches below.

## Possible Approaches:

## First Approach
1. If your dataset (including the user's question) doesn't exceed ChatGPT's character limit of 4096 characters you can just put the dataset at the end and add the users question to the end (as seen below).

**Input prompt:**

![Screenshot of an example dataset for ChatGPT](https://github.com/LunaHD24/ChatGPT-Wiki/blob/main/ressources/dataset1.png)

**ChatGPT's Answers:**

> Question: 'How to delete a repository?'

![Screenshot of an example answer to a question from ChatGPT using a given dataset](https://github.com/LunaHD24/ChatGPT-Wiki/blob/main/ressources/datasetAnswer1.png)

> Question: 'How to create a repository?'

![Screenshot of an example answer to a question from ChatGPT using a given dataset](https://github.com/LunaHD24/ChatGPT-Wiki/blob/main/ressources/datasetAnswer2.png)

### Second Approach

2. If your dataset is too large you can seperate it into multiple pieces (assuming these don't exceed the character limit. If it does exceed it you can skip to 3). For example, if you have two main parts, you can give ChatGPT each one individually, but still in the same conversation. This would result in ChatGPT getting all the needed information. In the last part of the instruction set you may include the users question, but you can also give the users question in a different message aswell (both options are shown below). The 'ONLY ANSWER WITH A WHITESPACE CHARACTER, NO EXPLANATION, NOTHING' is required, as otherwise ChatGPT will output a line of text even though it was told not to. With this phrase at the end of each part of the instruction set (except for the one with the users question if you would include it in the last instruction set) ChatGPT will output either a space character or nothing (as it's an AI it sadly isn't 100% reliable).

**Input Prompts:**

> Including the users question in the last instruction set

![Screenshot of an example dataset part for ChatGPT](https://github.com/LunaHD24/ChatGPT-Wiki/blob/main/ressources/datasetPart1.png)

**ChatGPT's Answers:**

> Including the users question in the last instruction set

![Screenshot of an example answer to a question from ChatGPT using a given dataset](https://github.com/LunaHD24/ChatGPT-Wiki/blob/main/ressources/datasetAnswer1.png)
