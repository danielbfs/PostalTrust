# Project Obsidian Brain

This file is designed for visualization in Obsidian with Mermaid. It shows the main system blocks and how they communicate.

## General Mindmap

```mermaid
mindmap
  root((Postal Trust))
    Vision
      Open source
      Self-hosted
      Federated
      API-first
      AI-native
    Blockchain
      Permissioned network
      Validator nodes
      BFT or PoA consensus
      Immutable ledger
      Smart contracts
    AI
      Document OCR
      Event classification
      Shipment summarization
      Fraud detection
      Operational copilot
      Automatic reports
    Domain
      Shipment
      Custody
      Events
      Documents
      Settlement
      Compliance
    PostalCoin
      RWA Programmable Stamp
      Proof of Infrastructure
      Per-shipment escrow
      Per-leg settlement
      Performance slashing
      Reputation score
      Crowdshipping
      IoT oracles
      Dedicated Layer 2
    Integration
      REST or GraphQL API
      Webhooks
      SDKs
      Federated protocol
      ERP TMS WMS
    Privacy
      GDPR LGPD
      Pseudonymization
      Off-chain data
      On-chain hashes
      Access control
    Applications
      Admin dashboard
      Audit portal
      Operator app
      Transporter app
      AI chat
    Roadmap
      MVP
      Custody
      Financial
      Federation
      Ecosystem
      Future PostalCoin
```

## Block Communication Map

```mermaid
flowchart TD
    A[Shipment Identity] --> B[Event Blockchain]
    A --> C[Custody and Proofs]
    A --> E[Documents and Evidence]

    B --> C
    B --> D[Smart Contracts]
    B --> G[Risk Fraud and Compliance]
    B --> I[Applications]

    C --> D
    C --> G
    C --> I

    E --> B
    E --> G
    E --> I

    D --> F[Finance and Settlement]
    D --> I
    D --> M[PostalCoin]

    F --> I
    F --> G
    F --> M

    G --> I

    H[API and Open Protocol] --> A
    H --> B
    H --> C
    H --> E
    H --> F
    H --> I

    J[Native AI Layer] --> A
    J --> B
    J --> C
    J --> D
    J --> E
    J --> F
    J --> G
    J --> H
    J --> I
    J --> M

    K[Privacy and GDPR] --> A
    K --> B
    K --> C
    K --> E
    K --> H
    K --> I

    L[Federation Between Instances] --> H
    L --> B
    L --> C
    L --> D
    L --> F
    L --> M

    M --> D
    M --> F
    M --> I
    M --> L
```

## Summarized Operational Flow

```mermaid
sequenceDiagram
    participant U as User or Company
    participant API as API Gateway
    participant ID as Shipment Identity
    participant DOC as Documents
    participant AI as AI Layer
    participant BC as Blockchain
    participant CU as Custody
    participant SC as Smart Contracts
    participant PCN as PostalCoin Escrow
    participant FI as Finance

    U->>API: Create shipment
    API->>ID: Generate digital identity
    U->>DOC: Upload documents
    DOC->>AI: Extract and validate data
    AI-->>DOC: Fields, alerts, and classification
    ID->>BC: Register creation
    U->>PCN: Hold PostalCoin value (escrow)
    API->>CU: Register pickup and custody
    CU->>BC: Register signed event
    PCN-->>CU: Release fraction to pickup operator
    BC->>SC: Execute business rules
    SC->>FI: Update split or guarantee
    AI->>API: Summarize status and detect exceptions
    CU->>BC: Register delivery
    PCN-->>CU: Release final fraction to deliverer
    BC->>SC: Close contractual flow
    SC->>FI: Settle final payment
    PCN->>FI: Escrow zeroed
```

## Quick Block Reference

- `Shipment Identity`: creates the digital asset and readable physical identifier.
- `Event Blockchain`: stores the immutable main trail.
- `Custody and Proofs`: records responsibility at each stage.
- `Smart Contracts`: executes business rules and automation.
- `Documents and Evidence`: stores off-chain attachments and on-chain hashes.
- `Finance and Settlement`: manages splits, escrow, and payments.
- `Risk, Fraud and Compliance`: monitors integrity and policies.
- `API and Open Protocol`: connects internal systems and other instances.
- `Native AI Layer`: supports all blocks with reading, analysis, and automation.
- `Privacy and GDPR`: ensures minimization, pseudonymization, and access control.
- `Federation Between Instances`: enables interoperability between companies.
- `PostalCoin`: programmable economic layer — the Programmable Stamp (RWA). Issuance via Proof of Infrastructure, automatic per-leg settlement, incentivized crowdshipping, performance slashing, and reputation scoring. Future ecosystem evolution.
