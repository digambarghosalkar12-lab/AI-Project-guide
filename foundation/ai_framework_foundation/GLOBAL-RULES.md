# Global AI Operating Rules

## 1. Context Isolation
Load only the minimum information required for the active operation: project essentials, active component, active agent, active skill, required MCP definitions, and current task.

Do not automatically load every component, plan, history, agent, skill, MCP, or evaluation.

## 2. Context Lifecycle
Each agent operates within a bounded context/token budget. Start with clean minimal context. At approximately 70% utilization, checkpoint and smart-compact. Use exact telemetry when available and estimation otherwise.

Preserve verified state, current task position, important decisions, dependencies, unresolved work, and continuation information. Compress/remove chatter, repeated output, obsolete intermediate information, debugging noise, and failed-attempt repetition.

## 3. Persistent State
Conversation is not permanent project memory. Persist verified state into the appropriate project/component MD files.

## 4. Testing
Automated testing is the default. Never blindly retry the same failed operation. If automated testing repeatedly produces the same unresolved failure/result or enters a loop, stop and ask the engineer to manually test. Record the engineer's working/not-working result before continuing.

Never record uncertain or failed work as success.

## 5. Capability Exposure
Agents receive only the skills and MCP/tools required for their active responsibility. Prefer focused component-specific capabilities over large generic capability sets when this reduces context and ambiguity.

## 6. Boundaries
Agents remain inside their assigned component/capability boundaries unless explicitly authorized. Cross-component changes require deliberate review.

## 7. Evaluators
Security and improvement evaluators may read and test the real project but may not modify it. They can write only inside their corresponding shadow evaluation directories.
## Strict Modular Code Rule

- Never place a large amount of implementation code into a single file when the code can be separated by responsibility.
- Prefer small, focused files with one clear responsibility and explicit interfaces between them.
- During creation, modification, refactoring, extraction, review, or improvement, proactively identify oversized or mixed-responsibility files and recommend or perform appropriate bifurcation when modification is permitted.
- Do not split code arbitrarily: preserve cohesion, runtime behavior, dependency correctness, and maintainability.
- This rule applies across every project component and every development/building workflow.
- Evaluation-only components may recommend modularization but must remain read-only when their own rules prohibit code changes.

