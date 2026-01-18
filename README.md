# devAssist — Build a Cursor AI Alternative

This repository accompanies a comprehensive **YouTube tutorial series** where we build a **fully‑featured cloud IDE** inspired by Cursor AI.

[![Watch the Tutorial](https://img.shields.io/badge/YouTube-Watch%20Tutorial-red?style=for-the-badge\&logo=youtube)](https://youtu.be/Xf9rHPNBMyQ)

> **Note**
> This repository contains **Part 1 of 2** of the tutorial series. The codebase is functional but incomplete. **Part 2** will introduce the AI Agent, WebContainer preview, and GitHub integration.

---

## 🚀 What We’re Building

devAssist is a browser‑based IDE inspired by Cursor AI, featuring:

* Real‑time collaborative code editing
* AI‑powered code suggestions and quick edits (Cmd + K)
* Conversation‑based AI assistant
* In‑browser code execution with WebContainer
* GitHub import/export integration
* Multi‑file project management

---

## 🧱 Tech Stack

| Category      | Technologies                                     |
| ------------- | ------------------------------------------------ |
| **Frontend**  | Next.js 16, React 19, TypeScript, Tailwind CSS 4 |
| **Editor**    | CodeMirror 6, Custom Extensions, One Dark Theme  |
| **Backend**   | Convex (Real‑time DB), Inngest (Background Jobs) |
| **AI**        | Claude Sonnet 4 (preferred) or Gemini 2.0 Flash  |
| **Auth**      | Clerk (GitHub OAuth supported)                   |
| **Execution** | WebContainer API, xterm.js                       |
| **UI**        | shadcn/ui, Radix UI                              |

---

## 📘 Tutorial Overview

### Part 1 — Chapters 1–12 (This Repository)

#### Phase 1: Foundation & Sponsor Technologies

* **Chapter 1:** Project setup, UI library & theming
* **Chapter 2:** Clerk authentication & protected routes
* **Chapter 3:** Convex database & real‑time sync
* **Chapter 4:** Inngest — background jobs & async UI
* **Chapter 5:** Firecrawl — teaching AI with live documentation
* **Chapter 6:** Sentry — error tracking & LLM monitoring
* **Chapter 7:** Projects dashboard & landing page

#### Phase 2: File System & Editor

* **Chapter 8:** IDE layout & resizable panes
* **Chapter 9:** File explorer (full implementation)
* **Chapter 10:** Code editor & state management

#### Phase 3: AI Features (Partial)

* **Chapter 11:** AI suggestions & quick edit (Cmd + K)
* **Chapter 12:** Conversation system

---

### Part 2 — Chapters 13–16 (Coming Soon)

* **Chapter 13:** AI Agent & tooling (AgentKit, file tools)
* **Chapter 14:** WebContainer, terminal & live preview
* **Chapter 15:** GitHub import & export
* **Chapter 16:** AI project creation & final polish

---

## ⚙️ Getting Started

### Prerequisites

* Node.js **20.09+**
* npm or pnpm
* Accounts:

  * [Clerk](https://cwa.run/clerk) — Authentication
  * [Convex](https://cwa.run/convex) — Real‑time database
  * [Inngest](https://cwa.run/inngest) — Background jobs
  * [Anthropic](https://anthropic.com) **or** [Google AI Studio](https://aistudio.google.com)
  * [Firecrawl](https://cwa.run/firecrawl) *(optional)*
  * [Sentry](https://cwa.run/sentry) *(optional)*

---

### Installation

1. **Clone the repository**

   ```bash
   git clone https://github.com/ManaswiBidkar/devAssist.git
   cd devAssist
   ```

2. **Install dependencies**

   ```bash
   npm install
   ```

3. **Create environment variables**

   ```bash
   cp .env.example .env.local
   ```

4. **Configure `.env.local`**

   ```env
   # Clerk
   NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=
   CLERK_SECRET_KEY=

   # Convex
   NEXT_PUBLIC_CONVEX_URL=
   CONVEX_DEPLOYMENT=
   devAssist_CONVEX_INTERNAL_KEY=

   # AI Providers (choose one)
   ANTHROPIC_API_KEY=
   GOOGLE_GENERATIVE_AI_API_KEY=

   # Optional
   FIRECRAWL_API_KEY=
   SENTRY_DSN=
   ```

5. **Start Convex**

   ```bash
   npx convex dev
   ```

6. **Start Next.js dev server**

   ```bash
   npm run dev
   ```

7. **Start Inngest dev server**

   ```bash
   npx inngest-cli@latest dev
   ```

8. Open **[http://localhost:3000](http://localhost:3000)**

---

## 🗂 Project Structure

```text
src/
├── app/                    # Next.js App Router
│   ├── api/                # API routes
│   │   ├── messages/
│   │   ├── suggestion/
│   │   └── quick-edit/
│   └── projects/
├── components/
│   ├── ui/
│   └── ai-elements/
├── features/
│   ├── auth/
│   ├── conversations/
│   ├── editor/
│   │   └── extensions/
│   ├── preview/            # Part 2
│   └── projects/
├── inngest/
└── lib/

convex/
├── schema.ts
├── projects.ts
├── files.ts
├── conversations.ts
└── system.ts
```

---

## ✨ Features Implemented (Part 1)

### Editor

* Syntax highlighting (JS, TS, CSS, HTML, JSON, Markdown, Python)
* Line numbers & code folding
* Minimap overview
* Bracket matching & indentation guides
* Multi‑cursor editing

### AI Features

* Real‑time ghost‑text code suggestions
* Quick edit (Cmd + K)
* Selection tooltip actions
* Conversation sidebar with history

### File Management

* File explorer with folder hierarchy
* Create, rename & delete files/folders
* VS Code‑style file icons
* Tab‑based navigation
* Auto‑save with debouncing

### Real‑time

* Convex‑powered instant updates
* Optimistic UI
* Background jobs via Inngest

---

## ⚠️ Current Limitations (Part 1)

Planned for Part 2:

* AI agent file modification
* Message cancellation
* Past conversations dialog
* Code preview & execution
* GitHub integration
* AI project generation

---

## 📜 Scripts

```bash
npm run dev     # Start development server
npm run build   # Build for production
npm run start   # Start production server
npm run lint    # Run ESLint
```

---

## 🤝 Sponsors

Thanks to the sponsors supporting this tutorial:

* **[Clerk](https://cwa.run/clerk)** — Authentication made easy
* **[Convex](https://cwa.run/convex)** — Real‑time database
* **[Inngest](https://cwa.run/inngest)** — Background jobs
* **[Firecrawl](https://cwa.run/firecrawl)** — Web scraping for LLMs
* **[Sentry](https://cwa.run/sentry)** — Error tracking
* **[CodeRabbit](https://cwa.run/coderabbit)** — AI‑powered code reviews

---

## 🙏 Acknowledgments

* [Cursor](https://cursor.sh)
* [Orchids](https://orchids.app)
* [shadcn/ui](https://ui.shadcn.com)
* [CodeMirror](https://codemirror.net)

