# docs-graph skill

`docs-graph` is a small Codex skill for organizing project-scoped agent memory as a local Markdown folder tree.

Core idea:

> Use the project directory's filesystem tree as a lightweight docs graph for coding agents.

It works without Git. If the project uses Git, the docs graph is automatically versioned with the source.

## Install

Copy the skill folder into your Codex skills directory:

```bash
mkdir -p ~/.codex/skills
cp -r docs-graph ~/.codex/skills/docs-graph
```

Restart Codex so it discovers the skill.

## When it triggers

Use it for:

- project memory
- architecture notes
- module documentation
- handoffs
- replacing or splitting oversized `AGENT.md` files
- repo-local context that should travel with a project

## Example docs graph

```text
docs_graph/
├── docs_graph.md
├── architecture/
│   └── architecture.md
├── runtime/
│   └── runtime.md
└── memory/
    ├── memory.md
    └── retrieval.md
```

The tree itself is the graph: directories define context boundaries, and Markdown files hold concise notes.
