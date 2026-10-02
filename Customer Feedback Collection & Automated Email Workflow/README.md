# Customer Feedback Automation with n8n

An automated customer feedback workflow built with **n8n, Google Sheets, and Gmail**.

The workflow monitors a Google Sheets response sheet for newly submitted feedback, prepares the feedback data, stores it in a separate analytics sheet, and automatically sends a personalized confirmation email to the customer.

## Architecture

```text
Customer submits feedback
          │
          ▼
   Google Form / Sheet
          │
          ▼
 ┌──────────────────────┐
 │ Google Sheets Trigger│
 │     Row Added        │
 └──────────┬───────────┘
            │
            ▼
 ┌──────────────────────┐
 │     Edit Fields      │
 │                      │
 │ • Submission time    │
 │ • Satisfaction score │
 └──────────┬───────────┘
            │
            ▼
 ┌──────────────────────┐
 │ Google Sheets        │
 │ Append Analytics Row │
 └──────────┬───────────┘
            │
            ▼
 ┌──────────────────────┐
 │        Gmail         │
 │ Personalized Email  │
 └──────────┬───────────┘
            │
            ▼
       Customer receives
       confirmation email
```

## Workflow

### 1. Google Sheets Trigger

The workflow listens for a newly added row in the feedback response sheet.

The incoming data includes:

- Customer name
- Email
- Overall rating
- Feedback

### 2. Edit Fields

The workflow creates/normalizes additional fields:

- `SubmittedAt` — current timestamp
- `SatisfactionScore` — extracted from the overall rating

### 3. Append Feedback to Analytics Sheet

The processed feedback is appended to a separate Google Sheet used for feedback analytics.

Stored information includes:

- Submission timestamp
- Customer name
- Email
- Overall rating
- Satisfaction score
- Feedback

This keeps the original response collection separate from the analytics dataset.

### 4. Automated Gmail Response

After the feedback is stored successfully, n8n sends a personalized email to the customer.

Example:

> Hi Customer,  
> Thank you for taking the time to submit your feedback.  
> We received your response successfully.  
> Your satisfaction score: 5/5  
> We really appreciate your feedback.

## Tech Stack

- **n8n** — workflow automation and orchestration
- **Google Sheets** — feedback collection and analytics storage
- **Gmail** — automated customer communication
- **Google Forms/Sheets** — response collection

## Key Concepts Demonstrated

- Event-driven automation
- Google Sheets integration
- Data transformation
- Field mapping
- Automated email communication
- Multi-step workflow orchestration
- Third-party API/service integrations
- Customer feedback data pipeline

## Use Case

This workflow can be used by a company after a customer submits a feedback form.

Instead of manually:

1. Checking new responses
2. Copying data into an analytics sheet
3. Sending confirmation emails

the entire process happens automatically.

## Workflow Flow

```text
New Feedback
     ↓
Detect New Row
     ↓
Process Feedback
     ↓
Store in Analytics Sheet
     ↓
Send Confirmation Email
```

## n8n Workflow

The workflow export is available in:

```text
workflow.json
```

You can import this JSON file into n8n to recreate the workflow.

> Note: Google Sheets and Gmail credentials must be configured in your own n8n instance. Credentials and secret values should never be committed to GitHub.

## Future Improvements

Possible production-level improvements:

- Add feedback sentiment analysis using an LLM
- Automatically classify feedback as Positive / Neutral / Negative
- Send low-rating feedback to a support team
- Store analytics in PostgreSQL
- Create a feedback dashboard
- Add Slack/Teams notifications
- Add retry and error-handling workflows
- Prevent duplicate processing
- Add customer segmentation
- Generate weekly feedback summaries using AI

## Project Structure

```text
customer-feedback-automation/
│
├── README.md
├── workflow.json
├── architecture.png
└── screenshots/
```

## Learning Outcome

This project demonstrates how **n8n can connect multiple business services into an automated workflow**, turning a simple customer feedback submission into a complete data-processing and communication pipeline.

---

**Built with n8n ⚡**
