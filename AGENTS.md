# Documentation project instructions

## About this project

- This is the Mintlify documentation site for **bunnyOS**, a small-model AI platform.
- Pages are MDX files with YAML frontmatter. Configuration lives in `docs.json`.
- Run `mint dev` to preview locally; `mint broken-links` to check links.
- The audience is **non-technical end users**: cover what a feature is, why you'd use it, and how to use it.

## What bunnyOS is

- You chat with **bunny**, a personal AI agent that runs either **on your own device** (private, free) or in the **bunnyCompute** cloud (a decentralised network of contributor GPUs, paid in **Carrots**).
- bunny can use built-in tools, connected apps, and remote tool servers, and run **bunnyApps** (mini-apps).
- **Carrots** are the usage credit (spent on cloud requests); **OS** is a token you stake on Base to earn Carrots. You can also earn Carrots by contributing compute.
- The product source of truth is the app under `/Users/joe/Downloads/bunnyos/` (`frontend` = the app, `api` = the backend, `worker` = the native worker). Verify claims against it.

## Terminology

- The app is a modern chat app branded **bunny** — never call it a "terminal".
- Use **bunny** (the agent), **bunnyOS** (the platform/app), **bunnyCompute** (the cloud network), **bunnyApps** (mini-apps), **Carrots** (the credit), **OS** (the staked token).
- The app lives at **platform.bunnyos.ai**. The docs "Launch app" button points there.

## Style preferences

- Active voice and second person ("you"). One idea per sentence. Sentence case for headings.
- Bold for UI elements: **Settings** › **Model**. Code formatting for file names, commands, and paths.
- Write the OS token as `` `$OS` `` (backticks) in prose — Mintlify renders bare `$...$` as LaTeX math. Same for money amounts like `` `$4.99` ``.
- Each feature is documented on exactly ONE page; link to it from elsewhere instead of repeating.
- End feature pages with a `## Related pages` `<CardGroup>`.

## Content boundaries

- **No developer/API docs.** There is no public API — never mention `api.bunnyos.ai`, endpoints, base URLs, or tokens.
- **Don't present "coming soon" features as available**: publishing your own bunnyApp, the `$4.99`/mo Subscribe top-up, chat file uploads, Browser Extension, Database, Schedule. Mention as "coming soon" only where natural.
- **No internal plumbing**: don't name the vendors behind features (web search/extract, image generation, voices), and avoid queues, ledgers, protocols, databases, and environment variables.
- Publish the current economy figures plainly: 10 Carrots per cloud request; a worker earns ~8 (about 80%) of a job; ~50 Carrots/day per 25,000 `$OS` staked; 24-hour unstake cooldown.
