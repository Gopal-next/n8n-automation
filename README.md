# n8n Automation Portfolio

A collection of practical workflow automation projects built with **n8n**, integrating business applications, APIs, data processing, and AI services.

## Projects

| # | Project | Focus | Technologies |
|---|---|---|---|
| 01 | [Customer Feedback Automation](./01-customer-feedback-automation/) | Collect feedback, store analytics data, and send automated email responses | n8n, Google Sheets, Gmail |

---

## Current Project

### Customer Feedback Automation

An event-driven workflow that:

```text
Customer submits feedback
          ↓
   Google Sheets Trigger
          ↓
      Edit Fields
          ↓
  Analytics Google Sheet
          ↓
   Automated Gmail
          ↓
 Customer confirmation
```

The workflow demonstrates:

- Google Sheets trigger automation
- Data transformation and field mapping
- Feedback analytics storage
- Personalized Gmail communication
- Multi-step workflow orchestration
- Integration between multiple business services

See the complete project documentation inside the project directory.

---

## What This Portfolio Demonstrates

As more workflows are added, this repository will cover practical concepts such as:

- Workflow automation
- Event-driven processes
- API integrations
- Webhooks
- Data transformation
- Database operations
- AI/LLM integrations
- RAG workflows
- Human-in-the-loop automation
- Error handling and retries
- Authentication and secure credential management

---

## Typical Architecture

```text
                    External Event
                          │
                          ▼
                   n8n Trigger
                          │
                          ▼
                 Data Processing
                          │
                          ▼
                  Business Logic
                          │
              ┌───────────┼───────────┐
              ▼           ▼           ▼
            API         Database     AI/LLM
              │           │           │
              └───────────┼───────────┘
                          ▼
                   Decision / Router
                          │
                          ▼
                       Action
```

The exact architecture depends on the individual workflow.

---

## Repository Structure

```text
n8n-automation-portfolio/
│
├── README.md
│
├── 01-customer-feedback-automation/
│   ├── README.md
│   ├── workflow.json
│   ├── architecture.png
│   └── screenshots/
│
└── ...
```

Each completed project can contain:

- `README.md` — project documentation
- `workflow.json` — n8n workflow export
- `architecture.png` — workflow architecture
- `screenshots/` — workflow and result screenshots

---

## Technologies

Depending on the workflow, this portfolio may use:

- **n8n**
- **Google Sheets**
- **Gmail**
- **REST APIs**
- **Webhooks**
- **PostgreSQL**
- **Python / FastAPI**
- **LLM APIs**
- **Vector databases**
- **RAG**
- **Docker**
- **Git / GitHub**

---

## Security

Credentials, API keys, passwords, access tokens, and other secrets should never be committed to the repository.

Review exported n8n workflows before publishing them publicly and keep sensitive configuration in secure credentials or environment variables.

---

## Goal

This repository showcases practical **n8n workflow automation**, progressing from straightforward business automations toward more advanced integrations involving APIs, databases, AI, RAG, and human-in-the-loop systems.
