# Assets Directory

This folder stores static resources used in documentation, diagrams, and UI prototypes for the **Federated Defense Reference Architecture**.

## Purpose
- Centralize logos, diagrams, and other shared visual materials.
- Maintain consistent references across `docs/` and presentation materials.
- Prevent the folder from being pruned in Git repositories when temporarily empty.

## Guidelines
- Use **SVG** or **high-resolution PNG** for diagrams.
- Keep filenames descriptive (e.g., `logo_federated.svg`, `diagram_layers.png`).
- Avoid committing large binary assets (>5 MB).
- Place generated figures from `.mmd` sources here if needed for publication.

---

_This folder remains part of the repository to ensure reproducibility and consistency in published documents._