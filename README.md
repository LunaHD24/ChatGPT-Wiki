# ChatGPT Wiki
This is a documentation about how to use ChatGPT as a 'smart' wiki to provide answers to user questions.

The basic idea is to give ChatGPT a sort of instruction set on what it should provide as an answer. Basically a look-up table. This can for example be used in certain applications so the user doesn't have to contact the support if he has a question, instead he can just ask a question about the application which will be answered by ChatGPT (using the instruction set) to provide a senseful human-like answer. This could be implemented by making an API-Request to ChatGPT including the instruction set, adding the users question at the end.
Because of the character limit we have to come up with other solutions than just putting all the info into one prompt, as that would exceed this limit. I've listed three possible approaches below.

## First Approach
If your dataset (including the user's question) doesn't exceed ChatGPT's character limit of 4096 characters you can just put the dataset at the end and add the users question to the end (as seen below).

**Input prompt:**

![Screenshot of an example dataset for ChatGPT](https://github.com/LunaHD24/ChatGPT-Wiki/blob/main/ressources/dataset1.png)

**ChatGPT's Answers:**

> Question: 'How to delete a repository?'

![Screenshot of an example answer to a question from ChatGPT using a given dataset](https://github.com/LunaHD24/ChatGPT-Wiki/blob/main/ressources/datasetAnswer1.png)

> Question: 'How to create a repository?'

![Screenshot of an example answer to a question from ChatGPT using a given dataset](https://github.com/LunaHD24/ChatGPT-Wiki/blob/main/ressources/datasetAnswer2.png)

## Second Approach

If your dataset is too large you can seperate it into multiple pieces (assuming these don't exceed the character limit. If it does exceed it you can skip to 3). For example, if you have two main parts, you can give ChatGPT each one individually, but still in the same conversation. This would result in ChatGPT getting all the needed information. In the last part of the instruction set you may include the users question, but you can also give the users question in a different message aswell (one of the options is shown below, both we're tested and worked). The 'ONLY ANSWER WITH A WHITESPACE CHARACTER, NO EXPLANATION, NOTHING' is required, as otherwise ChatGPT will output a line of text even though it was told not to. With this phrase at the end of each part of the instruction set (except for the one with the users question if you would include it in the last instruction set) ChatGPT will output either a space character or nothing (as it's an AI it sadly isn't 100% reliable).

**Input Prompt:**

![Screenshot of an example dataset part for ChatGPT](https://github.com/LunaHD24/ChatGPT-Wiki/blob/main/ressources/dataset2.png)

**ChatGPT's Answer:**

![Screenshot of an example answer to a question from ChatGPT using a given dataset](https://github.com/LunaHD24/ChatGPT-Wiki/blob/main/ressources/dataset2Answer1.png)

## Third Approach

You can also create a list of categories matching the parts of your instruction set.
For example:
```
- Creation
- Managing
- Deletion
```
You can provide ChatGPT with this list and the users question and then tell it to put the users question in one of the given categories.

![Screenshot of an example list for ChatGPT which matches it to a category](https://github.com/LunaHD24/ChatGPT-Wiki/blob/main/ressources/list1.png)

Now you can use this answer to provide the matching dataset.

![Screenshot of an example answer to a question from ChatGPT using a given dataset](https://github.com/LunaHD24/ChatGPT-Wiki/blob/main/ressources/list1Answer.png)
