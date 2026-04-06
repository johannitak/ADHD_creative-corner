# Creative Corner ✦

A mobile-first craft activity assistant for people with ADHD. Tell it what materials you have at home and how much time you've got — it suggests creative projects, tracks your supplies, and keeps things simple and encouraging.

Built as a single HTML file with no dependencies. Runs entirely in the browser.

---

## Features

- **AI chat assistant** — conversational, warm, never overwhelming
- **Inventory tracker** — automatically extracts materials from your messages and keeps a running count
- **Activity suggestions** — generates 2–3 step-by-step project ideas based on your time and supplies, with YouTube tutorial links
- **Usage dashboard** — tracks API token usage and estimated cost per session
- **Works as a PWA** — add to your home screen on iOS or Android for a native-app feel

---

## Setup

1. **Get an Anthropic API key** at [console.anthropic.com](https://console.anthropic.com) → API Keys
2. **Open `creative-corner.html`** in any browser (or visit your GitHub Pages URL)
3. **Tap the 🔑 key icon** and paste your API key — it's stored only on your device
4. Start chatting!

---

## Deployment

This is a single static file — no build step, no server needed.

**GitHub Pages:**
1. Fork or clone this repo
2. Go to Settings → Pages → Source: `main` branch, `/ (root)`
3. Your app will be live at `https://yourusername.github.io/your-repo-name/creative-corner.html`

---

## How it works

The app uses **Claude claude-sonnet-4-5** via the Anthropic API directly from the browser. Each message is sent with a system prompt that instructs the model to:

- Extract craft materials mentioned in conversation and return them as structured JSON (`INVENTORY_UPDATE`)
- Generate activity suggestions when the user mentions available time (`ACTIVITIES`)
- Keep replies short, encouraging, and ADHD-friendly

Your API key, inventory, conversation history, and usage stats are all stored in `localStorage` — nothing leaves your device except the API calls to Anthropic.

---

## Cost

Typical usage costs a fraction of a cent per session. The Usage tab shows a running total. Pricing is based on Claude claude-sonnet-4-5 rates ($3 / $15 per million input / output tokens).

---

## Tech

- Vanilla HTML, CSS, JavaScript — no frameworks, no build tools
- [DM Serif Display + DM Sans](https://fonts.google.com/) via Google Fonts
- Anthropic Messages API (`/v1/messages`)
