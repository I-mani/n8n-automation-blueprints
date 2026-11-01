# Production-Ready n8n AI & Data Automation Blueprints

A collection of functional backend workflows engineered in n8n for agentic AI processing, data parsing, and automated pipeline monitoring.

---

## 🛠️ Blueprint 1: AI-Powered Text Processor & Sentiment Classifier
This workflow runs custom script engines to structure raw text, injects it into a database, runs it through an advanced LLM via Groq, and conditionally routes payloads to distinct team notification channels based on logic outcomes.

### Architectural Blueprint
*   **Trigger:** Manual Execution / API Call Webhook
*   **Data Processing:** Custom JavaScript Node parsing 3 distinct data items
*   **Database Management:** Multi-row data upserting into core sheets/tables
*   **AI Integration:** Basic LLM Chain running via Groq Chat Model for near-zero latency contextual parsing
*   **Routing Logic:** If/Else conditional split branching execution parameters
*   **Output Sync:** Automated Discord multi-channel response triggers

---

## 📦 Blueprint 2: Automated Inventory & Multi-Branch Order Processor
A dual-trigger operational workflow that pulls batched JSON data from a warehouse API, checks internal status fields, branches processing paths, aggregates calculation data, and alerts the operations team.

### Architectural Blueprint
*   **Trigger Infrastructure:** Dual configuration (Manual testing + Production-ready Cron Schedule Trigger)
*   **API Connection:** HTTP Request GET fetching batched items from an external warehousing data application
*   **Conditional Filter:** Evaluates data properties to triage orders into operational states
*   **Branch A (Processing Queue):** Updates database tables → Sets operational metadata payloads → Pushes to downstream order processing buckets
*   **Branch B (Archival Queue):** Deactivates stagnant files → Computes calculations via JS Script block → Triggers an instant alerting routine to Discord channels
