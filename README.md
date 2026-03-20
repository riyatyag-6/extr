# High Level Diagram for Document-Chat
```mermaid
graph TD
    UI[User Interface]
    Auth{Authentication}
    API[Explorer API]
    KB[(Knowledge Base)]

    %% Connections
    UI --> Auth
    Auth --> API
    API -- Request --> KB
    KB -- Response --> API
    API -- Result --> UI
```

