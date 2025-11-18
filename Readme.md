                    📘 RAG-Powered AI Chatbot using Mistral (HuggingFace API)
HCLTech Campus Hiring – GenAI Hackathon Submission
____________________________________________________________________________________________________
🚀 Project Overview

This project is a Retrieval-Augmented Generation (RAG) powered chatbot built using Python, FAISS, and the Mistral model from HuggingFace (via API key).

Our solution is divided into three clearly defined phases as required by the problem statement:

Data Ingestion & Vector Store Creation

LLM Memory + RAG Pipeline Integration

Frontend Chatbot Interface + End-to-End Workflow

____________________________________________________________________________________________________
✅ Phase 1 — Data Ingestion, Chunking, Embedding & Vector DB

In the first phase, we prepare the knowledge base that the chatbot will use for retrieval.

1️⃣ Load PDFs

We allow the user to upload any number of PDF documents. These documents are extracted into raw text using:

--> PyPDFLoader (LangChain) OR pdfplumber

2️⃣ Split Text into Chunks

LLMs cannot process very long text directly.
Therefore, we break the text into overlapping chunks:

--->  Chunk size: 500 characters

--->  Chunk overlap: 50 characters

This helps preserve context while keeping embeddings clean.

3️⃣ Convert Chunks into Embeddings

We generate vector embeddings using a sentence-transformer model: all-MiniLM-L6-v2

Embeddings convert text into high-dimensional vectors that capture meaning.

4️⃣ Store Vectors in FAISS Vector DB

We store all embeddings in a local FAISS index, enabling fast semantic search.

FAISS allows us to retrieve the most relevant chunks for any user query in milliseconds.

___________________________________________________________________________________________________
🧠 Phase 2 — Adding Memory & Connecting to the LLM (Mistral)

After building the vector database, we connect the retrieval pipeline to the LLM.

1️⃣ Creating Long-Term Memory for the Chatbot

We add:

Retrieval memory: retrieves context from the PDFs

This ensures answers remain consistent and context-aware.

2️⃣ Connecting the LLM (Mistral from HuggingFace)

We use the Mistral Instruct Model via HuggingFace API: mistral-7b-instruct-v0.3

3️⃣ RAG Pipeline Working

When a user asks a question: ---->  The question is embedded.

FAISS retrieves the most relevant document chunks.

Those chunks are sent as context to the Mistral model.

Mistral generates a grounded, factual answer.

__________________________________________________________________________________________________

               💬 Phase 3 — Frontend Chat Interface & End-to-End Chat Flow

In the final phase, we build an interface where users can chat with the RAG system.

We implement this using:

🖥️ Streamlit Frontend

Clean layout

Chat UI with chat bubbles

Display of retrieved context 

____________________________________________________________________________________________________

✨ End-to-End Chat Flow

--->  PDFs → Chunked → Embedded → Saved in FAISS

--->  User asks a question

--->  Semantic search retrieves relevant context

--->  Mistral model generates answer
  
--->  Answer + context shown in the chat
 
--->  This completes the full RAG pipeline.




🧱 Tech Stack

              Component	                                         Technology

              LLM                                                Mistral (HuggingFace API)
              Vector DB                                          FAISS
              Embeddings                                         MiniLM (sentence-transformers)
              Framework                                          Python, LangChain
              Frontend                                           Streamlit
              PDF Processing                                     pyPDFLoader, pdfplumber


🎯 Key Features

-->   Fully working RAG architecture

-->   Uses Mistral (free HuggingFace API)

-->   Handles any number of PDFs

-->   Fast semantic search using FAISS

-->   Clean UI for chatting & document upload






