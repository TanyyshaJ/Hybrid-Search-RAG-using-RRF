# Hybrid Search RAG with RRF

This project implements a Hybrid Search Retrieval-Augmented Generation (RAG) system using both vector search and keyword search. By combining these two approaches, it aims to provide a more comprehensive and accurate retrieval mechanism. The system leverages Pinecone for efficient vector search capabilities and employs Reciprocal Rank Fusion (RRF) to combine search results. This implementation is done in a Kaggle notebook and is provided as a .ipynb file.

## Table of Contents
- [Introduction](#introduction)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Pinecone Integration](#pinecone-integration)
- [Reciprocal Rank Fusion (RRF)](#reciprocal-rank-fusion-rrf)

## Introduction
Retrieval-Augmented Generation (RAG) is a powerful method that enhances the generation capabilities of language models by incorporating external knowledge through a retrieval mechanism. This project takes RAG a step further by employing a hybrid search approach. It utilizes both vector search for semantic similarity and keyword search for exact matches, ensuring a more robust and precise retrieval process.

## Features
- **Hybrid Search:** Combines vector search and keyword search for better retrieval results.
- **Vector Search with Pinecone:** Utilizes Pinecone for efficient and scalable vector search.
- **Keyword Search:** Implements keyword search to handle exact matches and improve retrieval accuracy.
- **RRF (Reciprocal Rank Fusion):** Uses RRF to combine the results from both search methods.

## Installation
To get started with the project, follow these steps:

1. Clone the repository:
    ```bash
    git clone https://github.com/your-username/hybrid-search-rag.git
    cd hybrid-search-rag
    ```

2. Set up Pinecone:
    - Create an account on [Pinecone](https://www.pinecone.io/).
    - Obtain your API key and index name from Pinecone.
    - Set up your environment variables(optional):
    ```bash
    export PINECONE_API_KEY='your-pinecone-api-key'
    export PINECONE_INDEX_NAME='your-index-name'
    ```

## Usage
To run the project, execute the following command:
```bash
python main.py
```

Alternatively, you can explore and run the implementation in the provided Kaggle notebook (`https://www.kaggle.com/code/taniisshhaa/hybrid-search-rag-with-rrf`).

## Pinecone Integration
Pinecone is a vector database that provides high-performance, scalable, and low-latency vector search capabilities. In this project, Pinecone is used to perform vector searches, allowing the system to find semantically similar documents efficiently.

### Key Benefits of Pinecone:
- **Scalability:** Handles large-scale vector data seamlessly.
- **Performance:** Offers low-latency searches, ensuring quick retrieval.
- **Ease of Use:** Provides a user-friendly API for easy integration.

To learn more about Pinecone, visit their [official website](https://www.pinecone.io/).

## Reciprocal Rank Fusion (RRF)
Reciprocal Rank Fusion (RRF) is a method used to combine the results from multiple ranking algorithms. It assigns scores to documents based on their ranks in different search results. The core idea is that highly ranked documents in any of the individual search results should receive a high overall score.

### How RRF Works:
- Each document is given a score based on its rank in different search results.
- The score is calculated as the reciprocal of the rank plus a constant (depends on vectorDB- between 1 to 60) to avoid division by zero.
- The scores from different search results are then summed up to get the final score for each document.

### Benefits of RRF:
- **Combines Strengths:** Merges the strengths of different search methods, improving overall retrieval performance.
- **Robustness:** Provides a more stable ranking by considering multiple ranking signals.
- **Simplicity:** Easy to implement and understand.  
