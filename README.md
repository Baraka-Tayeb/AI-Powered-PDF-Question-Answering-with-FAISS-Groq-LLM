# AI-Powered-PDF-Question-Answering-with-FAISS-Groq-LLM
This repository contains a Retrieval-Augmented Generation (RAG) system developed to intelligently answer questions from PDF documents. The project demonstrates strong skills in natural language processing, vector databases, semantic search, and large language model integration.
The system can be integrated into real-world applications such as document assistants, knowledge management systems, customer support bots, and research tools.
🎯 Objective
To build an intelligent document Q&A engine that:

Extracts and processes text from PDF documents
Understands semantic meaning through embeddings
Retrieves relevant context using vector similarity search
Generates accurate, grounded answers using LLMs
Prevents hallucination by strictly using document content

This project showcases an end-to-end RAG workflow and reflects practical experience in developing deployable AI components.
🧠 Key Capabilities

PDF Text Extraction: Automatically extracts content from uploaded PDFs
Semantic Search: Finds relevant information using vector similarity (not just keywords)
Context-Aware Answers: Retrieves top-k most relevant chunks before generating responses
Hallucination Prevention: Strict prompting ensures answers come only from the document
Production-Ready Design: Clean OOP architecture with reusable agent class
Scalable Vector Storage: FAISS-powered efficient search over thousands of chunks

🏗️ Technical Approach
The system follows a structured RAG pipeline:
1. Document Processing

PDF text extraction using PyMuPDF
Text normalization and cleaning
Intelligent chunking with overlap for context preservation

2. Embedding Generation

Converts text chunks into dense vector representations
Uses all-MiniLM-L6-v2 sentence transformer (384 dimensions)
Creates semantic fingerprints of document content

3. Vector Storage

Builds FAISS index for efficient similarity search
L2 distance metric for chunk retrieval
Scalable to millions of documents

4. Query Processing

User question embedded into same vector space
Semantic search retrieves top-k relevant chunks
Context compilation from retrieved passages

5. Answer Generation

Groq LLM (Llama 3.1) generates natural language responses
Strictly grounded in retrieved context
Returns "not found" message when answer isn't in document

6. Production Architecture

ShoppingGuideAgent class encapsulates full pipeline
Modular design for easy integration
Configurable parameters (top_k, chunk_size, etc.)

This pipeline reflects standard practices used in modern RAG systems at scale.
🛠️ Technologies Used

Python
PyMuPDF - PDF text extraction
Sentence Transformers - Embedding generation
FAISS - Vector similarity search
LangChain - Text splitting utilities
Groq API - LLM inference (Llama 3.1)
NumPy - Numerical computations
Google Colab - Development environment
Use Cases

Research Assistants: Query academic papers and technical documents
Legal Document Analysis: Extract information from contracts and policies
Customer Support: Answer questions from product manuals
Educational Tools: Interactive learning from textbooks
Knowledge Management: Corporate document Q&A systems
