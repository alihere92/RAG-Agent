#RAG Agent – Supabase + Gemini + n8n Workflow

This project is a fully automated RAG (Retrieval-Augmented Generation) AI Agent built using n8n, Google Gemini, Supabase Vector Store, and PostgreSQL chat memory.
It allows you to upload documents, generate embeddings, store them in Supabase, and run an AI chat agent that responds with contextual knowledge retrieved from stored embeddings.

#Features
Google Gemini Chat Model for AI responses
RAG-based contextual answers using Supabase vector search
Document ingestion via Google Drive
Automatic embeddings generation with the Gemini Embedding model
Persistent chat memory using PostgreSQL
Fully automated workflow triggered by chat messages
n8n-based visual orchestration

#Architecture Overview
This workflow integrates several powerful components:

1. Chat Trigger
Listens for incoming chat messages (chatTrigger node)
Sends query to the AI Agent

2. AI Agent (LangChain Agent)
Receives user queries
Calls:
Gemini Chat Model
Supabase Vector Store (as a Tool)
PostgreSQL memory storage

3. Google Gemini Chat Model
Provides natural language responses for the agent.

4. Supabase Vector Store
Stores:
Document embeddings
Retrieved chunks for RAG answers
Used in two modes:
Insert mode – for uploading new documents
Retrieve mode (Tool) – for answering queries

5. Default Document Loader
Converts binary file (DOCX, PDF, text) into a text format for embeddings.

6. Google Drive Integration
Downloads the source document from Google Drive before processing.

7. Embeddings Model (Gemini Embeddings)
Generates embeddings for all uploaded documents.

9. PostgreSQL Chat Memory
Stores long-term conversation memory:
Previous questions
Chat context
Historical responses
