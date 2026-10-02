# 🎫 Multi-Channel Customer Support Triage & Ticket Routing Pipeline

An **n8n workflow** that automates customer support ticket classification, knowledge retrieval, human approval, response generation, and email delivery.

## Workflow

```text
Customer Ticket
      ↓
Webhook
      ↓
Edit Fields
      ↓
Ticket Classification
      ↓
Category + Urgency + Sentiment
      ↓
       If
      ↙  ↘
Low      High/Other
 ↓           ↓
Knowledge   Supabase
Retrieval   (Escalated)
 ↓           ↓
RAG         Slack Approval
 ↓           ↓
Response    Approve / Reject
Generation      ↓
 ↓          Approved
Supabase        ↓
 ↓          Knowledge Retrieval
Slack           ↓
 ↓          RAG Response
Email            ↓
              Supabase
                ↓
              Slack
                ↓
              Email
```

## How It Works

1. **Webhook** – receives customer support tickets through an HTTP POST request.

2. **Edit Fields** – extracts the customer's name, email, source, and message.

3. **Ticket Classification** – Gemini classifies each ticket into:
   - Category: `billing`, `technical`, `account`, or `general`
   - Urgency: `low`, `medium`, or `high`
   - Sentiment: `positive`, `neutral`, or `negative`

4. **Routing** – an IF node checks the ticket urgency and routes the request accordingly.

5. **Knowledge Retrieval** – the customer message is converted into an embedding and sent to Supabase for similarity search using the `match_documents` RPC function.

6. **RAG Response Generation** – the retrieved information is provided to Gemini to generate a concise customer-facing response without inventing unsupported information.

7. **Supabase Storage** – ticket details, classification results, generated responses, and ticket status are stored in the `support_tickets` table.

8. **Slack Approval** – escalated tickets are sent to Slack with **Approve** and **Reject** actions for human review.

9. **Approval Webhook** – receives the Slack button action and identifies whether the ticket was approved or rejected.

10. **Approved Ticket Processing** – approved tickets are updated in Supabase and sent through the knowledge retrieval and response-generation pipeline.

11. **Response Ready** – the generated response is saved in Supabase and a Slack notification is sent to indicate that the response is ready.

12. **Gmail** – the final customer-facing response is sent through Gmail.

## Key Features

- Customer support ticket intake through Webhooks
- Automated category, urgency, and sentiment classification
- Urgency-based ticket routing
- Human-in-the-loop Slack approval
- Retrieval-Augmented Generation (RAG)
- Semantic similarity search using embeddings
- Supabase ticket storage
- AI-generated customer support responses
- Approval and rejection workflow
- Automated Gmail response delivery
- Slack notifications for ticket status updates

## Tools Used

- n8n
- Webhooks
- Google Gemini
- Gemini Embeddings
- Supabase
- PostgreSQL / pgvector
- REST API
- HTTP Request
- JavaScript
- Slack
- Gmail
- RAG

## Architecture

See [`architecture.png`](architecture.png).