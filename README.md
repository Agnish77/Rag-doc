# Rag-doc

## RAG Document Q&A with Groq and Llama3
This project is a Document Q&A System that utilizes a Retrieval-Augmented Generation (RAG) approach. Built using Streamlit, it integrates Groq's Llama3 model for accurate document-based Q&A, and leverages HuggingFace embeddings for document similarity search. The system is designed to answer questions based on a set of research papers or any loaded PDF documents, making it ideal for academic and research purposes.

## Features
Interactive Q&A: Users can input queries related to the documents, and the system generates accurate answers based on the context.
RAG Architecture: Combines retrieval of relevant documents with generative capabilities to provide context-aware answers.
Embeddings with HuggingFace: Uses all-MiniLM-L6-v2 embeddings to build a vector store, enabling similarity search.
Groq Llama3 Integration: Uses Groq's Llama3 model as the core language model for generating responses.
PDF Ingestion: Supports bulk loading of research papers in PDF format from a specified directory.


## Installation
# Prerequisites

Python (version 3.8 or higher)

Streamlit

Langchain and related dependencies

HuggingFace Embeddings

Groq API Key

Install Required Packages

Run the following command to install all necessary packages:

pip install streamlit langchain-groq langchain-core langchain-huggingface langchain-community python-dotenv

## Setting Up Environment Variables
Create a .env file in the root of your project to store your API keys securely. Add the following lines to .env:

GROQ_API_KEY=your_groq_api_key_here
HF_TOKEN=your_huggingface_token_here
Make sure to replace your_groq_api_key_here and your_huggingface_token_here with your actual keys.


## Usage

Running the App

To run the Streamlit app, use the following command:

streamlit run app.py

Step-by-Step Guide
Document Embedding:

#### Place your research papers (PDFs) in a directory named research_papers within the project folder.
Click the "Document Embedding" button to build the vector database.
The vector store uses HuggingFace Embeddings to index the documents for retrieval.
Querying the Documents:

Enter your question in the input box related to the content of the research papers.
The system will retrieve relevant chunks of text, and Llama3 will generate a response based on the retrieved content.
The response is displayed with a Document Similarity Search section that shows similar documents with their content.
Response Time
The app displays the response time for each query, giving insights into the system's performance.

## How It Works

Document Loading:

PDF files from the research_papers directory are loaded using PyPDFDirectoryLoader.

Text Splitting:

The documents are split into manageable chunks using RecursiveCharacterTextSplitter to ensure relevant retrieval.

Vector Embedding:

The documents are embedded using HuggingFace embeddings and stored in a vector database managed by FAISS.

Query Processing:

User queries are processed, relevant documents are retrieved, and responses are generated using Groq’s Llama3 model.

## Project Structure

|-- .env                        # Contains environment variables (API keys)

|-- research_papers/            # Directory with research paper PDFs

|-- app.py                      # Main Streamlit application code

|-- README.md                   # Project documentation

|-- requirements.txt            # List of required Python packages

|-- .streamlit/

    |-- secrets.toml            # For storing Streamlit secrets (optional)

