# docs-graph skill

`docs-graph` organizes evolving project knowledge as directories with `README.md` content. Names and nesting provide an overview; cross-references connect branches into a graph.

Relationships stay in natural language. The model explores with `tree` and `rg`, reads relevant nodes, and improves the graph as it works. No fixed ontology, line limit, or database is required.

See [the skill](docs-graph/SKILL.md) for the conventions. It works with or without Git.

## Install

Copy the skill folder into your Codex skills directory:

```bash
mkdir -p ~/.codex/skills
cp -r docs-graph ~/.codex/skills/docs-graph
```

Restart Codex so it discovers the skill.
