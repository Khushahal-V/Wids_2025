# Assignment 1 – Hugging Face Pipelines

This folder contains solutions for **Assignment 1**, which focuses on using
pre-trained models from the **Hugging Face `transformers` library** via the
`pipeline` API.  
The assignment demonstrates three fundamental NLP tasks:
- Text Summarization
- Text Generation
- Sentiment Analysis


## Folder Structure
```
├── Hugging_face.ipynb # Q1: Text summarization using Hugging Face pipeline
├──                    # Q2: Text generation using Hugging Face pipeline
├──                    # Q3: Sentiment analysis on multiple reviews
└── README.md # Documentation for Assignment 1
```




---

## Q1. Text Summarization


### Task Description
A Python script was written to:
- Import `pipeline` from `transformers`
- Create a summarization pipeline using `pipeline("summarization")`
- Define a long paragraph (4–5+ sentences) as a single Python string
- Generate a summary while controlling the output size using `min_length`
  and `max_length`
- Print:
  - Original text
  - Original text length (in words)
  - Generated summary
  - Summary length (in words)

### Implementation Details
- The default summarization model
  (`sshleifer/distilbart-cnn-12-6`) is used
- `do_sample=False` ensures deterministic output
- Word counts are calculated using Python string splitting
- `textwrap` is used to improve output readability in the terminal

This demonstrates how large text can be compressed into a concise summary
using transformer-based models.

---

## Q2. Text Generation

### Task Description
A Python script was written to:
- Create a text generation pipeline using `pipeline("text-generation")`
- Use the prompt:  
  **"In 2030, AI systems will"**
- Generate **two different continuations** of the prompt
- Limit output length using `max_new_tokens=50`
- Clearly print both generated sequences for comparison

### Implementation Details
- The default GPT-2 model is used
- `num_return_sequences=2` generates multiple outputs
- `do_sample=True` enables variation in generated text
- Outputs are printed separately to allow easy comparison

This task demonstrates how language models can generate multiple plausible
continuations from the same prompt.

---

## Q3. Sentiment Analysis


### Task Description
A Python script was written to:
- Create a sentiment analysis pipeline using
  `pipeline("sentiment-analysis")`
- Define a list of **five short movie reviews**
- Pass all reviews to the pipeline in a single call
- Print, for each review:
  - Review text
  - Predicted sentiment label
  - Confidence score

### Implementation Details
- The pipeline processes all reviews in batch
- Results are printed in a readable format
- Confidence scores are rounded for clarity

This demonstrates how transformer models can efficiently analyze sentiment
across multiple inputs.

---

## Technologies Used

- Python
- Hugging Face `transformers`
- Pre-trained transformer models (via `pipeline` API)

---

## Summary

Assignment 1 focuses on understanding and applying Hugging Face pipelines for
core NLP tasks.  
The solutions demonstrate:
- Correct use of the `pipeline` abstraction
- Proper handling of inputs and outputs
- Clear and readable result presentation



