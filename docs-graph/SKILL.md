---
name: docs-graph
description: Build an evolving map of project ideas and research reasoning with directories and Markdown. Use when agents need to resume unfamiliar reasoning across tasks without rereading the whole document collection.
---

# Docs Graph

Use the graph to preserve understanding: how ideas connect, why a choice was made, and what remains unresolved. Let filesystem search locate the underlying material.

- One directory is one node. Its name conveys the point; its `README.md` holds one logical unit, without a line limit.
- Children elaborate a node: supporting ideas, dependencies, details, or related material. Group related nodes under a parent that summarizes their connection. These are approximate natural-language relationships, not formal logic or a fixed ontology.
- Cross-references reuse nodes across branches and may form cycles. In READMEs, use `@root/a/b` for the node at `a/b` under the graph root; state that root in the root README. This is a logical address, not a literal filename containing slashes. Explain the relationship in ordinary prose; no required relation schema.
- Keep bulk data, logs, source documents, and dependency artifacts in separate project folders outside the thought graph; reuse existing locations. Nodes retain the implications for the reasoning and cite particular sources when useful, rather than copying their contents or cataloguing every file.
- Browse ideas with `tree -L N <path>` and selected READMEs; locate material with `rg --files <path>` and `rg -n 'pattern' <path>`. Maintain no parallel file inventory or exhaustive source index. New files alone do not require graph updates.
- Reuse a suitable documentation location, or start with `docs_graph/`. Build and revise the relevant nodes as actual work develops understanding; no full-corpus reading or complete hierarchy is required first. Capture the reasoning yourself rather than asking the user to formalize it into structured fields. Update the graph when understanding changes.
- Write nodes for another capable model. Use Shannon's conditional-information perspective: treat its existing knowledge as shared context. For each sentence, ask whether it already knows this or would already act this way. Keep only the information that shifts its default understanding or behavior toward the intended result; use concise concepts to invoke shared knowledge instead of explaining it again.

```text
docs_graph/
├── README.md
└── reliable-inference/
    ├── README.md
    ├── formal-verification/
    │   └── README.md
    └── experimental-validation/
        └── README.md
```

A README can say: “This also depends on the domain knowledge discussed at `@root/domain-knowledge`.” The directory tree provides the initial view; references extend it into a graph.
