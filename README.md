# RAG Practice

A Retrieval-Augmented Generation (RAG) project built with **LangChain, Pinecone, and Groq**.

The goal of this project is to improve LLM responses by retrieving relevant context from a custom knowledge base before generating an answer.

## Tech Stack

- Python
- LangChain
- Pinecone
- Groq
- Vector Embeddings
- Large Language Models
- Retrieval-Augmented Generation (RAG)

## How It Works

The application follows a Retrieval-Augmented Generation pipeline:

1. Documents are processed and prepared for retrieval.
2. Text is converted into vector embeddings.
3. Embeddings are stored in **Pinecone**.
4. When a user asks a question, the query is compared against the stored vectors.
5. Pinecone performs semantic search and returns the most relevant context.
6. **LangChain** manages the retrieval workflow and combines the retrieved context with the user's question.
7. The completed prompt is sent to an LLM through **Groq**.
8. Groq provides low-latency inference and generates the final response.
9. The user receives an answer grounded in the retrieved knowledge-base content.

## Architecture

```text
User Question
      |
      v
Query Processing
      |
      v
Vector Embedding
      |
      v
Pinecone Similarity Search
      |
      v
Relevant Context
      |
      v
LangChain RAG Pipeline
      |
      v
Prompt + Retrieved Context
      |
      v
Groq LLM Inference
      |
      v
Final Response
