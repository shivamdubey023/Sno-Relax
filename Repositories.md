# Repositories

This document lists the repositories that make up the SNO-RELAX project and describes their purpose and primary contents.

1) sno-relax-client
- Repository: https://github.com/shivamdubey023/sno-relax-client
- Purpose: Main user-facing React application. Implements mood tracking, community groups, the AI chatbot client UI, report upload and summarization interfaces, theme handling, and small engagement features.
- Primary language / frameworks: JavaScript, React, Chart.js, Socket.IO client
- Quick start: `npm install` → `npm start`. Set `REACT_APP_API_BASE` if the server is hosted elsewhere.

2) sno-relax-server
- Repository: https://github.com/shivamdubey023/sno-relax-server
- Purpose: Backend API, including authentication, mood storage, community endpoints, AI integration (Cohere), and real-time Socket.IO functionality. Responsible for file uploads and summarization pipelines.
- Primary language / frameworks: Node.js, Express, MongoDB (Mongoose), Socket.IO
- Quick start: Copy `.env.example` to `.env`, set `MONGO_URI`, `JWT_SECRET`, `a as needed, then `npm install` and `npm start`.

3) sno-relax-admin
- Repository: https://github.com/shivamdubey023/sno-relax-admin
- Purpose: Administrative interface for moderators and administrators to manage users, content, groups, settings (including server theme), and analytics. Supports moderation tools and admin-only workflows.
- Primary language / frameworks: JavaScript, React, Socket.IO client, Admin UI components
- Quick start: `npm install` → `npm start`. Use `REACT_APP_API_BASE` to point to the backend.

---

Contact & Maintainers
- **Shivam Kumar Dubey** — GitHub: https://github.com/shivamdubey023
- **Suryakant Mishra** — Co-creator and contributor

Notes
- Each repository contains its own README with module-specific setup, environment, and deployment instructions. For academic documentation, consult the top-level `SNO-RELAX/` folder and the repository READMEs.
- This document is part of the final year submission and intended for evaluators and maintainers.