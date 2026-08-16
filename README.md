# Content Nuke
 
An n8n workflow that turns one YouTube video into ready-to-post content. It watches a channel, transcribes new videos, and creates a LinkedIn post, a Twitter thread, a newsletter, and a thumbnail image — all with human approval before anything goes live.
 
## What It Does
 
1. **Watch** — Checks a YouTube RSS feed every hour for new videos.
2. **Download** — Gets the audio file if the video is longer than 60 seconds.
3. **Transcribe** — Uses Gemini to turn the audio into text.
4. **Generate** — Creates 4 pieces of content from the transcript:
   - LinkedIn post
   - Twitter/X thread (5 tweets)
   - Newsletter (subject line, TL;DR, story, takeaways)
   - Thumbnail image (16:9, with headline text)
5. **Review** — Sends everything to Slack for approval.
6. **Publish** — On approval, posts to LinkedIn and X, sends the newsletter by Gmail, and logs the run to Google Sheets.
## Tools Used
 
| Purpose | Tool |
|---|---|
| Workflow engine | n8n |
| Transcription + content + image | Google Gemini |
| Approval | Slack |
| Posting | LinkedIn, X (Twitter) |
| Email | Gmail |
| Logging | Google Sheets |
| YouTube audio | RapidAPI (youtube-mp36) |

## Setup
 
1. Import `Content_Nuke.json` into n8n.
2. Add your own credentials for: Google Gemini, Slack, LinkedIn, X, Gmail, Google Sheets.
3. Add your own RapidAPI key for the YouTube download step.
4. Set the RSS feed URL to the YouTube channel you want to track.
5. Update the Google Sheet ID and Slack channel ID to your own.
6. Turn the workflow on.
