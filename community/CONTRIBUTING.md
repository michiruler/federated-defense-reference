# Contributing Guidelines

Thank you for your interest in contributing to **Federated Defense Reference**!

This project aims to build an open, quantum-safe communication framework combining **Decentralized Identity (DID)**, **Post-Quantum Cryptography (PQC)**, and **Federated AI Defense**.  
We welcome contributions from researchers, developers, and security professionals.

---

## 🧭 How to Contribute

### 1. Fork the repository
- Fork this repo to your own GitHub account.
- Clone it locally and create a feature branch.
  ```bash
  git clone https://github.com/<yourname>/federated-defense-reference.git
  cd federated-defense-reference
  git checkout -b feature/<your-feature-name>
  ```

### 2. Implement your changes

- Follow the project’s structure and coding conventions.
- Add comments and documentation where appropriate.
- Keep commits atomic and meaningful.

### 3. Test your code

- Verify your changes do not break existing functionality.
- Add test cases where applicable (e.g., for PoC modules).

### 4. Commit and push

```bash
git add .
git commit -m "Add: short and descriptive message"
git push origin feature/<your-feature-name>
```

### 5. Open a Pull Request

- Submit your PR to the main repository’s `main` branch.
- Describe:
  - Purpose of the change
  - Related issue (if any)
  - Testing or validation steps

------

## 🧩 Contribution Areas

| Category           | Description                                                  |
| ------------------ | ------------------------------------------------------------ |
| Core Protocol      | DID/PQC integration, message routing, and encryption logic   |
| Federated Defense  | Local AI filtering, SOC-level coordination, and detection rules |
| Documentation      | README, research notes, or academic references               |
| PoC & Examples     | Lightweight implementations for IoT, chat, or multi-platform use |
| UI / SDK Templates | Developer tools or visualization interfaces                  |

------

## 🧪 Development Environment

Recommended setup:

- Python ≥ 3.10
- OpenSSL ≥ 3.1 (for PQC KEM testing)
- Node.js ≥ 18 (for frontend or SDK templates)

Optional dependencies:

- `mermaid-cli` — to render `.mmd` diagrams
- `pqcrypto` — for PQC testing
- `didlib` — for decentralized identity simulation

------

## 🧱 Code Style

- Follow [PEP 8](https://peps.python.org/pep-0008/) for Python code.
- Use Conventional Commits for commit messages.
- Keep line width ≤ 100 characters.
- Use English for variable names and comments.

------

## 🔐 Security

If you discover a security issue, **do not open a public issue**.
 Instead, please contact the maintainers privately via:

> security@federateddefense.org (placeholder)

We will coordinate a responsible disclosure.

------

## 🌍 Code of Conduct

All contributors must follow the Code of Conduct.

------

Thank you for helping us make federated, quantum-safe communication a reality!

