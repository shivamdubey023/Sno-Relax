# Modules

SNO-RELAX is organized into logical modules to support maintainability and research extensions.

1. Client (`sno-relax-client`)
   - React-based user interface. Handles user flows: onboarding, mood tracking, community interaction, AI chatbot client, and report uploads.

2. Admin (`sno-relax-admin`)
   - Administrative UI for moderators. Manages users, content, settings, and theme controls. Shows system telemetry and admin-only tools.

3. Server (`sno-relax-server`)
   - Node.js / Express API providing REST endpoints, authentication, and web socket channels (Socket.IO) for real-time features.
   - Integrates with AI endpoints (Cohere) and includes Python utilities for training or data processing when needed.

4. AI & NLP
   - Cohere API for conversational responses and summarization.
   - Offline training scripts (Python) and training data storage for experimental models.

5. Database
   - MongoDB (Mongoose models) storing users, moods, messages, community groups, reports, and settings.

6. Shared Utilities
   - Socket handlers, API services, theme tokens, and common CSS variables used across client and admin.

Each module includes a test and build workflow locally and in CI (where configured). The modular structure supports academic experimentation and controlled feature toggles.