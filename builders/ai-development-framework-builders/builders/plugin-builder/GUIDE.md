# Plugin Builder Guide

## Definition
A Plugin is a controlled package/orchestrator of plugin-specific verified Skills. Agents are never embedded in Plugins; independent Agents may load Plugins when needed.

## Entry rule
Do not assemble a Plugin before its required Skills exist and are verified.

## Guided discovery
1. Ask the engineer the Plugin's purpose, desired outcomes, and restrictions.
2. Derive the required capability/Skill list. If the engineer already has a list, validate it.
3. For each required Skill, create a minimal child brief and redirect to Skill Builder one Skill at a time.
4. After each Skill is verified, checkpoint it, compact context, and continue with the next Skill.
5. Plugin-specific Skills may be derived from existing Skills, but must be compacted/trimmed to the exact Plugin need. Do not copy a broad Skill unchanged when fewer operations suffice.
6. Load only verified Skill interfaces/specifications when assembling the Plugin; do not load their development histories.
7. Define orchestration only: ordering, conditions, transitions, and data passed between Skills. Operational knowledge stays in Skills.
8. Discover runtime dependencies/intervention points: authentication, permissions, credentials, services, files, user decisions, network/dependency states.
9. For every known interruption, define visible reasoning: what blocked execution, why, and what user action is needed. Convert each into a test case.
10. Unknown failures follow Global Rules.
11. Integration-test Skill transitions and Plugin workflows.
12. Only after Plugin capabilities are finalized and tested, invoke Hook Builder.

## Dependency flow
`Plugin purpose → Skill list → [Skill + MCP build/test/lock] × N → compact → assemble Plugin → integration test → Hook Builder → final validation → register`
