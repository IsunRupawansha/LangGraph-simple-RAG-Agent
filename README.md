I built this AI-powered chatbot by first collecting and cleaning a domain knowledge base (FAQs, docs, and sample dialogs), then converting the content into embeddings using a sentence-embedding model and indexing them in a vector store (FAISS/Pinecone). Next I implemented a RAG pipeline with LangChain to retrieve relevant context and passed that context to an LLM (OpenAI / Hugging Face) using tuned prompt templates and simple conversation memory, plus fallback logic to reduce hallucinations. And deployed with basic tests. the repo includes scripts for data prep, embedding/indexing, RAG chains, prompt templates, connectors, and deployment.

How it Works
User Input → A user sends a query through the web interface or WhatsApp.
Embedding Generation → The query is converted into a vector embedding using a pre-trained embedding model.
Context Retrieval → The embedding is matched against a vector database (FAISS/Pinecone) to fetch the most relevant documents or knowledge base entries.
RAG Pipeline → The retrieved context is combined with the user query and passed into a Large Language Model (LLM) through LangChain.
Response Generation → The LLM generates a context-aware, human-like answer using the query + retrieved knowledge.
Memory & Logging → Conversations are stored for session memory and logging, helping improve future responses.
