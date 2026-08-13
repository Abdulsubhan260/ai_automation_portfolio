# Option 2: AI Recruitment & Applicant Screening Funnel

This automated recruitment pipeline evaluates incoming job applications, extracts candidate skills, and streamlines HR review.

### Key Architectural Steps:
1. **Application Intake:** Receives candidate resumes, names, emails, and target job roles via Webhook.
2. **Database Persistence:** Logs raw applications into a Supabase PostgreSQL `applicants` table.
3. **AI Resume Parsing:** Groq Llama 3.1 analyzes the resume text, extracts skills, generates a summary, and calculates a 0-100 fit score.
4. **Automated Filtering:** Automatically rejects candidates with fit scores below 80, updating their status and sending rejection emails.
5. **Human Recruiter Gate:** Pauses high-fit candidates (>= 80) via a Wait node for human recruiter approval.
6. **Interview Scheduling:** Upon human approval, updates the database status to `Shortlisted` and dispatches an automated interview scheduling link.

### Core Technologies Used:
* **Orchestration:** n8n (Self-Hosted)
* **AI & Parser:** Groq (Llama 3.1 8B) & Structured Output Parser
* **Database:** Supabase PostgreSQL (`applicants` table)