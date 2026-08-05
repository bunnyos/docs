# Documentation project instructions

## About this project

- This is the Mintlify documentation site for **bunnyOS**, a small-model AI platform.
- Pages are MDX files with YAML frontmatter. Configuration lives in `docs.json`.
- Run `mint dev` to preview locally; `mint validate` and `mint broken-links` before declaring done.
- The audience is **non-technical end users**: cover what a feature is, why you'd use it, and how to use it. The two allowed technical pages ("Run a worker", "Inference API") stay friendly and high-level.

## What bunnyOS is (post-Telegram pivot, 2026-08)

- The product is **bunny**, a personal AI agent that lives inside **Telegram**. Users chat with the bot **@bunnyagentbot** (`https://t.me/bunnyagentbot`). There is no web app, no sign-in; the Telegram account is the identity.
- bunny chats with long-term **memory**, searches the live web, finds places/restaurants/hotels/flights (3+ picks become shareable list pages), generates **PDF/Word documents**, keeps a **calendar** with reminders and **automations**, reads connected **Gmail** and **Google Calendar**, and works in **group chats**.
- The **Mini App** (opened with `/app` inside Telegram) is the control panel: Carrots balance and usage, memory browser, inbox, calendar, automations, lists, web-search history, **Stake $OS**, **Supply Compute** (worker registration), **Inference API** keys, Network Stats, and Bunny Images.
- Every answer is served by **bunnyCompute** (volunteer machines running small models). Users chat on **usage** first: free usage refills daily, bunny pro adds monthly usage, and both show only as percentages. **Usage is not Carrots** — never call an allowance "Carrots" or a "Carrot allowance" (internally allowances are Carrot-denominated, but never expose that). **Carrots are the credit of the bunnyCompute network**, the unit every answer is priced in and the unit workers and stakers earn. **Never frame Carrots as secondary**: no "backup", "fallback", "last resort", or "cushion", and no "you may rarely/never touch your balance" reassurances (user decision 2026-08-05; Carrots are positioned as valuable). Stating the usage-first spend order as plain fact is fine. The balance is spent once usage runs out, at a flat per-answer price that depends on the model (currently 10 free / 20 pro, NOT publishable). New accounts get a Carrot starter grant (currently 1,000), but **the grant is no longer mentioned in docs at all** (user decision 2026-08-05); the one exception is the **Starter grant** history-entry label on the "Your Carrots and usage" page, which names a real UI label. Spend order: free usage → pro usage → Carrot balance.
- **bunny pro**: `$9`/month via Telegram Stars, a monthly usage allowance plus a better model. Cancel in Telegram settings › My Stars.
- Earn Carrots by **staking `$OS`** on Base (currently 50 Carrots/day per full 25,000 staked, NOT publishable; credited automatically) or **supplying compute** (`npx @bunnyosai/worker@latest --key <key>`; the worker keeps about 80% of what a job pays). Only native workers exist; browser workers were removed.
- The product source of truth is `/Users/joe/Downloads/bunnyos/` (`Bunny-Telegram` = bot + Mini App, `Bunny-API` = the network backend). Verify claims against the code; the repos' own prose (README, replit.md) is partly stale.

## Terminology

- **bunny** (the agent), **bunnyOS** (the platform), **bunnyCompute** (the network), **Carrots** (the credit), **`$OS`** (the staked token), **Mini App** (the in-Telegram control panel), **bunny pro** (the subscription).
- lowercase `bunny`, `bunnyOS`, `bunnyCompute`, `bunny pro` even at sentence start; capitalize Carrots, Telegram, Mini App, Stars.
- The docs "Chat with bunny" button points at `https://t.me/bunnyagentbot`.

## Style preferences

- Active voice and second person ("you"). One idea per sentence. Sentence case for headings. US spelling.
- **Short sentences, at most 1 or 2 commas each** (more only when genuinely listing). Split long sentences instead.
- Plain words over jargon on user pages: "history" not "ledger", "not saved for later" not "queued", no "inference"/"context"/"mirrored" outside the Inference API page. UI labels are quoted as-is even if technical.
- **No em-dashes anywhere** in published pages.
- **No colons inside prose sentences or headings**; rewrite with a comma or split the sentence. Colons are fine in YAML frontmatter and code.
- Bold for exact UI labels and buttons (**Supply Compute**, **Register worker**). Code formatting for commands (`/start`), file names, and flags.
- Write the OS token as `` `$OS` `` (backticks) in prose; Mintlify renders bare `$...$` as LaTeX math. Inside bold labels escape it instead: **Stake \$OS**. Same for money amounts, `` `$9` ``.
- Each feature is documented on exactly ONE page; link to it from elsewhere instead of repeating.
- End feature pages with a `## Related pages` `<CardGroup>`; card titles match the target page's frontmatter title.
- No screenshots for now (user decision, 2026-08-03). Hero art from `/images/hero/` only.

## Content boundaries

- **Never mention** (all removed): the web app, platform.bunnyos.ai, sign-in/Privy, on-device or in-browser inference, local/cloud toggle, MCP servers, tool approvals/permissions, bunnyApps as usable, the app store, Narrator/Yuki, bunny b1, browser workers, keyboard shortcuts, `$4.99` Subscribe, "Settings ›" paths, **@bunnyosbot** (the dev bot; production is @bunnyagentbot).
- **Coming soon** (Mini App "Soon" badges, mention only as such): Complete Tasks, bunnyApps.
- **Do not call connected apps read-only** or say bunny "never writes/sends/edits" (user decision 2026-08-04; editing is planned). Describe what bunny does today (reads mail and events) without promising what it will never do.
- **No internal plumbing**: don't name the vendors behind web search, places, connected apps, or image generation, and avoid brokers, ledgers, schedulers, WebSockets, databases, env vars.
- The Inference API page is the one place API endpoints may appear; base URL `https://api.bunnyos.ai`, models `gemma-4-e4b` and `qwen3.7-flash`.
- **Never publish any specific Carrot amount** (user decision 2026-08-04; more models with different prices are coming). That covers per-answer model prices, the worker payout per job, the staking rate, the starter grant size, the free daily allowance, and the bunny pro monthly allowance. Concepts are fine: flat price per answer, the pro model costs more, workers keep about 80%, bigger stakes earn more daily, a starter grant exists, allowances refill. Also never publish the unstake cooldown duration (the app shows it live).
