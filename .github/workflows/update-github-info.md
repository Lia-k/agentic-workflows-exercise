---
name: update-github-info
description: Draft website updates for Mona's GitHub Info site from official GitHub sources.
engine:
  id: copilot
  model: gpt-4.1
on:
  workflow_dispatch:
  schedule:
    - cron: '17 9 * * *'
safe-outputs:
  create-pull-request:
    title-prefix: "[mona] "
    draft: true
    fallback-as-issue: false
tools:
  edit:
  web-fetch:
network:
  allowed:
    - github.com
    - github.blog
    - awesome-copilot.github.com
---

# Update Mona's GitHub Info website

Purpose: keep Mona's GitHub Info website current using Mona's notes and recent GitHub ecosystem updates.

Read notes/mona-notes.md first. Review recent items from all three sources:
- GitHub Blog: https://github.blog/latest/ or its official feed at https://github.blog/feed/
- GitHub Changelog: https://github.blog/changelog/ or its official feed at https://github.blog/changelog/feed/
- Awesome Copilot workflows: https://awesome-copilot.github.com/workflows/

Use any available web or network tool. If a helper named web-fetch is unavailable, use curl with redirects and read the downloaded HTML or RSS. A successful HTTP retrieval is valid web access; do not stop merely because a specific helper is absent. Read enough of each response to identify verifiable recent items and their direct source URLs.

Identify updates relevant to Mona's audience, then modify only site/content/github-info.md.

Keep the existing document style. Add concise, practical updates with clear headings, short summaries, publication dates when available, and direct source links. Do not invent facts or change unrelated website files.

Open a pull request for Mona to review. Include a clear summary listing Mona's notes and the Blog, Changelog, and Awesome Copilot updates used. Do not write directly to main; rely on safe-outputs with create-pull-request. Leave all proposed changes for human review before merging.
