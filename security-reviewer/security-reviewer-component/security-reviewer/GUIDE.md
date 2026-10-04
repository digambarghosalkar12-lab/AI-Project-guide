# Security + Reviewer Guide

## Purpose
Evaluate an extracted production candidate without modifying it. Produce component-scoped security findings and future engineering improvement recommendations that another AI or engineer can use later with minimal context.

## Phase 1 — Project Mapping
1. Inspect the extracted project structure.
2. Identify logical components, subcomponents, entry points, interfaces, runtime dependencies, data flows, trust boundaries, and parent-child relationships.
3. Build a compact project map. Do not load the full repository into persistent context.
4. Initialize review state with hierarchy, pending components, dependency relationships, and resume position.

## Phase 2 — Component Evaluation
For each logical component, following the real project hierarchy:
1. Load the compact global project map.
2. Load the current component.
3. Load its parent chain and only directly relevant interfaces/dependencies.
4. Understand what the component does before selecting checks.
5. Derive appropriate security checks from its actual attack surface and technology.
6. Evaluate engineering concerns relevant to correctness, architecture, integration, maintainability, reliability, performance, dependency use, and future improvement.
7. Require evidence for each finding.
8. Mark uncertain items `Needs Verification`.
9. Assign security severity where applicable: Critical / High / Medium / Low / Informational, with reasoning.
10. Write/update the component's report.
11. Persist compact findings into state.
12. Clear detailed component context before moving to the next evaluation frame.

## Phase 3 — Cross-Component Recheck
If new evidence from a later component materially affects an earlier component:
1. Record the dependency/evidence that triggered the recheck.
2. Reopen only the affected project path and necessary dependencies.
3. Re-evaluate the affected concern.
4. Update the existing report; do not create a duplicate.
5. Compact again and return to the normal traversal position.

## Phase 4 — Completion
1. Confirm every mapped evaluation unit has a corresponding report or an explicit documented reason it was not reviewable.
2. Confirm unresolved uncertainties are marked `Needs Verification`.
3. Confirm no application code was changed.
4. Save final state/index for future targeted improvement work.

## Context Discipline
Use: Understand globally -> work locally -> preserve dependencies -> record -> compact -> clear -> continue.
Never retain unrelated branches simply because they were reviewed earlier.
