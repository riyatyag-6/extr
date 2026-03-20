# extr
'''
flowchart TD
    U([👤 User]):::user

    subgraph Frontend["Frontend — Browser UI"]
        direction TB
        UP[📄 Upload Documents]
        NL[💬 Natural Language Query]
        RV[📋 Results View]
    end

    subgraph API["HumanizeIQ Explorer API"]
        direction LR
        AUTH[Auth Service]
        ING[Document Ingest]
        QE[Query Engine]
    end

    subgraph Store["Knowledgebase"]
        KB[(Document Store)]
        IDX[(Search Index)]
    end

    U --> UP
    U --> NL
    UP -->|"POST /documents"| ING
    NL -->|"POST /query"| QE
    AUTH -.->|"Bearer token"| ING
    AUTH -.->|"Bearer token"| QE
    ING --> KB
    ING --> IDX
    QE --> IDX
    QE --> KB
    QE -->|"Ranked results"| RV
    RV --> U

    classDef user fill:#EEEDFE,stroke:#534AB7,color:#3C3489
    classDef default fill:#F1EFE8,stroke:#888780,color:#444441
    '''
