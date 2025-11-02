# Governance Model for Federated Defense Reference

_Last updated: November 2025_

---

## 1. Purpose and Principles

The **Federated Defense Reference** project aims to define an **open, quantum-safe communication architecture** that integrates Decentralized Identifiers (DID), Post-Quantum Cryptography (PQC), and Federated AI Defense.  
Our governance model ensures that this project remains:

- **Open** — Transparent in process, discussion, and decision-making  
- **Collaborative** — Welcoming contributions from diverse communities  
- **Stable** — Maintained through consistent review and versioning practices  
- **Ethical** — Respectful of privacy, security, and human rights  

This model is inspired by the governance principles of the **Apache Software Foundation**, **Linux Foundation**, and **W3C**.

---

## 2. Organizational Structure

The project operates through three main roles:

| Role             | Description                                                  |
| ---------------- | ------------------------------------------------------------ |
| **Maintainers**  | Core contributors with write access who guide technical direction, approve pull requests, and manage releases. |
| **Contributors** | Anyone submitting code, documentation, or discussion contributions via GitHub. |
| **Advisors**     | External experts providing feedback on technical, ethical, or security aspects, without direct commit rights. |

---

## 3. Decision-Making Process

### 3.1 Consensus Seeking
- All major changes (architecture, cryptographic design, protocol changes, AI defense models) will be proposed via a **Request for Discussion (RFD)** in GitHub Discussions or Issues.
- The project aims for **lazy consensus** — if no objections are raised within 5 working days, the proposal is considered accepted.

### 3.2 Voting (if consensus fails)
If consensus cannot be reached:
- Maintainers will call for a vote.
- Each maintainer has one vote.
- A simple majority decides the outcome.
- The results and rationale will be documented publicly in the repository.

---

## 4. Maintainers

### 4.1 Responsibilities
Maintainers are responsible for:
- Reviewing and merging pull requests
- Ensuring security and quality of the codebase
- Managing releases and versioning
- Coordinating community discussions
- Enforcing the [Code of Conduct](./CODE_OF_CONDUCT.md)

### 4.2 Appointment and Removal
- New maintainers are nominated and approved by existing maintainers.
- Inactive maintainers (no activity for 6 months) may be transitioned to “Emeritus” status.
- Maintainers may be removed for repeated violations of the Code of Conduct or governance rules.

### 4.3 Current Maintainers
*(Example — replace with actual names or organization handles when finalized)*

| Name             | Affiliation | GitHub ID     | Role                      |
| ---------------- | ----------- | ------------- | ------------------------- |
| **Michiru Aoki** | Forest Inc. | `@michiruler` | Lead Maintainer / Founder |
| TBD              | —           | —             | —                         |

---

## 5. Release Management

- Releases follow **semantic versioning (SemVer)**: `MAJOR.MINOR.PATCH`
- Major versions correspond to breaking protocol or API changes.
- Minor versions add new features in a backward-compatible way.
- Patch versions include bug fixes or documentation updates.

Release artifacts include:
- Source code (tagged in Git)
- Release notes (in `/docs/releases/`)
- Optional container images or SDK packages

---

## 6. Working Groups (Optional)

As the project grows, specific working groups may be formed to focus on particular domains:

| Working Group           | Focus Area                                            |
| ----------------------- | ----------------------------------------------------- |
| **Core Protocol WG**    | DID, PQC, and routing layer specifications            |
| **Federated AI WG**     | Local anomaly detection and federated SOC integration |
| **Interoperability WG** | MCP connectors and external integrations              |
| **Research WG**         | Whitepapers, academic validation, and citations       |

Each group operates semi-autonomously but reports to the Maintainers collectively.

---

## 7. Community Governance

### 7.1 Meetings and Communication
- Community discussions are held openly via GitHub Discussions and Issues.  
- Optional community calls (e.g., via Matrix/Zoom) may be scheduled for major updates.
- Meeting minutes and decisions will be published in `/community/meetings/`.

### 7.2 Transparency
All project governance documents (this file, Code of Conduct, Contributing Guidelines) are public and version-controlled within the repository.

### 7.3 Language Policy
The project uses **English** for official documentation and discussions, with optional **Japanese translations** for reference.

---

## 8. Intellectual Property and Licensing

- All code contributions are licensed under the **Apache License 2.0**.  
- Contributors agree to the terms defined in the [CONTRIBUTING.md](./CONTRIBUTING.md).  
- Any patents or technical proposals contributed must be made available under royalty-free, open terms compatible with Apache 2.0.

---

## 9. Amendments

This Governance document may be amended through the same consensus process described in Section 3.  
All revisions will be logged and versioned in Git history with timestamps.

---

## 10. Contact

- **Project Lead:** Michiru Aoki (`@michiruler`)  
- **Security Contact:** security@federateddefense.org *(placeholder)*  
- **Community Email:** community@federateddefense.org *(placeholder)*  

---

### Attribution

This governance model is adapted and synthesized from:
- The [Apache Software Foundation Governance Model](https://www.apache.org/foundation/governance/)
- The [W3C Process Document](https://www.w3.org/Consortium/Process/)
- The [Linux Foundation Open Governance](https://www.linuxfoundation.org/)