# RAG with Local Models (using LM Studio)
![python version](https://img.shields.io/badge/python-v3.12.1-green?logo=python)

This repository demonstrates how to perform Retrieval-Augmented Generation (RAG) using locally running language models with LM Studio. The code integrates a local instance of an OpenAI-compatible API and performs text extraction from PDF files.

## Features

- **Local Language Model Integration**: Leverage local language models using LM Studio.
- **PDF Text Extraction**: Extract text from PDF documents using the `pypdf` library.
- **Retrieval-Augmented Generation**: Generate responses based on provided system inputs and user queries.

## Prerequisites

- Python 3.12.1+
- LM Studio set up and running with a local model.

## Installation

0. Install LM Studio and follow simple instructions:
    https://lmstudio.ai/docs/local-server

1. Clone the repository:
    ```bash
    git clone https://github.com/Huraqan/RagForFree.git
    cd RagForFree
    ```

2. Create a virtual environment and activate it:
    ```bash
    python -m venv venv
    venv\Scripts\activate.bat
    ```

3. Install the required packages:
    ```bash
    pip install -r requirements.txt
    ```

## Usage

### Extract Text from a PDF

Use the `get_pdf_text` function to extract text from a PDF document:

```python
pdf_text = get_pdf_text("path/to/your/document.pdf")
```

### Generate Responses with Local Model
Use the prompt function from the provided notebook to generate responses based on system and user inputs:

```python
system_input = get_pdf_text("Sebastiaan-Indesteege-CV2024.pdf")
user_input = "Who is Sebastiaan?"
response = prompt(system_input, user_input, temperature=0).choices[0].message.content
```

`'Sebastiaan Indesteege is a Junior Data Scientist with interests in programming, machine learning, data analysis, deployment, visual design, and music production. He has experience working on various projects, including developing an app for visual latent-space exploration of a Conv-VAE, creating a word-relevance web app using transformers, coding a neural network from scratch using numpy, developing a tariff plan prediction model for Orange, and developing a scraping tool for use with ImmoWeb website. He also has experience in procedural modeling, animation & texturing, exploratory game development, and music production.'`
