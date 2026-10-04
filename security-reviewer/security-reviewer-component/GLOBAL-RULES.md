# Global Rules

1. Evaluation is read-only. Never modify application code or configuration.
2. Understand the project globally, evaluate locally.
3. Review one logical component/evaluation frame at a time.
4. Preserve the real project hierarchy and parent-child relationships.
5. Keep only compact global context, current component, parent chain, relevant interfaces, dependencies, and necessary prior findings in active context.
6. After each component, persist findings, compact working context, clear unnecessary detail, then continue.
7. Every finding requires concrete code/configuration evidence. Generic unsupported recommendations are prohibited.
8. If evidence is insufficient, mark the item `Needs Verification`; never invent a vulnerability or defect.
9. Security severity uses: Critical, High, Medium, Low, Informational. Explain the reason for the selected severity.
10. A later finding may trigger a targeted recheck of an earlier affected component. Do not restart the entire review unless required.
11. Every evaluated component or subcomponent gets exactly one component-specific security/improvement Markdown report.
12. Reports live under top-level `review/`, mirroring the source project hierarchy.
13. Derive relevant security and engineering checks dynamically from the component's purpose, technology, interfaces, data, trust boundaries, and dependencies. Do not force an irrelevant static checklist.
14. Global framework rules and context/compaction rules always apply.
## Strict Modular Code Rule

- Never place a large amount of implementation code into a single file when the code can be separated by responsibility.
- Prefer small, focused files with one clear responsibility and explicit interfaces between them.
- During creation, modification, refactoring, extraction, review, or improvement, proactively identify oversized or mixed-responsibility files and recommend or perform appropriate bifurcation when modification is permitted.
- Do not split code arbitrarily: preserve cohesion, runtime behavior, dependency correctness, and maintainability.
- This rule applies across every project component and every development/building workflow.
- Evaluation-only components may recommend modularization but must remain read-only when their own rules prohibit code changes.

