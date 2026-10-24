# docs-graph skill

`docs-graph` encodes a reasoning graph with directories and `README.md` content. The filesystem is only the graph's lightweight address and storage layer; the substance is the relationships between independently useful points. It borrows from knowledge graphs, causal models, and argument networks while keeping relations in natural language. A decision is an organizing node whose constraints, evidence, tradeoffs, and consequences are separate child points; cross-references connect reused points into a graph.

Relationships stay in natural language. The model explores ideas with `tree` and selected READMEs, then uses `rg` to find underlying material. Bulk data and source documents stay outside the graph; there is no file inventory to synchronize. Update nodes as understanding changes.

See [the skill](docs-graph/SKILL.md) for the conventions. It works with or without Git.

## Install

Copy the skill folder into your Codex skills directory:

```bash
mkdir -p ~/.codex/skills
cp -r docs-graph ~/.codex/skills/docs-graph
```

Restart Codex so it discovers the skill.
