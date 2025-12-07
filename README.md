RAG Agent – Supabase + Gemini + n8n Workflow

This project is a fully automated RAG (Retrieval-Augmented Generation) AI Agent built using n8n, Google Gemini, Supabase Vector Store, and PostgreSQL chat memory.
It allows you to upload documents, generate embeddings, store them in Supabase, and run an AI chat agent that responds with contextual knowledge retrieved from stored embeddings.

🚀 Features
Google Gemini Chat Model for high-quality AI responses
RAG-based contextual answers using Supabase vector search
Document ingestion via Google Drive
Automatic embeddings generation using the Gemini Embedding model
Persistent chat memory stored in PostgreSQL
Automated chat response workflow triggered by incoming messages
n8n-based visual and modular orchestration

🧩 Architecture Overview
This workflow integrates several powerful components to create an intelligent RAG agent:

1. Chat Trigger
Listens for incoming chat messages (chatTrigger node)
Sends the user query to the AI Agent

2. AI Agent (LangChain Agent)
Receives and processes user queries through:
Google Gemini Chat Model
Supabase Vector Store (as a retrieval tool)
PostgreSQL chat memory
Internal reasoning & tool execution pipeline

3. Google Gemini Chat Model
Generates natural language responses
Processes context from the vector store and memory

4. Supabase Vector Store
Stores:
Document embeddings
Retrieved chunks for RAG responses

Used in two modes:
Insert Mode — Stores new document embeddings
Retrieve Mode (Tool) — Searches for relevant context to answer queries

5. Default Document Loader
Converts binary documents (PDF, DOCX, TXT, etc.) into text
Prepares documents for embedding generation

6. Google Drive Integration
Downloads source files directly from your Google Drive
Sends them to the loader for processing

7. Gemini Embedding Model
Generates embeddings for documents
Embeddings are stored inside Supabase for vector search

8. PostgreSQL Chat Memory
Stores long-term conversational data:
Previous user queries
Chat context
Past responses

Conversation history for personalized answers

📌 How It Works (Workflow Overview)
Document Processing
Manual Trigger → Google Drive Download → Document Loader
→ Gemini Embeddings → Supabase Vector Store (Insert)

Chat Processing
Chat Trigger → AI Agent
→ Gemini Chat Model → Supabase Vector Search (RAG)
→ PostgreSQL Memory → Final Answer
