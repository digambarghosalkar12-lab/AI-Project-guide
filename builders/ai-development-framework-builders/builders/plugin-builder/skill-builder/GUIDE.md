# Skill + MCP Builder Guide

## Definition
A Skill is the minimum operational procedure needed to perform an approved capability. Its required MCPs are built/configured as part of the same capability unit.

## Discussion framework
1. Ask intent: what should this Skill do, why is it needed, and what outcome means success?
2. Ask the engineer to list desired operations and explicit non-goals/restrictions.
3. Map workflow: trigger, inputs, steps/behavior, outputs, validation.
4. Identify environment/services/technologies involved.
5. Determine what can be achieved by instructions alone and what needs external tool capability.
6. Research technical details the Builder can discover itself. Explain material choices to the engineer; do not force the engineer to supply discoverable implementation details.
7. For each external need, invoke MCP Builder: reuse/configure an existing MCP when suitable, otherwise build a minimal custom MCP.
8. Apply least privilege. Expose only actions, permissions, scopes, credentials, and resources needed by this Skill.
9. Generate minimal runtime SKILL.md. Keep research, alternatives, and builder discussion outside runtime context.
10. Test Skill, MCPs independently, Skill→MCP interaction, boundaries/forbidden operations, failure/intervention behavior, and expected outputs.
11. Obtain engineer verification/approval and lock the Skill before returning to Plugin Builder.

## Plugin-specific rule
When derived from an existing Skill, copy only relevant content, then compact/trim it to the Plugin's intended work. Remove unused MCP operations rather than merely hiding them.
