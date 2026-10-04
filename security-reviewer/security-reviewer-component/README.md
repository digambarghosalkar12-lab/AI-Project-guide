# Security + Reviewer Component

Read-only evaluation component for clean extracted production candidates.

It maps the project, reviews one logical component at a time while preserving hierarchy and relevant dependencies, and writes evidence-backed security and engineering improvement recommendations. It never changes application code.

## Output
All reports are stored under a top-level `review/` directory that mirrors the production project hierarchy. Every evaluated component receives one `<component>-security-improvement.md` file.
