# 🎥 YouTube Video Summarizer

A **n8n workflow** that takes a YouTube video link, fetches its transcript, checks for previously summarized videos, summarizes short or long transcripts with OpenAI, and stores the result in Google Sheets.

## Workflow

```text
Paste YouTube Link
        ↓
Filter link
   ↙         ↘
Invalid     Valid
  ↓           ↓
Error    Fetch Transcript
             ↓
       Clean Transcript
             ↓
       Extract Video ID
             ↓
       Check Video History
          ↙       ↘
      Exists       New
        ↓            ↓
   Show Saved    Check Length
   Summary          ↓
                ┌───┴───┐
             Short     Long
               ↓         ↓
          OpenAI     Split Transcript
          Summary         ↓
                    OpenAI per Chunk
                         ↓
                  Combine Summaries
                         ↓
                    Show Summary
                         ↓
                   Save to History
```

## How It Works

1. **Paste YouTube Link** – accepts a YouTube video URL through an n8n form.
2. **Filter link** – validates the YouTube URL format before making an API request.
3. **Fetch Transcript** – gets the transcript using the Supadata API.
4. **Clean Transcript** – removes unnecessary whitespace and prepares the transcript.
5. **Extract Video ID** – extracts the unique YouTube video ID.
6. **Check Video History** – searches Google Sheets to see whether the video was already summarized.
7. **Check Length** – routes shorter transcripts directly to OpenAI and longer transcripts through chunking.
8. **Split Transcript** – divides long transcripts into smaller chunks.
9. **OpenAI** – generates summaries for the transcript or each transcript chunk.
10. **Combine Summaries** – combines chunk summaries before the final result is displayed.
11. **Show Summary** – displays the generated summary to the user.
12. **Save to History** – stores the video ID, URL, summary, and timestamp in Google Sheets.

## Result

You can paste a YouTube video link and receive an **AI-generated summary** with a short overview and key points.

Previously summarized videos can be returned from the **Google Sheets history**, helping avoid unnecessary AI processing.

## Tools Used

- n8n
- Supadata API
- OpenAI
- Google Sheets
- JavaScript
- YouTube Transcript

## Architecture

See [`architecture.png`](architecture.png).
