# AI Development Framework — Extractor Component

Locked Extractor component for producing a clean, production-deployable project from the complete development workspace.

Core rule: extract everything the application needs to run, and exclude development/AI scaffolding that is not a runtime dependency.

The original development project is never cleaned or modified in place. Extraction creates a separate output directory.
