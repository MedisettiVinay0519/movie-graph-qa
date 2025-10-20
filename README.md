# Movie Graph RAG: LangChain, Neo4j, and Groq

This project is contained within a single Jupyter Notebook (`Movie_graph.ipynb`). It demonstrates an end-to-end workflow for building a **Knowledge Graph (KG)** and implementing a **Retrieval-Augmented Generation (RAG)** system that enables natural language querying (NLQ) over graph data.

It combines **LangChain** for orchestration, the **Neo4j** graph database for data storage, and a **Large Language Model (LLM)**—specifically **Groq's Gemma2-9b-It**—for both knowledge extraction and query translation.

## Key Features

* **Technology Stack:** Integrates LangChain, Neo4j, and the Groq LLM for a high-performance RAG pipeline.
* **Graph Creation from Text:** Demonstrates using the `LLMGraphTransformer` to extract structured data (entities and relationships) from raw, unstructured text.
* **Movie Data Ingestion:** Loads a public movie dataset using a powerful Cypher `LOAD CSV` query, creating a cinematic knowledge graph with `Movie`, `Person`, and `Genre` nodes connected by `:ACTED_IN`, `:DIRECTED`, and `:IN_GENRE` relationships.
* **Natural Language Querying (RAG):** Implements the **`GraphCypherQAChain`**, which is the core of the RAG system. This chain performs three steps:
    1.  Translates an English question (e.g., "Who directed GoldenEye?") into a precise **Cypher query** using the LLM.
    2.  Executes the Cypher query against the Neo4j graph.
    3.  Synthesizes the factual results into a natural, human-readable answer.

## Getting Started

### Prerequisites

* **Python 3.8**
* Access to a **Neo4j Database** instance (Cloud or Local).
* A **Groq API Key**.

### Installation

Install the required Python packages using pip:

```bash
pip install --upgrade --quiet  langchain langchain-community langchain-groq neo4j langchain_experimental
