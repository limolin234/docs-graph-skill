---
name: docs-graph
description: Use when a project needs repo-local agent memory, modular project documentation, architecture notes, handoffs, or a lightweight alternative to oversized AGENT.md files. This skill organizes project-scoped context as a concise Markdown folder tree inside the project, using filesystem paths as a simple docs graph. It works without Git; when the project uses Git, the docs graph is versioned with the source automatically.
---

# Docs Graph

Use a small Markdown folder tree inside the project as project-scoped agent memory.

## Core idea

A docs graph is local project documentation shaped as a filesystem tree:

- directories define modules, topics, or context boundaries
- Markdown files contain concise human/agent-readable notes
- a same-name Markdown file may serve as a directory entry note, for example `runtime/runtime.md`
- the tree is path-addressable, selectively readable, and easy to edit
- if the project uses Git, these notes naturally version, diff, branch, and roll back with the source

Do not create a separate Git repository, vector database, or graph database by default. The local Markdown tree is the substrate.

## When to use

Use this skill when the user asks to:

- organize project memory or durable context
- record architecture decisions, module boundaries, or handoffs
- split or avoid an oversized `AGENT.md`
- make project context easier for coding agents to selectively read
- keep implementation notes close to the project they describe

## Default layout

Prefer the smallest useful tree, such as:

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

Code-adjacent notes are also acceptable when that better matches the project:

```text
src/
└── memory/
    ├── memory.md
    └── retrieval/
        └── retrieval.md
```

Follow the repository's existing documentation style when one exists.

## Workflow

1. Inspect the project root and read `AGENTS.md` / `AGENT.md` if present.
2. Check for existing docs or a docs graph convention before creating new files.
3. Create or update the smallest relevant Markdown file for the task.
4. Write stable project knowledge: decisions, invariants, architecture boundaries, module explanations, commands, and next steps.
5. Keep transient reasoning out unless it has become durable project context.
6. Keep notes concise; split by module or concern when a file grows too large.
7. If the project uses Git, update docs graph files with related code changes when practical.

## Boundary with global memory

Use global instructions or global memory for cross-project defaults and user preferences.

Use the project docs graph for project-specific knowledge that should travel with the project directory.
