# Semantic Search System with LangChain and PostgreSQL

This project is the implementation of a technical challenge from the MBA in Software Engineering with AI at Faculdade FullCycle.

It consists of a RAG (Retrieval-Augmented Generation) system using LangChain, PostgreSQL with pgvector for vector storage, and Google Gemini or OpenAI GPT for embeddings and answer generation.

## Features

- **PDF Document Ingestion**: Processes and stores PDF documents in a vector database.
- **Semantic Search**: Performs searches based on semantic meaning.
- **RAG Chat**: Interactive chat interface that answers questions based on the ingested documents.


## Environment Setup

To set up the environment and install the project dependencies, follow the steps below.

1. **Create and activate a virtual environment (`venv`):**

```bash
python3 -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

2. **Install dependencies:**

```bash
pip install -r requirements.txt
```

3. **Set environment variables:**
    - Duplicate the `.env.example` file and rename it to `.env`.

```bash
cp .env.example .env
```

- Open the `.env` file and replace the values with your real API keys obtained as per the instructions below.

4. **Install PostgreSQL via Docker:**

```bash
docker-compose up -d
```


## Requirements to Run the Code

To run the code, you must create API Keys for the OpenAI or Google Gemini services.
Below are detailed instructions for creating these keys.

**To use OpenAI, comment out the Google key in `.env`.**

### Creating an API Key in OpenAI

1. **Go to the OpenAI website:** 
    - https://platform.openai.com/account/api-keys
2. **Log in or create an account:**
    - If you already have an account, click “Log in” and enter your credentials.
    - Otherwise, click “Sign up” to create a new account.
3. **Go to the API Keys section:**
    - After logging in, click “API Keys” in the left sidebar.
4. **Create a new API Key:**
    - Click the “Create new secret key” button.
    - Give the key a name that you can easily identify.
    - Click “Create secret key”.
5. **Copy and store your API Key:**
    - The key will be shown only once. Copy it and paste it into the `.env` file in the `OPENAI_API_KEY` variable.

### Creating an API Key in Google Gemini

1. **Access Google AI Studio:**
    - https://ai.google.dev/gemini-api/docs/api-key?hl=pt-BR
2. **Log in with your Google account:**
    - Use your Google account to access AI Studio.
3. **Go to the API Keys section:**
    - In the dashboard, click “API Keys” or “Chaves de API”.
4. **Create a new API Key:**
    - Click “Create API Key” or “Criar chave de API”.
    - Give the key a name that you can easily identify.
    - The key will be generated and shown on the screen.
5. **Copy and store your API Key:**
    - Copy the generated key and paste it into the `.env` file in the `GOOGLE_API_KEY` variable.

### PDF File

This repository contains the file `document.pdf` with an article about the history of Linux (in portuguese), which can 
be used for content ingestion into the vector database. If you wish, you can replace this file with a PDF of your choice.

***

## Execution

### 1. PDF Ingestion

```bash
python3 src/ingest.py
```

### 2. Start the chat

```bash
python3 src/chat.py
```

- Ask questions about the PDF content.


### 3. Exit

- Type **'exit'** to terminate the script.
