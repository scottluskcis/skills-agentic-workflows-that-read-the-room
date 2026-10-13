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

Read `notes/mona-notes.md` before making changes.

Web fetch these official sources:

- https://github.blog/latest/
- https://github.blog/changelog/

Update `site/content/github-info.md` with concise, practical information that
helps developers learn GitHub faster. Mention the source for information from
the GitHub Blog or GitHub Changelog.

Open a pull request for Mona to review. Use a title that mentions Mona or
GitHub Info. Do not write directly to `main`; rely on the
`create-pull-request` safe output.
