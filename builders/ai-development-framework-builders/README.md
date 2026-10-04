# AI Development Framework — Builder Set

This package is the locked builder foundation for creating AI capabilities with bounded context, explicit capability boundaries, testing, checkpointing, and least privilege.

## Immutable builder tree

```text
builders/
├── agent-builder/
│   ├── GUIDE.md
│   ├── STATE.template.yaml
│   └── template/
│       ├── config.yaml
│       ├── AGENT.md
│       ├── PLAN.md
│       └── .env.example
└── plugin-builder/
    ├── GUIDE.md
    ├── STATE.template.yaml
    ├── template/PLUGIN.md
    ├── skill-builder/
    │   ├── GUIDE.md
    │   ├── STATE.template.yaml
    │   ├── template/SKILL.md
    │   └── mcp-builder/
    │       ├── GUIDE.md
    │       ├── STATE.template.yaml
    │       └── template/MCP.md
    └── hook-builder/
        ├── GUIDE.md
        ├── STATE.template.yaml
        └── template/HOOK.md
```

## Operating order

`GLOBAL-RULES → GUIDE → working copy of TEMPLATE → engineer discussion → checkpoint → approval → generate → validate → functional test → register → compact → resume/return`

Master Guides and Templates are read-only during normal project development. A project uses working copies. Builder state contains only approved decisions, completed dependencies, resume position, and next action.
