---
name: docs-graph
description: Encode an evolving reasoning graph with directories and Markdown. Use when agents need to resume unfamiliar reasoning across tasks without rereading the whole document collection.
---

# Docs Graph

Use the filesystem as a lightweight encoding of a reasoning graph, not as a project documentation repository. The nodes and their relationships are the substance; directories are addresses and READMEs are their natural-language expressions. Preserve how ideas connect, why a choice was made, and what remains unresolved. Let filesystem search locate the underlying material.

- One directory is one node. Its name conveys one independently useful point; its `README.md` holds that logical unit, without a line limit. Do not make a node merely because a project has a subsystem, phase, document, or task with that name.
- Treat a decision as an organizing node, not a complete explanation. Put the chosen conclusion in its README, then split the constraints, observations, tradeoffs, rejected alternatives, and consequences that materially support it into separate point nodes. A decision should therefore usually have several child nodes and may reuse the same constraint through `@root/...` from other decisions.
- Borrow the perspective of knowledge graphs, causal models, and argument networks: nodes may represent facts, concepts, constraints, decisions, questions, or consequences, and relations may express support, dependence, limitation, conflict, explanation, or possible causation. Use causal language only when the relationship is actually causal. Keep relations in ordinary prose; do not impose an ontology, triple format, or exhaustive edge vocabulary.
- Children elaborate a node: supporting ideas, dependencies, details, or related material. Group related nodes under a parent that summarizes their connection. These are approximate natural-language relationships, not formal logic or a fixed ontology.
- Cross-references reuse nodes across branches and may form cycles. In READMEs, use `@root/a/b` for the node at `a/b` under the graph root; state that root in the root README. This is a logical address, not a literal filename containing slashes. Explain the relationship in ordinary prose; no required relation schema.
- Keep bulk data, logs, source documents, and dependency artifacts in separate project folders outside the thought graph; reuse existing locations. Nodes retain the implications for the reasoning and cite particular sources when useful, rather than copying their contents or cataloguing every file.
- Browse ideas with `tree -L N <path>` and selected READMEs; locate material with `rg --files <path>` and `rg -n 'pattern' <path>`. Maintain no parallel file inventory or exhaustive source index. New files alone do not require graph updates.
- Reuse a suitable documentation location, or start with `docs_graph/`. Build and revise the relevant nodes as actual work develops understanding; no full-corpus reading or complete hierarchy is required first. Capture the reasoning yourself rather than asking the user to formalize it into structured fields. Update the graph when understanding changes.
- Write nodes for another capable model. Use Shannon's conditional-information perspective: treat its existing knowledge as shared context. For each sentence, ask whether it already knows this or would already act this way. Keep only the information that shifts its default understanding or behavior toward the intended result; use concise concepts to invoke shared knowledge instead of explaining it again.

```text
docs_graph/
├── README.md
└── choose-delayed-model/
    ├── README.md
    ├── delay-history-is-state/
    │   └── README.md
    ├── reduction-needs-validation/
    │   └── README.md
    └── compute-budget-favors-approximation/
        └── README.md
```

Here `choose-delayed-model` is the decision; its children are separate reasons that constrain it. A README can say: “This also depends on the domain knowledge discussed at `@root/domain-knowledge`.” The directory tree provides the initial view; references extend it into a graph.
