# Option 3: AI Lead Qualification & B2B Sales Router

This enterprise lead management system ingests B2B inquiries, enriches lead data, calculates qualification scores, and routes warm leads to sales reps.

### Key Architectural Steps:
1. **Lead Intake & Validation:** Receives incoming lead payloads via Webhook and validates required contact fields.
2. **API Data Enrichment:** Queries the Agify API to enrich the lead profile with predicted demographics based on their first name.
3. **AI Lead Scoring:** Groq Llama 3.1 evaluates budget, company size, and service interest, outputting a 0-100 lead score and buying intent.
4. **Relational Storage:** Persists enriched lead data and AI metrics into a Supabase PostgreSQL `leads` table.
5. **Human-in-the-Loop Sales Gate:** Pauses qualified enterprise leads (>= 80 score) via a Wait node for sales manager review.
6. **Priority Routing:** Dispatches discovery call booking links for approved enterprise leads and routes low-value leads to a nurture list.

### Core Technologies Used:
* **Orchestration:** n8n (Self-Hosted)
* **API & AI:** Agify API & Groq (Llama 3.1 8B)
* **Database:** Supabase PostgreSQL (`leads` table)