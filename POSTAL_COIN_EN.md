# PostalCoin — The Programmable Stamp

## PostalCoin Ecosystem: The Evolution from Stamp to Digital Logistics Asset

### Document status

Version: `0.1-draft`

Date: `2026-05-12`

Suggested license for the document: `CC BY 4.0`

Current status:

- initial conceptual document;
- open to comments, technical critique, and community contributions;
- subject to revisions as the repository and main white paper evolve.

---

## 1. Summary

The PostalCoin project proposes the creation of a **Utility Token** backed by operational logistics capacity. Unlike a common cryptocurrency, PostalCoin functions as a **Real World Asset (RWA)**, where each token represents the right to transport and process cargo, audited and executed via Smart Contracts.

PostalCoin is the conceptual evolution of the postal stamp: from a static, physical proof of payment to a **programmable stamp**, capable of carrying settlement rules, dynamic incentives, automatic penalties, and end-to-end financial traceability.

Within the Postal Trust ecosystem, PostalCoin solves a structural problem: **how to fairly, transparently, and automatically compensate each participant in a multi-operator logistics chain, proportionally to the real effort of each leg**.

> PostalCoin is not a speculative cryptocurrency. It is the operational unit of value for the Postal Trust protocol.

---

## 2. Central Thesis

Traditional logistics operates with manual invoicing, slow settlements, and recurring disputes over costs and responsibility among operators. PostalCoin proposes replacing this model with **real-time financial settlement**, governed by smart contracts and fed by real operational data.

The central thesis is:

> Transform the postal company from a rigid carrier into a **Logistics Mesh Orchestrator**, where every leg, every operator, and every delivery is priced, executed, and settled in a programmable, auditable, and automatic fashion.

This transformation relies on three pillars:

1. **real backing**: tokens issued based on audited logistics capacity, not speculation;
2. **per-leg settlement**: each stage of the chain consumes and releases tokens upon custody confirmation;
3. **smart incentives**: game theory applied to optimize inefficient routes and incentivize last-mile delivery.

---

## 3. Issuance Architecture (Tokenomics)

### 3.1 Proof of Infrastructure

PostalCoin issuance is based on an innovative model called **Proof of Infrastructure**: federated logistics operators issue tokens based on their audited operational capacity.

Unlike Proof of Work (computational effort) or Proof of Stake (locked capital), Proof of Infrastructure anchors issuance to the **real-world capacity to move cargo**.

Issuance criteria:

- audited processing capacity (e.g., kg/day, objects/day);
- proven geographic coverage;
- verified operational infrastructure (hubs, vehicles, teams);
- performance and compliance track record;
- ecosystem reputation score.

> Example: an operator with an audited capacity to process 10,000 kg/day across routes up to 500 km can issue tokens proportional to that capacity.

### 3.2 Algorithmic Issuance

The protocol regulates circulating supply according to the volume of successfully completed deliveries, preventing asset inflation without a corresponding physical counterpart.

Rules:

- issuance is proportional to audited capacity;
- tokens only enter circulation when there is a corresponding operation;
- the protocol adjusts supply based on real demand;
- operators with higher reputation scores may have higher issuance limits;
- operators with recurring slashing have limits automatically reduced.

### 3.3 Who Can Issue

- **Federated operators**: direct issuance, based on their audited infrastructure;
- **Authorized partners**: can mint tokens if authorized by the protocol and the federated operator that accredited them;
- **Unauthorized entities**: cannot issue.

### 3.4 Token Uniqueness

PostalCoin is **a single currency** across the entire Postal Trust ecosystem. There is no per-instance or per-operator currency. All federated instances share the same token, ensuring native financial interoperability.

---

## 4. Operational Mechanics and Automatic Settlement

The system replaces manual invoicing with **real-time financial settlement**, executed by smart contracts.

### 4.1 Complete Cycle

```
Sender purchases PostalCoins
        │
        ▼
Posts object → Smart Contract holds total value (escrow)
        │
        ▼
Pickup confirmed → pickup operator receives their fraction
        │
        ▼
Sorting confirmed → hub receives its fraction
        │
        ▼
Transit confirmed → carrier receives their fraction
        │
        ▼
Last mile confirmed → deliverer receives their fraction
        │
        ▼
Delivery confirmed → escrow zeroed, settlement complete
```

### 4.2 Per-Leg Payment

The postage value is "locked" in a smart contract at the moment the shipment is created. As the object passes through **logistics triggers** (Pickup → Sorting → Hub → Transit → Distribution → Delivery), token fractions are automatically released to the executors of each leg.

Each release is conditioned on **custody confirmation** recorded on the blockchain:

- operator's digital signature;
- event timestamp;
- authorized location;
- associated evidence (when applicable).

### 4.3 Practical Example

Shipment: 5 kg, São Paulo → Rural Minas Gerais

| Leg | Operator | Effort | PostalCoin |
|-----|----------|--------|------------|
| Pickup | Operator A (SP) | Low | 8 PCN |
| Sorting | Hub SP | Low | 5 PCN |
| Transit SP→MG | Carrier B | High | 42 PCN |
| Last mile (rural MG) | Local crowdshipper | High | 30 PCN |
| **Total held in escrow** | | | **85 PCN** |

---

## 5. Oracles and Dynamic Pricing

### 5.1 Price Oracles

Sensors, monitoring systems, and operational data act as **oracles**, informing the smart contract of the real cost so that the token value is dynamically adjusted.

Oracle data sources:

- **IoT and sensors**: GPS, NFC, barcode readers, scales;
- **Fuel cost**: integration with updated price databases;
- **Demand**: shipment volume on the route during the period;
- **Seasonality**: adjustments for peak dates (Black Friday, Christmas, etc.);
- **Operational conditions**: weather, traffic restrictions, strikes.

### 5.2 Effort Formula (proposal)

```
route_effort = (
    distance_weight    × distance_km
  + modal_weight       × modal_factor
  + object_weight      × (weight_kg + volume_m³)
  + complexity_weight  × documentary_factor
  + risk_weight        × risk_score
  + deadline_weight    × urgency_factor
  + demand_weight      × seasonality_factor
)

cost_pcn = route_effort × base_rate_pcn
```

Each operator at each leg receives a proportional fraction of their relative effort within the total route effort.

---

## 6. Market Incentives and Crowdshipping

PostalCoin uses **game theory** to optimize inefficient routes and incentivize operator participation in hard-to-reach regions.

### 6.1 Price Signaling

Low-density logistics legs (e.g., rural Minas Gerais, remote Northern regions) carry a **higher cost in PostalCoins**, creating financial incentive for local micro-operators or crowdshippers to perform last-mile delivery.

The mechanism is simple:

- route with few operators → higher PCN price → attracts new operators;
- route with many operators → price stabilizes → market equilibrium.

### 6.2 Density-Based Delivery

The protocol allows the creation of **differentiated tariffs** for those who opt to wait for cargo consolidation:

- express delivery: full cost;
- economy delivery: sender accepts waiting for consolidation, paying fewer PCN;
- grouped delivery: objects to the same region are consolidated, reducing unit cost.

This model optimizes freight and reduces the carbon footprint.

### 6.3 Crowdshipping

Any person or micro-business can register as a **crowdshipper** in regions where last-mile costs are high. The PostalCoin incentive makes delivery viable in locations where traditional operators do not operate profitably.

---

## 7. PostalCoin Smart Contracts

### 7.1 Main Contracts

| Contract | Function |
|----------|----------|
| **Issuance** | Mint tokens based on the federated operator's audited capacity |
| **Escrow** | Hold the total postage value until the logistics chain is complete |
| **Per-leg release** | Release proportional fraction to the operator who confirmed custody |
| **Penalty (Slashing)** | Debit tokens from the operator who failed on deadline or integrity |
| **Refund** | Return tokens to the sender in case of loss or total failure |
| **SLA Bonus** | Reward operators who exceed deadline and quality targets |
| **Burn** | Remove tokens from circulation in cases defined by governance |

### 7.2 Execution Rules

- token release only occurs after custody confirmation on the blockchain;
- slashing is automatic and does not depend on manual dispute;
- refund can be partial (proportional to the unexecuted leg);
- SLA bonus is funded by a reserved fraction of the escrow;
- all contracts are auditable and deterministic.

---

## 8. Governance and Quality (Slashing)

### 8.1 Performance Slashing

If an operator fails on deadlines or cargo integrity (verified via digital trail and IoT oracles), the protocol executes **automatic slashing**:

- tokens are taken from the failing operator;
- tokens are returned to the sender as an **automatic penalty**;
- the operator's reputation score is reduced;
- recurrence can lead to suspension of issuance capacity.

### 8.2 Reputation Score

The transaction trail on the blockchain creates an **immutable efficiency record** for each distribution center and logistics partner.

Score factors:

- on-time delivery rate;
- cargo integrity rate;
- slashing frequency;
- operational volume;
- response time;
- quality of custody evidence.

The score directly affects:

- token issuance limits;
- route allocation priority;
- visibility in the operator marketplace;
- eligibility for SLA bonuses.

---

## 9. Technical Infrastructure

### 9.1 Dedicated Layer 2 / Subnet

To handle the daily transaction volume of a logistics ecosystem (potentially millions of events per day), the project envisions the use of a **dedicated Layer 2 or Subnet**, ensuring:

- near-zero transaction fees;
- high processing speed;
- compatibility with the main permissioned blockchain;
- financial transaction load isolation.

### 9.2 Integration with the Main Blockchain

The PostalCoin Layer 2 operates in parallel with the Postal Trust main blockchain:

- **main blockchain**: records custody events, proofs, and audits;
- **PostalCoin Layer 2**: processes financial transactions, escrow, releases, and slashing;
- **periodic anchoring**: consolidated financial states are anchored to the main chain for auditability.

---

## 10. Privacy and Compliance

### 10.1 GDPR/LGPD and Financial Data

PostalCoin financial data handling follows the same privacy-by-design principles as Postal Trust:

- individual balances are pseudonymized;
- transactions are recorded with opaque IDs;
- personal data associated with wallets remains off-chain;
- financial reports are accessible only by authorized roles.

### 10.2 On-chain vs Off-chain Data

| On-chain (Layer 2) | Off-chain |
|---------------------|-----------|
| Pseudonymized balances | Holder's personal data |
| Escrow transactions | Sensitive commercial details |
| Per-leg releases | Complete fiscal documents |
| Slashing events | Management reports |
| Issuances and burns | ERP integration data |
| Reputation score | Commercial contracts |

### 10.3 Regulatory Note

> [!WARNING]
> Depending on the jurisdiction, even internal utility tokens may require specific legal analysis. This document describes the conceptual and technical vision for the token. Formal regulatory analysis for each market is a necessary step before implementation and is outside the scope of this document.

---

## 11. Strategic Impact

Implementing PostalCoin transforms the postal company from a **rigid carrier** into a **Logistics Mesh Orchestrator**. This enables:

### 11.1 Fixed Cost Reduction

Remote regions that currently require expensive fixed infrastructure can be served via **automatic partnerships** with crowdshippers and micro-operators incentivized by PostalCoins.

### 11.2 Revenue Anticipation (Logistics Hedge)

Large e-commerce companies can **purchase PostalCoins in advance** at a fixed price, ensuring predictable shipping costs for future operations. This works as a logistics hedge, protecting against transport cost fluctuations.

### 11.3 Absolute Transparency

The physical and financial tracking of each posted object is **unified**: who moved it, when it was moved, how much it cost, and who was paid — all auditable on the same infrastructure.

### 11.4 Capacity Marketplace

The ecosystem can evolve into an **open logistics capacity marketplace**, where operators offer capacity and senders seek the best routes and prices, all settled in PostalCoins.

---

## 12. Risks

### 12.1 Technical Risks

- integration complexity between Layer 2 and main blockchain;
- price and effort oracle calibration;
- transaction volume requiring robust infrastructure;
- escrow and slashing smart contract security.

### 12.2 Operational Risks

- resistance from traditional operators to the slashing model;
- difficulty in capacity auditing for Proof of Infrastructure;
- initial calibration of effort weights per route;
- onboarding crowdshippers in remote regions.

### 12.3 Regulatory Risks

- token classification by regulatory bodies (SEC, central banks);
- jurisdiction-specific compliance requirements;
- tax treatment of PostalCoin transactions;
- relationship with payment means legislation.

### 12.4 Adoption Risks

- need for critical mass of operators for the model to work;
- learning curve for senders and operators;
- competition with traditional invoicing models;
- perception of unnecessary complexity.

---

## 13. PostalCoin Roadmap

PostalCoin is a **future evolution** of the Postal Trust ecosystem, planned for after the consolidation of basic operational functionalities.

### Conceptual Phase (current)

- documentation of the thesis and economic model;
- community review;
- definition of initial effort and issuance parameters.

### Research Phase

- Layer 2 technical feasibility study;
- mathematical modeling of algorithmic issuance;
- crowdshipping scenario simulation;
- regulatory analysis per jurisdiction.

### Prototype Phase

- escrow and per-leg release smart contracts;
- integration with simulated oracles;
- slashing and reputation testing;
- PostalCoin management dashboard.

### Pilot Phase

- operation with real operators on controlled routes;
- dynamic pricing validation;
- effort parameter adjustment;
- sender and operator feedback.

### Production Phase

- complete integration with the Postal Trust ecosystem;
- capacity marketplace;
- crowdshipping at scale;
- decentralized token governance.

---

## 14. Relationship with the Postal Trust Project

PostalCoin does not replace or compete with Postal Trust. It is an **economic layer** that integrates with the existing ecosystem:

- **Postal Trust** provides traceability, custody, auditing, and AI;
- **PostalCoin** provides settlement, incentives, reputation, and network economics.

Together, they form a complete infrastructure for programmable logistics:

> Cryptographic trust + Operational intelligence + Network economics.

---

## Related Documents

- [Postal Trust White Paper](WHITEPAPER_EN.md)
- [Project Blueprint](PROJECT_BLUEPRINT_EN.md)
- [Obsidian Brain](OBSIDIAN_BRAIN_EN.md)
- [Contribution Guide](CONTRIBUTING.md)
- [Versão em português](POSTAL_COIN.md)
