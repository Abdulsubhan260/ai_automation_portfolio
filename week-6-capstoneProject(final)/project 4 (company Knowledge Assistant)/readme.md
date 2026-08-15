# Option 4: Company Knowledge AI Assistant with Human Escalation

This enterprise RAG assistant provides instant answers to employee policy questions while enforcing strict hallucination boundaries and automated database escalations.

### Key Architectural Steps:
1. **Conversational Chat Interface:** Receives employee questions via a native chat trigger.
2. **Memory & Context Tracking:** Uses Simple Memory to maintain conversation history across multi-turn queries.
3. **RAG Document Search:** Queries a 384-dimensional Pinecone vector index (via Hugging Face embeddings) containing 20+ company SOPs.
4. **Strict Hallucination Guardrail:** Outputs source citations for valid queries, while responding with an `[ESCALATE]` tag for unverified topics.
5. **Automated Database Escalation:** Detects the `[ESCALATE]` tag downstream, logs the unanswered question into a Supabase PostgreSQL table, and alerts HR.

### Core Technologies Used:
* **Orchestration:** n8n (Self-Hosted on Localhost)
* **AI Agent & Memory:** Groq (Llama 3.1 8B) & Simple Memory
* **Vector Database & Storage:** Pinecone, Hugging Face Embeddings & Supabase PostgreSQL