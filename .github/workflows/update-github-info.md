---
name: update-github-info
description: Draft website updates for Mona's GitHub Info site from official GitHub sources.
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
---

# Update Mona's GitHub Info website

Purpose: keep Mona's GitHub Info website current using Mona's notes and recent official GitHub announcements.

Read notes/mona-notes.md first. Use web-fetch to review:
- GitHub Blog: https://github.blog/latest/
- GitHub Changelog: https://github.blog/changelog/

Identify updates relevant to Mona's audience, then modify only site/content/github-info.md.

Keep the existing document style. Add concise, practical updates with clear headings, short summaries, publication dates when available, and direct source links. Do not invent facts or change unrelated website files.

Open a pull request for Mona to review. Include a clear summary listing the notes and source updates used. Do not write directly to main; rely on safe-outputs with create-pull-request. Leave all proposed changes for human review before merging.
