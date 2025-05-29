# MicDrop -- A Mini NotebookLM Powered by GPT

Meet **MicDrop** -- a mini NotebookLM that turns your short text documents into intuitive, conversational podcasts.

Inspired by Google's cutting-edge AI tool and powered by not one but two GPT models, MicDrop is a **proof-of-concept, ambitious prototype** that aims to take information-rich documents and make them easy to understand.

To accomplish this text-generation task -- and ultimately transform these scripts into MicDrop episodes -- we will begin by fine-tuning `distilgpt2`, the streamlined version of GPT-2, which is smaller and faster but still effective. To learn more about this large language model, check out the official model card on [Hugging Face](https://huggingface.co/distilbert/distilgpt2).

Our `distilgpt2` model will be fine-tuned on an initial dataset consisting of pairings of articles and corresponding podcast scripts. Each of these documents will be approximately 200-300 words, the foundation for our bite-sized, two-minute episodes.

But you might be wondering, *where* will this dataset come from?

We'll build it -- from scratch.

To do so, we will utilize a *teacher* LLM -- specifically GPT-4o -- to generate the synthetic dataset that its predecessor `distilgpt2` will learn from.

Finally, we will bring these scripts to life with a text-to-speech tool.

Ok. So. Stay tuned.

## View the full notebook right here:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/177J6947KLG3UtF3ZdulVNKG8FaHvZQYS?usp=sharing)

## The Pipeline

Before we *record* our first episode, here's a roadmap of what is to come:

- Set up the GPU runtime
- Generate the synthetic dataset with GPT-4o, the *teacher* LLM
- Prepare the dataset for `distilgpt2`
- Load the pretrained `distilgpt2` model
- Test the base model on a single sentence
- Fine-tune the model using the article-podcast script dataset
- Test the fine-tuned model's podcast script-writing skills
- Transform the scripts into MicDrop episodes

## Tools & Libraries Used

- **Google Colab** — for free GPU access and seamless integration with Drive  
- **Python 3.11.12** — base language for all modeling and data wrangling  
- **pandas** — for reading and managing the dataset of 120K recipes  
- **transformers** — Hugging Face's library for working with 'distilgpt2` and custom fine-tuning  
- **torch** — PyTorch backend powering the fine-tuning and inference  
- **curl** — to download the custom training script from the course server  
- **shutil** — for saving and exporting the fine-tuned model  
- **subprocess** — to manage training script execution with more readable output  
- **Google Drive** — used to store and export the final model

## Acknowledgements

A big thanks to Michele Samorani, Associate Professor in the Department of Information Systems & Analytics at Santa Clara University. A notebook I was working on in his NLP course at the Leavey School of Business helped bring MicDrop to life.
