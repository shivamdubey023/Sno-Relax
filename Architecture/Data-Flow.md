3. Server validates the request (authentication, data format).
4. Mood entry is persisted in the database (MongoDB).
5. Server emits a real-time Socket event to notify active client sessions.
6. Client updates the UI optimistically and reconciles with the server response if needed.

**Key Characteristics:**
- Optimistic UI updates
- Real-time synchronization
- Safe retry handling

---

## 2. Chatbot Interaction Flow

**Purpose:**  
To provide AI-assisted, non-clinical conversational guidance.

**Flow:**
1. User sends a message via the Client chatbot interface.
2. Client sends the message to the Server AI endpoint.
3. Server forwards the input to the AI service (e.g., Cohere API or local model).
4. AI service returns a generated response.
5. Server optionally enriches the response (context, summaries, safeguards).
6. Server sends the final response back to the Client.
7. Client renders the message and optionally stores chat history.

**Key Characteristics:**
- AI used strictly as a guidance layer
- No medical diagnosis or automated decision-making
- Stateless or minimally stateful processing

---

## 3. Community Posting Flow

**Purpose:**  
To enable user participation in community discussions.

**Flow:**
1. User creates a community post in the Client.
2. Client sends post data to the Server.
3. Server validates and stores the post.
4. Server emits a Socket event to subscribed community members.
5. Connected clients receive the update and refresh content as needed.

**Key Characteristics:**
- Real-time broadcast updates
- Scalable publish–subscribe model
- Server-side validation for content integrity

---

## 4. Health Report Summarization Flow

**Purpose:**  
To summarize uploaded health reports using AI assistance.

**Flow:**
1. User uploads a report file from the Client.
2. Client securely uploads the file to the Server.
3. Server sanitizes and processes the uploaded data.
4. Relevant content is forwarded to an AI summarization service.
5. AI returns a summarized output.
6. Server stores the summary (only with user consent).
7. Client receives and displays the summarized report.

**Key Characteristics:**
- Secure file handling
- Explicit user consent
- AI used for summarization only

---

## Data Integrity & Reliability

- Optimistic UI patterns are used where appropriate (e.g., mood logging, messaging).
- Retry mechanisms handle transient failures.
- Server-side mutations are designed to be **idempotent** where feasible.
- Real-time updates are reconciled with authoritative server state.

---

## Academic Considerations

- All data flows are designed for **explainability** and **predictability**.
- AI components are clearly isolated from core system logic.
- The architecture avoids opaque or autonomous decision-making.
- Each flow can be independently evaluated and reproduced.

---

This data flow design supports scalability, reliability, and ethical AI usage, aligning with the academic objectives of the **SNO-RELAX Final Year Project**.
