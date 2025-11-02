# Proof of Concept (PoC)

This directory contains prototype scripts, experimental tests, and validation code for the **DID + PQC Federated Defense Architecture**.

## Purpose
The goal of these PoC files is to:
- Demonstrate end-to-end feasibility of decentralized, quantum-safe communication.
- Provide minimal, self-contained examples for developers and researchers.
- Serve as a foundation for integration testing and future benchmark automation.

## Guidelines
- Keep scripts simple and well-commented.
- Use only lightweight dependencies (e.g., `cryptography`, `paho-mqtt`, `requests`).
- Do **not** include production credentials or large datasets.
- If a script depends on external data, describe it in comments or add a `.sample` file.

## Example Files
| File                        | Description                                                  |
| --------------------------- | ------------------------------------------------------------ |
| `pq_did_handshake_demo.py`  | Demonstrates DID-based key negotiation using a PQC hybrid approach. |
| `iot_low_bandwidth_test.py` | Tests message integrity and size efficiency under low-bandwidth IoT scenarios. |

---

_This directory is part of the open reference implementation for the Federated Defense Architecture project._