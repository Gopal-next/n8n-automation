# n8n Automation Portfolio

A collection of **automation workflows built with n8n**, integrating APIs, SaaS platforms, data pipelines, and AI services.

## Projects

### 01. Customer Feedback Collection & Automated Email Workflow

Automated workflow for processing customer feedback, storing analytics data, and sending personalized email confirmations.

**Stack:** `n8n` · `Google Sheets` · `Gmail` · `Workflow Automation`

[View Project →](https://github.com/Gopal-next/n8n-automation/tree/main/Customer%20Feedback%20Collection%20%26%20Automated%20Email%20Workflow)

---

### 02. India News Daily Email

Automated workflow that fetches the latest India news, selects the top 10 headlines, formats them into an HTML newsletter, and sends them to Gmail in a single email.

**Stack:** `n8n` · `RSS` · `HTTP Request` · `XML` · `JavaScript` · `Gmail`

[View Project →](https://github.com/Gopal-next/n8n-automation/tree/main/Daily%20AI%20News%20Digest)

---

### 03. YouTube Video Summarizer

AI-powered n8n workflow that accepts a YouTube video link, fetches its transcript using the Supadata API, checks previously summarized videos, and generates summaries with OpenAI. Long transcripts are automatically split into chunks before summarization, and results are stored in Google Sheets for future reuse.

**Stack:** `n8n` · `Supadata API` · `OpenAI` · `Google Sheets` · `JavaScript` · `YouTube Transcript`

[View Project →](https://github.com/Gopal-next/n8n-automation/tree/main/Yotube%20video%20summarizer)

---

### 04. Multi-Channel Customer Support Triage & Ticket Routing Pipeline

AI-powered n8n workflow that receives customer support tickets through a webhook, classifies them by category, urgency, and sentiment, and routes tickets based on urgency. Escalated tickets are sent to Slack for human approval before generating a customer response using retrieved information.

The workflow uses embeddings and similarity search with Supabase to retrieve relevant information, generates concise customer-facing responses with Gemini, stores ticket data and status in Supabase, and sends approved responses through Gmail.

**Stack:** `n8n` · `Webhooks` · `Google Gemini` · `Gemini Embeddings` · `Supabase` · `PostgreSQL` · `pgvector` · `Slack` · `Gmail` · `REST API` · `HTTP Request` · `JavaScript` · `RAG`

[View Project →](https://github.com/Gopal-next/n8n-automation/tree/main/Multi-Channel%20Customer%20Support%20Triage%20%26%20Ticket%20Routing%20Pipeline)

---

## Technical Focus

* **Event-driven workflow automation**
* **API and RSS integration**
* **AI-powered workflow automation**
* **Data transformation and field mapping**
* **Conditional routing and workflow logic**
* **Transcript processing and chunking**
* **Automated email notifications**
* **HTML email generation**
* **Multi-step workflow orchestration**
* **AI summarization and data storage**
* **Webhook-based ticket intake**
* **Human-in-the-loop approval workflows**
* **Semantic search and vector similarity retrieval**
* **AI-powered ticket classification**
* **Sentiment and urgency analysis**
* **RAG-based response generation**
* **Database record management**
* **Slack-based workflow approvals**

## Technology

`n8n` · `Google Sheets` · `RSS` · `Gmail` · `OpenAI` · `Google Gemini` · `Supabase` · `PostgreSQL` · `pgvector` · `Slack` · `Supadata API` · `JavaScript` · `REST API` · `HTTP Request`