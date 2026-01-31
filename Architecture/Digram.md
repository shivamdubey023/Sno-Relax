flowchart LR
    User([User])
    System[[SNO-RELAX System]]
    AI([AI Service<br/>(Cohere / NLP)])

    User -->|Mood, Chat, Posts, Reports| System
    System -->|Insights, Responses, Summaries| User

    System -->|AI Requests| AI
    AI -->|AI Responses| System
