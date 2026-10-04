# Framework Guide

## A. Before Building
Ask three questions:

### 1. What size project is this?
- Small / standalone
- Intermediate
- Enterprise / high complexity

### 2. How far should it be decomposed?
Break it into components until each component is easy for a developer and AI to understand, minimally document, independently design/update, improve, and test. If a component needs huge documentation merely to explain itself, consider decomposing it further.

### 3. What capabilities does each component need?
Use the analogy:
- Agent = worker / role
- Skill = knowledge + procedure / how work is performed
- MCP = tool / action capability
- Plugin = controlled packaging/binding of capabilities
- Hook = event-triggered behavior

## B. Component Model
Each component has a minimal `COMPONENT.md`, plus local `PLAN.md`, `IMPROVEMENT.md`, and `HISTORY.md`. Other components should normally need only the minimal component contract, not its full internal history.

## C. Capability Isolation
Directory existence does not mean automatic context loading. Load capabilities lazily. Duplication is acceptable when it improves isolation, clarity, and independent evolution.

## D. Context Lifecycle
Normal flow:
1. Clean context.
2. Load minimum required context.
3. Execute.
4. Automated test.
5. Verify result.
6. Persist verified state.
7. Continue.
8. At ~70% context utilization, checkpoint and compact.
9. Reload only the minimum continuation state.

Manual testing is an escalation path only after repeated unresolved automated failure/looping.

## E. Shadow Evaluations
`security-evaluation/` and `improvement-evaluation/` mirror the relevant project/component structure. Evaluator LLMs inspect/test the real project in read-only mode and write findings only to their own shadow tree. Development agents later validate and selectively implement findings through the normal development/test workflow.

### Security evaluation flow
1. Core discovery identifies languages, frameworks, components, dependencies, APIs, databases, authentication, infrastructure, tools, and technologies.
2. Build a security evaluation agenda.
3. Evaluate components sequentially using component-specific security skills/MCPs.
4. Record findings under `security-evaluation/`.

### Improvement evaluation flow
1. Core discovery maps the project.
2. Evaluate components sequentially for architecture, quality, performance, maintainability, complexity, documentation, component design, and AI efficiency.
3. Record findings under `improvement-evaluation/`.

## F. Capability Builders
Builders are developed independently in this order/current scope:
1. Agent Builder
2. Skill/MCP Builder
3. Plugin Builder
4. Hooks Builder

A builder is a structured AI interview: raw template -> discuss intent -> ask only missing information -> fill specification -> review -> generate -> independently test -> verify -> register into the target component.

Do not mix detailed builder designs prematurely.
