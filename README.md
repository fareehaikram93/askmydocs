# askmydocs
RAG assistant that cites its sources, or admits it doesn't know



A retrieval-augmented generation (RAG) assistant that answers questions
strictly from your own documents — and shows you exactly where each answer
came from.

## Why this exists

General-purpose chatbots like ChatGPT don't know your private documents,
research papers, or internal knowledge base. When asked about them, they
either refuse or hallucinate. This app solves that by retrieving the most
relevant passages from your PDFs and grounding every answer in them.

## What it does

- Upload PDFs and index them into a vector database
- Ask questions in natural language
- Get answers **with source citations** (file name + page number)
- Says "I don't know" when the answer isn't in your documents

## How it works

PDFs → text extraction → chunking → embeddings (all-MiniLM-L6-v2)
     → Chroma vector store → top-k retrieval → LLM (Groq) → cited answer

## Tech stack

- Python, Streamlit (UI)
- sentence-transformers (embeddings)
- ChromaDB (vector database)
- pypdf (PDF parsing)
- Groq API (LLM inference)

## Try it

Upload a few PDFs, wait for indexing, then ask something specific.
Answers include [1], [2] citations you can verify against the source.
