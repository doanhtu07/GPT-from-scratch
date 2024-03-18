# GPT-from-scratch

Credit: https://www.youtube.com/watch?v=kCc8FmEb1nY&list=WL&index=42&t=10s

## Links

- https://github.com/karpathy/nanoGPT

- Google Colab with Shakespear Data & character tokens: 
  - https://colab.research.google.com/drive/1JMLa53HDuA-i7ZBmqV7ZnA3c_fvtXnx-?usp=sharing#scrollTo=h5hjCcLDr2WC

- My copy with notes: 
  - https://colab.research.google.com/drive/1aMCSPvRnjFAdt2gfF5MP7z-fWxyGHnWF

## Quick Notes

- Generative Pretrained Transformer

- We give it the start of a sequence, and the model will try to finish the sequence using probabilities

- Purpose of this project: Train a transformer-based language model, character-level language model

### Tokenization

- Simplest way: Create a mapping from a single character to the vocabulary of single unique characters from training data

![](./images/Screenshot%202024-03-15%20at%206.06.48%20PM.png)

- Other ways: Google SentencePiece (using sub-word units instead of single characters), OpenAI Tiktoken

- Takeaway: Trade-off codebook size (vocabulary) and the sequence length (encoded sequence size)

### Feed Data

- We don't feed the whole training dataset into the model, because that's expensive

- Rather we sample random chunks of dataset and train it a chunk at a time. Also known as **block size** or **context size**

- Take (block size + 1) as sample. Plus 1 is the character we want to predict