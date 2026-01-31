# Data Flow

This file documents the primary data flows in SNO-RELAX for academic review and reproducibility.

## Example Flows

### 1) Mood Logging
- User submits mood entry in Client → POST /api/moods/:userId → Server validates and persists entry in MongoDB → Server emits Socket event to update active clients → Client updates UI optimistically and reconciles with server response.

### 2) Chatbot Interaction
- User sends message → Client posts to Server AI endpoint → Server calls Cohere API (or local model) → Server receives AI response, optionally enriches it (summaries, suggestions), and returns to Client → Client displays message, logs history as needed.

### 3) Community Posting
- User creates post → Client → Server persists post and notifies group subscribers via Socket → Subscribers receive broadcast update and fetch new content when necessary.

### 4) Report Summarization
- User uploads report (file) → Client uploads to Server (securely) → Server processes (sanitizes, forwards content to AI summarization service) → Server stores summaries (with user consent) and returns results to Client.

## Integrity & Reliability
- Optimistic UI patterns are used where appropriate (e.g., messages, mood logging) with retry logic on failure.
- All server-side mutations are idempotent where feasible to ensure safe retries and predictable state.

These flows are designed for clarity, reproducibility, and explainability for academic reviewers.