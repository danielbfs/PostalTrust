# Obsidian Brain

This file was designed for visualization in Obsidian using Mermaid. It shows the main system blocks and how they communicate.

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
      Shipment summaries
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
    Integration
      REST or GraphQL API
      Webhooks
      SDKs
      Federated protocol
      ERP TMS WMS
    Privacy
      Data protection
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
      Finance
      Federation
      Ecosystem
```

## Communication Map Between Blocks

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

    F --> I
    F --> G

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

    K[Privacy and Compliance] --> A
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
```

## High-Level Operational Flow

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
    participant FI as Finance

    U->>API: Create shipment
    API->>ID: Generate digital identity
    U->>DOC: Send documents
    DOC->>AI: Extract and validate data
    AI-->>DOC: Fields, alerts, and classification
    ID->>BC: Register creation
    API->>CU: Register pickup and custody
    CU->>BC: Register signed event
    BC->>SC: Execute business rules
    SC->>FI: Update split or guarantee
    AI->>API: Summarize status and detect exceptions
    CU->>BC: Register delivery
    BC->>SC: Close contractual flow
    SC->>FI: Settle final payment
```

## Quick Reading of the Blocks

- `Shipment Identity`: creates the digital asset and physical identifier.
- `Event Blockchain`: stores the main immutable trail.
- `Custody and Proofs`: records responsibility at each stage.
- `Smart Contracts`: executes business rules and automation.
- `Documents and Evidence`: stores off-chain attachments and on-chain hashes.
- `Finance and Settlement`: manages splits, escrow, and payouts.
- `Risk, Fraud, and Compliance`: monitors integrity and policy adherence.
- `API and Open Protocol`: connects internal systems and external instances.
- `Native AI Layer`: supports all blocks with reading, analysis, and automation.
- `Privacy and Compliance`: ensures minimization, pseudonymization, and access control.
- `Federation Between Instances`: enables interoperability between companies.
