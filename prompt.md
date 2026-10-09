# prompt.md — AI-Assisted Development Log

Project: **What Did I Miss?** (Challenge: "The Unread Problem")
Format: Vibe Coding Hackathon
Last updated: 2026-10-09 (before any application code was written)

> This file records the real AI-assisted development process. Entries are added only for interactions that actually happened. Nothing here is invented, and no secrets (API keys, passwords) are stored.

---

## 1. Project Overview

**Problem:** People return to long, unread chat conversations and miss what matters: deadlines, tasks assigned to them, decisions, and direct mentions. Existing AI summarizers usually upload private conversations to the cloud.

**Solution:** A simple micro-app where the user pastes or uploads a chat export and instantly sees what they missed, with everything processed locally on their device.

**Key features (MVP, planned):**
- Paste or upload a chat export (WhatsApp .txt) and enter "your name"
- Short summary of the missed conversation
- Highlighted mentions of the user, deadlines, decisions, and action items
- Priority ranking (High / Medium / Low) based on urgency and relevance
- Clear "100% local: nothing leaves this device" indicator

**Constraints:** Solo developer, 2 hours total, local-first (no conversation data leaves the device).

---

## 2. Tech Stack & Architecture

**Planned stack (not yet built):**
- UI: React + Tailwind (initial UI generation planned with v0)
- Code generation/editing: Antigravity (planned), Claude (planning and assistance)
- Hosting: Vercel, static site with no backend
- Storage: browser only, no database, no server

**Planned architecture (all in the browser):**

```
Chat text -> Parser -> Signal detector -> Priority scorer -> Summary builder -> Results UI
```

| Module | Responsibility |
|---|---|
| Parser | Convert WhatsApp-style text into {sender, time, text} messages |
| Signal detector | Rule-based detection of mentions, deadlines, questions/requests, decisions, action verbs |
| Priority scorer | Explainable point score mapped to High / Medium / Low |
| Summary builder | Template-based summary from counts and top-scored items |
| Results UI | Summary card plus sections for mentions, deadlines, decisions, action items |

**Design decision:** Rule-based processing first, because it is fast, fully local, and reliable within a 2-hour limit. A local in-browser model is a stretch goal only, if time remains.

---

## 3. AI Code Generation

_No application code has been generated yet. Entries will be added here as they happen._

---

## 4. Debugging

_No errors encountered yet._

---

## 5. AI Features & Design

_No AI-driven design or UI generation has been executed yet._

---

## 6. Testing & Improvements

_No testing has been done yet._

---

## 7. Final Summary

_To be completed at the end of the hackathon (AI tools used, major contributions, completed features)._

---

## Interaction Log

### Entry 1: Planning and problem analysis
- **Date:** 2026-10-09
- **AI tool/model:** Claude (claude.ai chat)
- **Prompt / instruction:** Developer shared the challenge statement ("The Unread Problem - What Did I Miss?": summarize unread chats, identify important messages/decisions/action items, prioritize by urgency and relevance, highlight mentions/deadlines/tasks, and use local-first processing so data never leaves the device), then stated: working solo with 2 hours to build.
- **Purpose:** Understand the problem, choose an MVP, decide architecture, and create a time-boxed build plan.
- **Files/components affected:** None (planning only).
- **Outcome:** Decided on a browser-only, rule-based MVP with a 5-step build order (UI shell, parser, detector and scoring, results display, test and deploy). A cloud AI API and Supabase were ruled out for chat data because of the local-first requirement.
- **Verification status:** Planning only; nothing to verify yet.

### Entry 2: Hackathon master prompt received
- **Date:** 2026-10-09
- **AI tool/model:** Claude (claude.ai chat)
- **Prompt / instruction:** Developer provided the hackathon's master prompt (understand and plan, create prompt.md before coding, keep it updated, wait for confirmation before generating application code).
- **Purpose:** Align the workflow with the hackathon rules.
- **Files/components affected:** `prompt.md` (created).
- **Outcome:** This file was created before any application code. A UI-generation prompt for v0 was drafted in chat but has **not been run yet** and is on hold until the developer confirms.
- **Verification status:** Pending developer review of this file.
