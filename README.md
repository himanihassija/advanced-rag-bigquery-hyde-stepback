

# Advanced RAG with HyDE and Step-Back Prompting

This project implements an advanced Retrieval-Augmented Generation (RAG) pipeline using HyDE (Hypothetical Document Embeddings) and Step-Back Prompting to improve retrieval quality over a vector store hosted in BigQuery. It leverages Google Vertex AI (Gemini and embeddings) and LangChain for orchestration.

## Overview

Traditional RAG systems often struggle with vague, underspecified, or overly specific user queries. This project enhances retrieval quality by introducing two research-backed techniques:

- HyDE: Generates a hypothetical answer to a query and embeds it for retrieval
- Step-Back Prompting: Rewrites the query into a more abstract form to retrieve higher-level contextual information

These approaches increase semantic coverage and recall before downstream answer generation.

## Architecture

1. User query is received  
2. Query is transformed using HyDE and Step-Back prompting  
3. Transformed queries are embedded using Vertex AI embeddings  
4. Similar documents are retrieved from BigQuery vector storage  
5. Retrieved context can be used for downstream response generation  

## Tech Stack

- Python  
- LangChain  
- Google Vertex AI (Gemini, text-embedding-004)  
- BigQuery Vector Search  
- Google Cloud SDK  

## Setup

### Environment Variables

PROJECT_ID=your-gcp-project-id  
REGION=your-gcp-region  
BQ_INSTANCE=your_bigquery_dataset  
BQ_TABLE=your_bigquery_table  

### Installation

pip install langchain langchain-google-vertexai google-cloud-bigquery

### Run

python main.py

## Example Query

Tell me about the Dursleys.

The query is expanded using HyDE and Step-Back Prompting before retrieving relevant documents from BigQuery.

## Key Learnings

- Implemented advanced RAG enhancement techniques  
- Used BigQuery as a scalable vector store  
- Integrated Gemini models with LangChain  
- Designed modular and extensible retrieval pipelines  

## Future Improvements

- Merge multi-query retrieval results  
- Add reranking of retrieved documents  
- Integrate final answer synthesis  
- Support additional vector stores  

## Acknowledgements

This project was inspired by concepts learned during an AI workshop and extended through independent implementation and experimentation.
