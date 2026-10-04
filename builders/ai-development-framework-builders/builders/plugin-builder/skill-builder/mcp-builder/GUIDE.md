# MCP Builder Guide

## Purpose
Provide only the external actions a Skill actually needs.

## Process
1. Read the approved Skill requirement, not the entire Plugin discussion.
2. Enumerate exact external actions required.
3. Research whether a suitable existing MCP/tool implementation exists and verify authoritative technical requirements where needed.
4. If suitable, configure/trim it to required actions only. If unsuitable or absent, design and build a minimal custom MCP.
5. Define tool/action name, purpose, inputs, outputs, errors, authentication/env variable names, scopes/permissions, side effects, and forbidden actions.
6. Never store real credentials in templates, Markdown, checkpoints, or source control.
7. Test each MCP action independently, including permission/authentication failures and forbidden operations.
8. Return only the verified MCP interface to Skill Builder; keep implementation/debug history out of Skill runtime context.
