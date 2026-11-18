# Rules for this repository

Decided by the owner on 18 November 2026.

## The master copy

- `index.html` on `main` is the master copy of the coach. There is no other master.
- Never replace the whole file with a copy from somewhere else, for example an export from a chat. Bring changes in as edits on top of the current file.
- Every change goes through a pull request, started from the latest `main`. If `main` moves while you work, merge it into your branch and check your change again before you ask for a merge.

## What the file must stay free of

This repository is only for testing. The end product is `index.html` on its own, handed to another team. So the file has to be clean by itself, including its comments, its meta tags and any encoded text.

- No names of people, real or invented. Refer to people by their role, for example a manager or a new starter.
- No mention of Claude or Anthropic, and no `claude:` meta tag.
- No name of a company, a client or a consultant, and no "the firm" in comments.
- No comment that points at a file outside the page, such as `app.js`, `setup.js` or `build.py`.
- No web address and nothing loaded from outside. Keep the Content-Security-Policy meta tag (the browser lock) and the empty icon link in the page head.

## Check before every pull request

Run this in the repository folder. It must print nothing.

```bash
grep -n -i -E 'claude|anthropic|fromCharCode|the firm|app\.js|setup\.js|build\.py|https?://' index.html
```

The command cannot find names of people. Read any text you add or change for those yourself.
