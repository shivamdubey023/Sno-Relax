# Features

This document lists the core features of SNO-RELAX and short descriptions suitable for academic review.

1. AI Chatbot
   - A conversational AI assistant providing non-dependent guidance and coping strategies. The chatbot integrates with Cohere (external NLP API) and supports both text and limited voice interactions.

2. Mood Tracking
   - Users can log mood entries; the system visualizes mood history with charts and summary cards (weekly/monthly averages). Mood bands are used to adapt UI elements and insights.

3. Community Groups
   - Public and private community groups where users can post and reply. Moderation controls and reporting mechanisms are provided to ensure user safety.

4. Hospital Report Summarization
   - Users can upload medical reports to obtain AI-assisted summaries, making clinical information easier to understand.

5. Admin Panel
   - Moderators and administrators can manage users, content, and system settings (including a server-configured theme fallback).

6. Theme System
   - Global theming with three modes: Brand (application default), Dark, and Light. Implemented using a single ThemeContext which applies CSS variables and persists user preference.

7. Therapist Notes & Messaging
   - Optimistic UI for message send and retry behavior. Messages show immediately and handle background retries for resilience.

8. Games & Engagement
   - Small engagement features (eg. Tic-Tac-Toe) for ancillary interaction and usability testing.

Note: All features are implemented with privacy and accessibility considerations; where AI is used it is explicitly described in the UI to make users aware.