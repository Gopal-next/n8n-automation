# 📰 India News Daily Email

A simple **n8n workflow** that gets the latest 10 India news headlines and sends them to Gmail as one clean HTML email.

## Workflow

```text
Manual Trigger
      ↓
HTTP Request
      ↓
XML
      ↓
Limit 10
      ↓
Code
      ↓
Gmail
```

## How It Works

1. **Manual Trigger** – starts the workflow.
2. **HTTP Request** – gets India news from an RSS feed.
3. **XML** – converts the RSS response into usable data.
4. **Limit 10** – keeps the top 10 news articles.
5. **Code** – creates one HTML email containing all 10 articles.
6. **Gmail** – sends the newsletter to the inbox.

## Result

You receive **one email containing the top 10 India news headlines**, with a clickable **READ ARTICLE →** button for each story.

## Tools Used

- n8n
- RSS
- HTTP Request
- XML
- JavaScript
- Gmail

## Future Improvement

Replace the **Manual Trigger** with a **Schedule Trigger** to automatically send the news every morning.

## Architecture

See [`architecture.png`](architecture.png).
