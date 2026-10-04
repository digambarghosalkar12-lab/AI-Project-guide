# Hook Builder Guide

## Definition
Hooks are Plugin-level lifecycle/event controls. They live at the Plugin control/root layer and invoke already-verified Plugin orchestration, Skills, and MCP capabilities. They do not duplicate operational implementation.

## Entry rule
Hooks are built last. Required MCPs, Skills, and Plugin orchestration must already be built and verified. If a dependency is missing, stop Hook construction, redirect to the appropriate Builder, verify it, compact, then resume.

## Derivation process
1. Load the final trimmed Plugin capability map only.
2. Identify operations that need recognizable control points for Agents/users.
3. Derive valid controls from what the underlying Plugin→Skill→MCP chain can actually support. Possible controls include START, RUN, WAIT, PAUSE, RESUME, STOP, STORE/CHECKPOINT, RESTART, or initiating another approved task—but none are mandatory.
4. Never advertise a control that the underlying capability cannot safely honor.
5. Define asynchronous state model and valid transitions for each Hook, e.g. IDLE→STARTING→RUNNING→WAITING/PAUSED→RUNNING→COMPLETED/STOPPED/FAILED.
6. Define invocation target, preconditions, state preservation, interruption semantics, user-visible reasoning, and recovery/resume behavior.
7. Test every valid transition, invalid transition, dependency/intervention state, safe stop, checkpoint/resume where supported, and concurrency/race behavior where relevant.
8. Expose only the minimal Hook interface needed to control the Plugin.
