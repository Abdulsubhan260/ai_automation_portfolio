# Week 6 Capstone Project: AI Customer Support CRM & RAG Automation

This production-grade system automates the intake, triaging, database logging, and resolution of incoming customer support tickets.

### **Key Architectural Steps:**
1. **Asynchronous Intake:** Captures support tickets via Webhooks and instantly responds to keep the client application responsive.
2. **AI Classification (Triage):** Groq Llama 3.1 extracts structured JSON data: category, priority, sentiment, and summary.
3. **Semantic Knowledge Search (RAG):** Queries a Pinecone vector database using Hugging Face embeddings to fetch relevant help policies.
4. **AI Response Drafting:** Leverages retrieved documentation to draft an accurate, highly contextual, and polite email response.
5. **PostgreSQL Database Logging:** Inserts customer details, triage metadata, and timestamps into a Supabase PostgreSQL table.
6. **Human-in-the-Loop Safeguard:** Pauses execution on high-priority tickets via a Wait node, requiring human approval to resume.

### **Core Technologies Used:**
* **Orchestration:** n8n (Self-Hosted on Localhost)
* **AI & Embeddings:** Groq (Llama 3.1 8B) & Hugging Face (all-MiniLM-L6-v2)
* **Databases:** Pinecone Vector Database & Supabase PostgreSQL
* **Notifications:** SMTP Email Protocols