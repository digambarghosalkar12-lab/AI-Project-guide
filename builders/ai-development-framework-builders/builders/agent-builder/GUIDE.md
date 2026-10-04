# Agent Builder Guide

## Purpose
Guide an engineer from an agent idea to a verified, registered agent without carrying unnecessary design history into runtime.

## Discussion sequence
1. Ask what the agent exists to accomplish and what successful output looks like.
2. Capture identity/runtime: name, model, required model settings, runtime environment, required environment-variable names.
3. Capture responsibilities and explicit boundaries: allowed actions, forbidden actions, stop/escalation conditions.
4. Define input/output contract.
5. Declare capabilities the agent may invoke: specific Plugins/Skills/Hooks only. Nothing is implicitly available.
6. Define minimum startup context and lazy-load rules. Apply global ~70% compaction policy.
7. Define failure behavior: diagnose before retry; no blind retry loops; engineer escalation when needed.
8. Define validation: structure, configuration, env names, boundaries, capability access, functional behavior.
9. Define version/compatibility metadata and registration target.
10. Explain material design choices to the engineer, but keep explanations out of production files unless operationally required.
11. Obtain engineer approval before generation.

## Generation lifecycle
`Raw Template → Guided Discussion → Completed Spec → Engineer Approval → Generate → Validate → Functional Test → Register → Ready`

## Runtime rule
PLAN.md is design/build-time documentation. Production should load stable runtime information from config.yaml, AGENT.md, required environment variables, and explicitly required capability interfaces. PLAN.md is loaded only when development/revision requires it.
