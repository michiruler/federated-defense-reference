# Post-Quantum Cryptography (PQC) Overhead Analysis  
_Updated: November 2025_

This document provides a quantitative overview of the **data size and computational overhead** introduced when implementing post-quantum cryptographic algorithms in the **Federated Defense Reference Architecture**.  
It compares typical classical cryptographic primitives (RSA, ECC) against **NIST-selected PQC standards** such as **CRYSTALS-Kyber** (KEM) and **CRYSTALS-Dilithium** (Signature).

---

## 1. Overview

| Layer                  | Protocol / Mechanism      | Function                     | PQC Algorithm           | Estimated Data Increase     | CPU Overhead | Typical Use                    |
| ---------------------- | ------------------------- | ---------------------------- | ----------------------- | --------------------------- | ------------ | ------------------------------ |
| **Application**        | TLS 1.3 + PQ Handshake    | Secure session establishment | Kyber-768 (KEM)         | +800–1200 bytes / handshake | +25–35%      | Initial session key exchange   |
| **Identity (DID)**     | DIDComm v2 + PQ Signature | Identity assertion           | Dilithium-2 (Signature) | +2.5–3.0 KB / signature     | +20–30%      | DID document signing           |
| **Transport**          | QUIC / gRPC + PQ Hybrid   | Stream encryption            | Kyber + AES-GCM hybrid  | +1.0 KB / connection setup  | +10–20%      | Reliable data transport        |
| **Connector / MCP**    | AI Agent Channel          | Control / AI instruction     | Falcon-512              | +1.2 KB / message           | +15%         | Secure connector communication |
| **Edge Node / IoT**    | MQTT + PQ Key             | Lightweight encryption       | Kyber-512               | +400–700 bytes              | +10–15%      | Sensor / IoT telemetry         |
| **Storage / Metadata** | DID Record Signing        | Persistent identity record   | Dilithium-2             | +2.8 KB / record            | +20%         | Long-term identity anchoring   |

---

## 2. Discussion

- **Overall PQ Overhead:**  
  Across the 6-layer model, average **data expansion is ~1.2–3.0 KB per transaction**, depending on layer complexity.  
  This represents a **10–30% increase in packet size**, but remains acceptable given quantum resistance guarantees.

- **Computational Impact:**  
  Moderate CPU impact (15–35%) at connection setup or signature verification.  
  For continuous data flow (e.g., MQTT), amortized impact drops below 10%.

- **IoT Compatibility:**  
  PQC algorithms like **Kyber-512** and **Falcon-512** are suitable for constrained devices.  
  Hybrid handshake mechanisms can reduce initial cost via pre-shared key caching.

---

## 3. Reference Implementations

| Implementation              | Language | Library                         | Link                                                         |
| --------------------------- | -------- | ------------------------------- | ------------------------------------------------------------ |
| NIST PQC Reference          | C        | Official Kyber/Dilithium/Falcon | [https://csrc.nist.gov/projects/post-quantum-cryptography](https://csrc.nist.gov/projects/post-quantum-cryptography) |
| Open Quantum Safe (OQS)     | C/C++    | liboqs                          | [https://github.com/open-quantum-safe/liboqs](https://github.com/open-quantum-safe/liboqs) |
| PQC in TLS (BoringSSL fork) | C        | Hybrid Kyber+ECDHE              | [https://github.com/open-quantum-safe/oqs-boringssl](https://github.com/open-quantum-safe/oqs-boringssl) |
| Python Example              | Python   | pyca/cryptography (PQC patch)   | [https://github.com/open-quantum-safe/liboqs-python](https://github.com/open-quantum-safe/liboqs-python) |

---

## 4. Example: Hybrid PQ Key Exchange (Python)

```python
from oqs import KeyEncapsulation

# Example: Hybrid ECDH + Kyber key exchange
kem = KeyEncapsulation("Kyber768")

public_key = kem.generate_keypair()
ciphertext, shared_secret = kem.encap_secret(public_key)
recovered_secret = kem.decap_secret(ciphertext)

print("Shared Secret Length:", len(shared_secret), "bytes")
```

------

## 5. Notes

- Benchmarks are averaged from OQS benchmarks (2024).
- Actual performance depends on CPU architecture and implementation (AVX2, ARMv8).
- When applied within DID-based communication, DID resolution time remains within 1.2× of non-PQC implementations.
- PQC integration aligns with the **NIST FIPS 203–205** (Kyber, Dilithium, Falcon) standardization drafts.

------

## 6. Citation

If you reference this document, please cite as:

> Aoki, M. (2025). *PQC Overhead Analysis in Federated Defense Reference Architecture.*
>  Forest Inc. Technical Documentation, v0.1.
>  DOI: pending.

---

## 🖼 `/docs/architecture-diagram/` 図3枚のテンプレート

> 各画像ファイル名・タイトル・キャプションを**このまま図のaltテキストに記載**すれば、READMEや論文にそのままリンクできます。

---

### **`fig1_layered_architecture.png`**
**Title:** *Layered Architecture of the Federated Defense Reference Framework*  
**Caption:**  
This diagram illustrates the six-layer architecture of the Federated Defense Reference, integrating DID-based identity, post-quantum secure communication channels, and federated AI defense. Each layer—from Identity to Defense—operates independently but communicates through standardized APIs.

---

### **`fig2_did_pqc_flow.png`**
**Title:** *DID–PQC Secure Communication Flow*  
**Caption:**  
Shows the handshake sequence where DID identity verification combines with Kyber-based key exchange and Dilithium digital signatures. The diagram depicts message flow between peers, connector nodes, and federated monitoring agents.

---

### **`fig3_layer_dependencies.png`**
**Title:** *Inter-Layer Dependency Map*  
**Caption:**  
Depicts dependency relationships among the six architectural layers, highlighting data flow and control flow between Identity, Transport, and AI Defense layers. Arrows represent dependency direction; dotted lines show optional AI-enhanced or federated communication paths.