# VibeSafe

**Safety guardrails for AI-assisted coding when the user is non-technical.**

VibeSafe guides the AI to use secure defaults, avoid secret leakage, and explain decisions in simple language. It works with any programming language and framework.

## Why this exists

Non-technical builders ship fast with AI help—but they often don’t know what a secret is, why API keys must stay server-side, or why hardcoding backend values is risky. They ship, and they leak.

**Before (unsafe):**  
The AI might put a secret key in client code so “the app can call the API.” Anyone can open the app and copy the key.

**After (with VibeSafe):**  
The AI stores the key in an environment variable, creates a server-side route that uses it, and has the client call that route. The key never reaches the browser. The AI explains in plain language: “We keep this key on the server. If it were in the client, anyone could see and use it.”

VibeSafe doesn’t block the AI—it **corrects** unsafe patterns and explains why in simple English.

---

## Install

**Download → drag → done.** No terminal, no folders, no setup.

1. Download **[vibesafe.skill.md](vibesafe.skill.md)** from this repo.
2. Add it to your environment in one of these ways:
   - **Cursor:** Drag `vibesafe.skill.md` into `.cursor/skills/` (project) or `~/.cursor/skills/` (user), or paste its contents into your Cursor rules/settings where custom instructions are supported.
   - **v0 / Lovable / Replit:** Paste the contents of `vibesafe.skill.md` into the custom instructions, system prompt, or “AI instructions” field.
   - **ChatGPT / other:** Paste the contents into the system prompt or equivalent.

One file = portable safety. Use it everywhere you vibe code.

**Landing page:** This repo includes a static landing page (`index.html` + `style.css`) for GitHub Pages. In the repo go to **Settings → Pages → Source:** deploy from branch **main**, folder **/ (root)**. The site will be at `https://<username>.github.io/vibesafe/` and the download link will serve `vibesafe.skill.md`.

---

## What’s in the file

| Section | Purpose |
|--------|--------|
| **1. Core Behavior** | Assume non-technical user; safe defaults; correct don’t refuse; explain simply; think ahead before integrating APIs/DB/auth/payments. |
| **2. Secrets** | No hardcoded keys; env vars; template (e.g. `.env.example`); backend proxy for client; placeholder keys only in examples/docs. |
| **3. Frontend–Backend** | No credentials or admin SDKs in client; sensitive logic on server; client calls your backend only. |
| **4. Validation** | Basic input validation, sanitization, safe error handling, no internal details to client. |
| **5. Final Safety Check** | Before responding: secrets exposed? privileged logic in client? env vars? input validated? safe errors? Refactor if not. |

---

## Philosophy

- **Secure by default** – Prefer safe patterns without the user having to ask.
- **Replace, don’t refuse** – Fix unsafe code and explain; avoid blunt “This is insecure. Refused.”
- **Simple language** – Explain what you did and why, without jargon or shame.
- **Language-agnostic** – Rules are conceptual; the AI applies them in the user’s stack (any language or framework).

---

## Future possibilities

The core is free and MIT for distribution. Long-term, VibeSafe could grow into: a hosted version, browser or VS Code extension, a “Built with VibeSafe” certification badge, or a SaaS that audits AI-generated repos. This can grow bigger than a markdown file.

---

## License

MIT
