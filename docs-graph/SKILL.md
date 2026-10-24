---
name: docs-graph
description: Organize evolving project knowledge and research reasoning as a navigable graph of directories and Markdown. Use when scattered documents make context expensive to rediscover, or project understanding should accumulate across tasks.
---

# Docs Graph

Let the filesystem carry the overview; let the model interpret meaning and choose what to read.

- One directory is one node. Its name conveys the point; its `README.md` holds the content. Size nodes by logical unity, not a line limit. Keep coherent evidence such as tables intact.
- Children elaborate a node: supporting ideas, dependencies, details, or related material. Group related nodes under a parent that summarizes their connection. These are approximate natural-language relationships, not formal logic or a fixed ontology.
- Cross-references reuse nodes across branches and may form cycles. In READMEs, use `@root/a/b` for the node at `a/b` under the graph root; state that root in the root README. This is a logical address, not a literal filename containing slashes. Explain the relationship in ordinary prose; no required relation schema.
- Reuse the project's existing documentation location, or start with `docs_graph/`. Build from the material encountered during actual work; do not require reading the entire corpus or designing a complete hierarchy first. Revise local summaries and placement as understanding develops, retaining pointers to original material.
- Browse with `tree -L N <path>`, locate paths with `rg --files <path>`, and search content with `rg -n 'pattern' <path>`. Read selected READMEs and follow relevant references. Search original documents when the graph is insufficient; the graph need not be complete. Use existing filesystem tools rather than adding a query engine.
- Leave newly understood project reasoning in the relevant nodes so the next task can resume from it. Include the connections that make a conclusion understandable, rather than making the user rewrite their research into structured fields.
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
