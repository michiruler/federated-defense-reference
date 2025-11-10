# Federated Defense Architecture — DID + PQ Communication Reference

> **Flux–Echo Framework:** From message to meaning — secure communication beyond email and chat.

## 🌐 Overview
The **Federated Defense Architecture** is a research-driven framework exploring how **decentralized identifiers (DID)** and **post-quantum cryptography (PQC)** can enable secure, interoperable, and autonomous communication systems.

It aims to replace traditional, centralized communication models (e.g., email and chat) with a **trust-minimized, verifiable, and privacy-preserving messaging layer** that operates across domains and organizations.

This project is part of the broader **EchoFlux Initiative**, which envisions a future where secure interaction and identity verification occur seamlessly within a federated network of trust.

---

## 🧩 Core Components

### 1. DID Layer
Implements decentralized identity primitives:
- W3C-compliant **Decentralized Identifiers (DID)**
- Verifiable Credential (VC) compatibility
- Integration with emerging identity frameworks (e.g., OpenID4VC, EUDI Wallet)

### 2. PQ Communication Layer
Provides a **quantum-resistant communication protocol** stack:
- KEM: Kyber512 (→ 768 for high-assurance profiles)
- Signature: Dilithium2 (→ Falcon for compact use cases)
- AEAD: AES-GCM-SIV / ChaCha20-Poly1305
- Optional hybrid key exchange (X25519 + Kyber)

### 3. Federated Defense Layer
Adds **cross-domain verification, routing, and defensive intelligence**:
- Trust federation registry (verifiable membership)
- Policy-driven encryption routing
- Adaptive risk scoring and revocation handling

---

## 🔐 Authentication Policy

### Current Implementation
The current prototype employs an **ephemeral post-quantum key exchange** (Kyber-based) for every session.  
Authentication bootstrap relies on **WebAuthn / Passkey**, enabling users to verify their identity through existing platform authenticators.  
No persistent secret keys are stored locally; all PQC key pairs are generated in-memory and destroyed when the session ends.

This approach minimizes attack surface and avoids the complexity of long-term key management while maintaining compatibility with current device ecosystems.

### Design Principle
- **No invention in authentication** — this project focuses on secure distributed communication and federation, not on designing new login schemes.  
- **Use open standards** to stay interoperable with existing systems and future identity frameworks.  
- **Keep identity modular** — authentication can be replaced or upgraded without altering the core protocol.

### Future Direction
As global standards evolve, the project plans to migrate toward **wallet-based and decentralized identity (DID + Verifiable Credential)** models.  
Potential future integrations include:
- **OpenWallet Foundation** standards and **EU Digital Identity Wallet (EUDI)** initiatives.  
- **OpenID4VC / SIOPv2** for DID-anchored authentication and selective disclosure.  
- **Privacy-preserving, zero-knowledge-based identity proofs** for advanced use cases.

These emerging systems promise higher UX, privacy, and security cohesion than current passwordless approaches.

### Summary
| Aspect          | Current (Prototype)                 | Future (Optional Integration)  |
| --------------- | ----------------------------------- | ------------------------------ |
| Key Handling    | Ephemeral PQC (Kyber512, in-memory) | Device-secure or wallet-sealed |
| Identity Proof  | WebAuthn / Passkey                  | DID + VC / OpenWallet          |
| UX Level        | Stable but limited                  | Unified, privacy-preserving    |
| Role in Project | Supporting mechanism                | Replaceable module             |

> Authentication is a **supporting module**, not the core differentiator.  
> The project’s focus remains on **post-quantum secure communication**, **federated trust**, and **adaptive defense architecture**.

---

## ⚙️ Repository Structure

```
federated-defense-reference/
│── README.md
│── README_JP.md
│── docs/
│   ├── research-note_v0.1.md (planned)
│   ├── architecture-overview.md
│   └── key-management-policy_v0.1.md
│── poc/
│   └── README.md (PoC placeholder)
│── assets/
│   └── README.md (image/document placeholders)
```

---

## 📘 Architecture Overview

See [`docs/architecture-overview.md`](docs/architecture-overview.md)  
for detailed explanation and supporting diagrams located in  
[`docs/architecture-diagrams/`](docs/architecture-diagrams/):

- `architecture-overview-diagrams.mmd` — Layered Architecture Overview  
- `communication-flow-diagrams.mmd` — DID + PQ Communication Flow  
- `layer-dependencies-diagrams.mmd` — Layer Interdependencies and Trust Logic

---

## 🧠 Research Focus (v0.1)

| Area             | Description                                                  |
| ---------------- | ------------------------------------------------------------ |
| PQC Integration  | Hybrid KEM/DEM construction using ML-KEM and AEAD (AES-GCM-SIV / Ascon) |
| DID Federation   | Verifiable routing + reputation via decentralized identity registry |
| Adaptive Defense | Policy framework for autonomous mitigation and trust updates |
| UX Exploration   | “EchoFlux” interface for proactive, human-centered communication |

---

## 📈 Roadmap (2025–2026)

| Phase                     | Focus                                           | Output                           |
| ------------------------- | ----------------------------------------------- | -------------------------------- |
| **Phase I (Q1–Q2 2025)**  | PQC–DID hybrid PoC, secure channel prototype    | `poc/` scripts and research note |
| **Phase II (Q3–Q4 2025)** | Federated routing + defense policy integration  | architecture + flow diagram      |
| **Phase III (2026)**      | Multi-party interoperability and open prototype | reference implementation         |

---

## 📚 References
- NIST FIPS 203 / 204 / 205 — ML-KEM, ML-DSA, SLH-DSA  
- W3C Decentralized Identifiers (DID) v1.0  
- OpenID4VC & SIOPv2 Specifications  
- OpenWallet Foundation / EU Digital Identity Wallet (EUDI)  
- IETF MLS / OPAQUE / HPKE / PQC hybrid drafts  

---

## 🪶 Author & Contact
**EchoFlux Initiative**  
Project Maintainer: [Michiru Aoki](mailto:fluxecho@tealforest.io)  
Organization: [Teal Forest](https://tealforest.io)  
Email: [fluxecho@tealforest.io](mailto:fluxecho@tealforest.io)

---

> “Beyond encrypted messages — toward verifiable trust.”  
> — *EchoFlux Manifesto*
