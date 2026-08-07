# Petalnex AI Automation Internship Portfolio

This repository contains all my practical learning, daily tasks, weekly assignments, and my final Capstone project completed during my 6-week AI Automation Internship at Petalnex Pvt. Ltd.

---

##  Week 6: Final Capstone Project — AI Customer Support CRM & RAG Automation

*   **Location in Repository:** [Week 5, Day 6 - Final Capstone](./Week-5-Production-and-Databases/week%205%20day%206)
*   **Project Goal:** To replace a highly inefficient, manual support ticketing queue with an error-safe, secure, AI-powered triage and automated retrieval system.

### **How the System Works (End-to-End Pipeline)**
1.  **Asynchronous Intake:** A webhook receives incoming customer support queries and instantly returns a `200 OK` response to keep the client responsive, running the rest of the logic in the background.
2.  **AI Classification (Triage):** Groq Llama 3.1 8B parses the email body, extracting strict JSON metadata: `category`, `priority`, `sentiment`, `department`, and `summary`.
3.  **Knowledge Retrieval (RAG):** The system takes the AI's clean summary, generates a vector embedding using Hugging Face, and runs a semantic search in Pinecone across our company help docs to retrieve the exact solution.
4.  **AI Response Drafting:** A secondary LLM node reads the retrieved help documents and drafts a personalized, polite, and highly accurate email reply.
5.  **Relational Database Logging:** The ticket, along with its unique ID, customer details, and AI metadata, is saved in a cloud PostgreSQL database (Supabase).
6.  **Human-in-the-Loop Safeguard:** If the ticket is categorized as Urgent/High, the system blocks automatic mailing, pauses the workflow via a Wait node, and alerts an admin. Once a human clicks "Approve" via a secure URL, the drafted response is dispatched.

---

##  Completed Daily Tasks & Assignments

###  Week 1: Automation Foundations & n8n Core
*   [Day 1: Onboarding & BPA Opportunities](./Week-1-Foundations/week%201%20day%201)
*   [Day 2: Scheduled Daily Reminder](./Week-1-Foundations/week%201%20day%202/workflow.json)
*   [Day 3: JSON Data Shaping & Classification](./Week-1-Foundations/week%201%20day%203/workflow.json)
*   [Day 4: Logic Branching & Transformation](./Week-1-Foundations/week%201%20day%204/workflow.json)
*   [Day 5: Google Sheets & Email Automation](./Week-1-Foundations/week1%20day%205/workflow.json)
*   [Day 6 (Assignment 1): Candidate Screening Automation](./Week-1-Foundations/week1%20day%206/workflow.json)

###  Week 2: APIs, Webhooks, and System Integration
*   [Day 7: API Fundamentals & Postman Exploration](./Week-2-APIs-and-Integration/week%202%20day%201)
*   [Day 8: HTTP Request Node & Authentication](./Week-2-APIs-and-Integration/week%202%20day%202/workflow.json)
*   [Day 9: JavaScript Data Transformations (Code Node)](./Week-2-APIs-and-Integration/week%202%20day%203/workflow.json)
*   [Day 10: Event-Driven Webhooks](./Week-2-APIs-and-Integration/week2%20day%204/workflow.json)
*   [Day 11: Multi-System Enrichment Integration](./Week-2-APIs-and-Integration/week%202%20day%205/workflow.json)
*   [Day 12 (Assignment 2): Automated Lead Management System](./Week-2-APIs-and-Integration/week%202%20day%206/workflow.json)

###  Week 3: Generative AI, LLMs & Prompt Engineering
*   [Day 13: LLM Provider Manual Postman Evaluations](./Week-3-Generative-AI-Prompting/week%203%20day%201)
*   [Day 14: Prompt Engineering & Structured JSON Prompts](./Week-3-Generative-AI-Prompting/week%203%20day%202)
*   [Day 15: LLM Categorizer Chain](./Week-3-Generative-AI-Prompting/week3%20day%203/workflow.json)
*   [Day 16: Structured AI Output & Fallback Parsing](./Week-3-Generative-AI-Prompting/week%203%20day%204/workflow.json)
*   [Day 17: Provider Comparison & Evaluation Report](./Week-3-Generative-AI-Prompting/week%203%20day%205)
*   [Day 18 (Assignment 3): AI Customer Support Triage System](./Week-3-Generative-AI-Prompting/week%203%20day%206/workflow.json)

###  Week 4: RAG, Vector Databases & AI Agents
*   [Day 19: RAG Architecture & Fundamentals](./Week-4-RAG-and-AI-Agents/week%204%20day%201/RAG-Explained.pdf)
*   [Day 20: Document Ingestion & Embeddings Pipeline](./Week-4-RAG-and-AI-Agents/week%204%20day%202/workflow.json)
*   [Day 21: RAG Policy Assistant](./Week-4-RAG-and-AI-Agents/week%204%20day%203/workflow.json)
*   [Day 22: AI Agent with Conversation Memory](./Week-4-RAG-and-AI-Agents/week%204%20day%204/workflow.json)
*   [Day 23: Multi-Tool Agent with Human Safeguards](./Week-4-RAG-and-AI-Agents/week%204%20day%205/workflow.json)
*   [Day 24 (Assignment 4): Company Knowledge AI Assistant (Pinecone + HF)](./Week-4-RAG-and-AI-Agents/week%204%20day%206/workflow.json)

###  Week 5: Databases, Security, and Production-Grade Workflows
*   [Day 25: Relational Postgres Database CRUD (Supabase)](./Week-5-Production-and-Databases/week5%20day%201/workflow.json)
*   [Day 26: Resilient Error Handling & Node Retries](./Week-5-Production-and-Databases/week%205%20day%202/workflow.json)
*   [Day 27: Webhook Endpoint Header Security](./Week-5-Production-and-Databases/week%205%20day%203/workflow.json)
*   [Day 28: Human-in-the-Loop Approval (Wait Node)](./Week-5-Production-and-Databases/week5%20day%204/workflow.json)
*   [Day 29: Performance Optimization & Data Pinning](./Week-5-Production-and-Databases/week%205%20day%205/workflow.json)
*   [Day 30 (Assignment 5): AI-Assisted Recruitment Automation](./Week-5-Production-and-Databases/week%205%20day%206/workflow.json)