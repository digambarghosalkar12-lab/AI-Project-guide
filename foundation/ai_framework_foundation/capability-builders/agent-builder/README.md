# Agent Builder — Locked Checkpoint

Current agreed structure:

agents/
├── .env
├── .env.example
└── <agent-name>/
    ├── config.yaml
    ├── AGENT.md
    └── PLAN.md

## Runtime loading
1. Read the individual agent's `config.yaml`.
2. Load only environment variables named as required by that config from the agents-root `.env`.
3. Load that agent's `AGENT.md`.
4. Load the relevant `PLAN.md`.
5. Execute.

An agent does not load another agent's files by default.

`.env` contains real runtime configuration/secrets and must not be committed. `.env.example` declares required variable names with safe placeholders only.

This is the current locked checkpoint. Detailed Agent Builder questionnaire/specification is the next unfinished design task.
