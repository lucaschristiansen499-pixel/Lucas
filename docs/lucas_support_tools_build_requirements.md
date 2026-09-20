# Academic Support Tools for Lucas — Build Requirements

*Note: this project will be built directly as a private Claude-hosted web app rather than handed to an outside developer — see "Platform decision" below.*

## Context

The student has documented difficulty with note-taking (fine motor / visual-motor), working memory, and executive function (planning, task initiation, breaking down multi-step problems), based on a formal evaluation. He processes verbal, plain-language explanations well but struggles with dense, unstructured text. He is a high school junior. Goal: reduce manual, one-off reformatting work and consolidate several point solutions into a small number of purpose-built tools.

## Platform decision

These tools will be built and hosted as a private, Claude-based web app (a Claude "Artifact") rather than commissioned from an outside developer. This keeps the underlying AI reformatting work inside Claude, gives the student a single bookmarkable link, and avoids introducing a new third-party vendor or account relationship. Component 2 (reminders) remains a configuration task against the school's existing system rather than custom software.

## Component 1 — Lecture Note Processor

Highest-value component; the reformatting approach below has already been validated manually on two real lecture exports.

**Input:** Text export from an AI note-taking/recording device ("AI Pocket"). This may arrive as a cleaned summary (headers, terms, an embedded decision-tree block) or as a raw speech-to-text transcript with timestamps, filler words, and occasional transcription errors.

**Required output structure, every time:**
1. One-line, plain-language TL;DR of the lecture's topic.
2. Key terms/definitions, simplified, one per line.
3. Any taught procedure rewritten as an explicit numbered step list (never paragraphs).
4. Worked examples preserved with the actual numbers, clearly laid out.
5. Edge cases / special rules (e.g. a "no solution" case) called out separately.
6. Homework / action items pulled into a checklist.
7. Off-topic chatter and classroom banter filtered out entirely.
8. Any transcript segment that is unclear or internally inconsistent must be flagged, not guessed — accuracy matters more than completeness.

## Component 2 — Reminders

Mostly a configuration task, not new software.

- The school (Marmion Academy) uses PlusPortals (Rediker Software) as its student information system, which has a built-in Google Calendar Feed export (webcal/ics URL).
- Task: locate/enable that feed in the student or parent PlusPortals account, subscribe to it from Google Calendar ("Other calendars" → "From URL"), and set default reminder notifications on the imported calendar.
- Google's URL-subscribed calendars refresh every several hours, not instantly — also enable push notifications in the free PlusPortals mobile app as a faster backup channel.

## Component 3 — Executive-Function / Task Breakdown Tool

- Function: turn a loose brain-dump into an organized task list, and break one task into concrete, sequential steps (comparable to tools such as Goblin Tools' "Compiler" and "Magic ToDo"), plus a simple time estimator.
- UI requirements: minimal and low-friction; short bullet points; no dense paragraphs; explicit sequential steps, especially for math/spatial tasks.
- Nice-to-have: a shared view so a parent and the student can both see/check off the same task list (lightweight multi-user access, not enterprise auth).
- May reasonably be merged with Component 1 into a single tool covering both "here's my lecture" and "here's my task list."

## Evaluated and rejected: general-purpose AI agents

Broad, account-connected AI assistants (e.g. "Instinct"-style products) were evaluated and rejected as a foundation for this project.

- They connect broadly to email, messaging, screen, audio, and location, and can autonomously take actions/make commitments on the user's behalf.
- Rejected because: (a) too broad a data-access footprint for a student's accounts; (b) autonomous action-taking is a poor fit for someone with documented executive-function/judgment weaknesses — it shifts risk to the user rather than reducing it; (c) new/unproven vendor with capped liability and mandatory arbitration.
- Guidance: avoid any architecture that requires broad, standing account access or autonomous third-party actions. Favor scoped, single-purpose tools — consistent with the "stay in Claude / dedicated site" decision above.

## Open questions

- Does AI Pocket support exporting transcripts to email or a synced folder (Google Drive/Dropbox)? If yes, Component 1 could ingest automatically instead of copy/paste.
- Should Component 3's task list be single-user (student only) or shared (student + parent visibility)?
