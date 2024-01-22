## Retrieval Augmented Generation
This repository implements Offline Retrieval Augmented Generation (Offline-RAG), a framework for enhancing text generation models with retrieved knowledge, even when internet access is unavailable. It builds upon the popular RAG (Retrieval-Augmented Generation) approach, but uses pre-built document indexes for offline retrieval, making it ideal for applications like chatbots in remote environments or for sensitive data that should not be exposed online.

### Overall architecture:

![RAG diagram](https://github.com/jsztompka/RetrievalAugmentedGeneration/assets/1412985/b8004a5c-a02d-4b75-aac9-f9847e39ce63)

#### Major components:
* Embedding model - https://huggingface.co/BAAI/bge-small-en-v1.5 
Why this particular model? It's a relatively small model (compared to billion parameter models) and still placed in the top 10 leaderboards when it comes to embeddings
* Large Language Model - LLama-2
Main reason behind it was to try to run complete offline RAG pipeline on my home PC. This required a LLM that can be used to power local RAG pipeline and be capable of accepting context for question answering without sending data via the internet.
* Transformers from HuggingFace - models and library
* LangChain - this library allows to easily "chain" multiple components such as VectorDB to a Large Language Model
* VectorDB - ChromaDB - the choice was dictated by simplicity - it can be run locally without any complex setup  

