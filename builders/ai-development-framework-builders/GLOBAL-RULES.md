# Global AI Operating Rules

1. These rules have precedence over every Builder, Agent, Plugin, Skill, MCP, and Hook. Local rules may be stricter, never weaker.
2. Load minimum relevant context only. Do not load unrelated components, histories, skills, MCPs, plugins, or builder discussions.
3. At approximately 70% context utilization, checkpoint verified state, compact, clear nonessential context, then reload only the minimum state required to continue.
4. Persistent files are durable memory; conversation history is not the project memory system.
5. Preserve verified results, approved decisions, dependencies, current position, unresolved work, and next action. Compress/remove repetition, obsolete reasoning, debug noise, redundant tool output, and failed attempts with no continuing value.
6. Do not blindly retry. Diagnose first. Retry only when the correction materially changes execution. If execution loops or repeated automated testing cannot resolve a failure, stop and request engineer intervention/manual verification.
7. Record success only when automation verifies it or an engineer explicitly verifies it after escalation.
8. Apply least privilege to context, tools, credentials, permissions, MCP actions, filesystem access, and external services.
9. Builder research and explanations are build-time information. Do not automatically place them in production runtime context.
10. Master Builder Guides and Templates are read-only during project work. Generate working copies and artifacts elsewhere.
11. Security/improvement evaluators may read/test/report but may write only in their designated shadow evaluation trees; they never modify the real project.
12. Never expose secrets in Markdown, templates, logs, checkpoints, or source control. Reference environment-variable names only.
## Strict Modular Code Rule

- Never place a large amount of implementation code into a single file when the code can be separated by responsibility.
- Prefer small, focused files with one clear responsibility and explicit interfaces between them.
- During creation, modification, refactoring, extraction, review, or improvement, proactively identify oversized or mixed-responsibility files and recommend or perform appropriate bifurcation when modification is permitted.
- Do not split code arbitrarily: preserve cohesion, runtime behavior, dependency correctness, and maintainability.
- This rule applies across every project component and every development/building workflow.
- Evaluation-only components may recommend modularization but must remain read-only when their own rules prohibit code changes.

