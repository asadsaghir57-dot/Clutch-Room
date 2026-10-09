# Clutch Room

A sports media site concept — recaps, previews, odds and debate-style coverage across football, MLB, tennis, NFL, NBA, padel, cricket, UFC, boxing and F1, ranked by what's actually happening right now rather than a fixed menu order.

## Deploying

This is a single static `index.html` — no build step. On [Vercel](https://vercel.com/new), import this repo and deploy with the default "Other" / static framework preset; no configuration needed.

## Note on the live tracker

The homepage's live score strip and the F1/MLB/padel live-update features use a Claude Artifact-platform capability (`window.claude.use('db')`) that only exists when this page is served from claude.ai's Artifact system. When deployed here on Vercel as a plain static site, that API isn't present — the code already checks for it and no-ops gracefully, so the rest of the site works normally, but the live-updating strip itself won't activate. Replacing it with a real backend (a database + API route) is the next step if live updates are needed outside the Artifact platform.
