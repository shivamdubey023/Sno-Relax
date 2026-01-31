# System Architecture

This document provides a high-level description of SNO-RELAX system components and interactions.

## Components
- Client UI (React)
- Admin UI (React)
- Backend API (Express)
- Real-time socket server (Socket.IO)
- Database (MongoDB)
- AI services (AI; Python helpers for offline training)

## Interaction Flow
1. User interacts with the Client UI (mood logging, chat, community).
2. Client sends REST requests to the Backend for CRUD operations and file uploads.
3. Real-time features (new messages, group updates) are sent/received via Socket.IO channels.
4. For AI operations (chat, summarization), the server forwards requests to Cohere and returns processed responses to the client.
5. Persistent data is stored in MongoDB; admin and system settings are stored in a settings collection.

## Deployment Notes
- Server and AI integrations can be containerized and deployed independently. The system supports environment-based configuration via `REACT_APP_API_BASE` and server environment variables for API keys and DB URIs.

## Security Notes
- Authentication & authorization handled on the server. Sensitive actions (admin changes, report uploads) require authentication and server-side validation.
- Uploads and report content are handled with privacy-first considerations and should be stored according to institutional privacy guidelines when used in production.