# Extractor Global Rules

1. Framework global rules remain in force; Extractor rules may be stricter, never weaker.
2. Never modify or delete the source development project during extraction.
3. Preserve functionality over size or cleanliness. Never remove a component when it is required at runtime.
4. Determine the runtime set from the engineering/code structure and dependency evidence, not from a manually maintained file list.
5. Exclude AI/development scaffolding when it is not a runtime dependency: builder guides/templates, plans, checkpoints/state, development-only agents/plugins/skills/MCPs/hooks, research notes, and similar framework metadata.
6. If any normally excluded component is genuinely required by the production application, retain the minimum runtime-required portion or ask the engineer when the dependency cannot be resolved safely.
7. Preserve required application code, runtime packages, assets, binaries, configuration, runtime scripts, and environment files/values needed by the application.
8. Environment files copied into output are sensitive runtime material. Copy required values without printing them into reports, logs, manifests, Markdown, or checkpoints.
9. Ask the engineer only for genuine ambiguity, blocked extraction, or an explicit decision that cannot be derived safely.
10. Testing the extracted output is optional and requires engineer choice. If requested, test the extracted copy independently from the development directory.
11. Do not report extraction as successful if required runtime content is known to be missing.
12. Keep extraction state compact: decisions, unresolved ambiguities, retained runtime exceptions, output location, and status only.
## Strict Modular Code Rule

- Never place a large amount of implementation code into a single file when the code can be separated by responsibility.
- Prefer small, focused files with one clear responsibility and explicit interfaces between them.
- During creation, modification, refactoring, extraction, review, or improvement, proactively identify oversized or mixed-responsibility files and recommend or perform appropriate bifurcation when modification is permitted.
- Do not split code arbitrarily: preserve cohesion, runtime behavior, dependency correctness, and maintainability.
- This rule applies across every project component and every development/building workflow.
- Evaluation-only components may recommend modularization but must remain read-only when their own rules prohibit code changes.

