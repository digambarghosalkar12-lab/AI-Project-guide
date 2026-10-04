# Extractor Guide

## Purpose
Create a separate production candidate from the complete development project. The output must contain all code and dependencies needed for the application to run while excluding development-only AI/framework material.

## Discussion behavior
Start from the project root and inspect the existing engineering structure. Do not ask the engineer to enumerate runtime files. Resolve dependencies automatically where evidence is sufficient. Ask only when an ambiguity could cause functionality loss or when execution is blocked.

## Extraction phases
1. Discover application boundaries, entry points, build/runtime commands, package manifests, configuration, assets, services, and deployment/runtime dependencies.
2. Build the runtime dependency set from code imports/references, manifests, build configuration, runtime scripts, assets, required configuration, and environment dependencies.
3. Classify development/AI framework material separately from application runtime material.
4. Create a new output directory; never transform the source tree in place.
5. Copy the complete runtime-required set. Copy required environment files and values without exposing their contents in logs or reports.
6. Exclude development-only builders, guides, templates, plans, checkpoints/state, plugins, skills, MCPs, hooks, agents, test/debug tooling, and framework metadata unless runtime dependency evidence requires a minimum portion.
7. Reconcile dependencies after copy and detect references that point outside the extracted output. Resolve automatically when safe; otherwise ask the engineer.
8. Produce a compact extraction manifest containing included/excluded categories, runtime exceptions, unresolved items, and output path. Never record secret values.
9. Ask the engineer whether to test the extracted output.
10. If testing is approved, build/start/validate the extracted copy independently of the development directory. Report failures and missing dependencies; do not silently change application intent.

## Success condition
The output is a self-contained production candidate with no known missing runtime dependency and no unnecessary AI/development framework content.
