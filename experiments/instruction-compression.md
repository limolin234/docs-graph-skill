# Instruction compression pilot — 2026-10-24

Question: can instructions omit what a capable model already does, while preserving the project-specific directions that change its behavior?

## Design

An independent compressor saw a deliberately verbose project-status policy, but not the downstream tasks. Six fresh executor agents received two synthetic Chinese status-writing tasks under three conditions: no policy, full policy, or compressed policy. An independent reviewer received the six outputs in shuffled order without condition labels and scored eight criteria defined before executor results were collected. All agents inherited the parent model; no model override or conversation history was supplied. Executors used no tools. This tests text deliverables, not actual repository operations.

This is a matched-policy comparison, not a comparison between the old and new docs-graph skill: those versions change substantive conventions.

## Results

| Condition | Instruction words | Task 1 / 8 | Task 2 / 8 |
| --- | ---: | ---: | ---: |
| No policy | 0 | 6.5 | 7 |
| Full policy | 577 | 8 | 8 |
| Compressed policy | 220 | 8 | 8 |

Instruction words decreased 61.9%; UTF-8 bytes decreased from 3,803 to 1,615 (57.5%). These are word and byte counts, not model token counts. No latency, API cost, attention, or total-agent-cost improvement was measured. Total pilot work included eight agents: one compressor, six executors, and one evaluator.

Both no-policy notes already preserved source IDs, conflicts, numerical ranges, owner omissions, and execution-scope distinctions. They did not invent the local verified/provisional status vocabulary and classification convention. One partially organized the result by topics rather than reader decisions.

Both compressed-policy notes satisfied the eight scored requirements, as did both full-policy notes. The reviewer nevertheless found one unnecessary addition in compressed task 2: it marked performance scope unspecified for D-3 even though D-3 was a design proposal without a performance result. Thus equal rubric scores do not mean identical quality or zero compression risk.

The compressed policy retains some arguably generic reminders, such as distinguishing observations from estimates. This pilot evaluates one compression attempt as a whole; it does not establish that each surviving sentence is necessary or that every deleted sentence is universally redundant.

## Interpretation

The pilot supports the feasibility of removing generic exposition while preserving useful behavioral departures on these tasks. It supplies no evidence that compression improves answer quality over full instructions, and no broad claim that shorter instructions are always better.

The operational criterion is behavioral contribution: would removing a sentence change the intended downstream behavior? Linguistic rarity is only a heuristic. A rare irrelevant sentence can be useless; a familiar instruction may still change behavior in a particular workflow. No token probabilities, entropy, or information-theoretic optimum were measured.

The next useful experiment would use existing skills not constructed for this test, multiple independent runs, actual tool actions, and targeted deletion of individual instructions. Evaluate against the intended task outcomes, including failure cases, rather than readability judgments alone. A separate reusable compression skill remains a candidate, not a validated outcome.

## Limitations

Two synthetic tasks from one narrow domain, one output per condition per task, and one model family are insufficient for statistical or cross-task generalization. The full policy intentionally contains generic padding, so it is an easy compression case. Blinding hid condition labels from the evaluator, but output wording can reveal them. There was no test of preserving a difficult exception, authority boundary, or safety-critical operational constraint. The dated artifact paths were synthetic supplied records, not files whose existence was verified.

Complete prompts, source records, agent identifiers, outputs, shuffled labels, rubric, and reviewer findings are in [the raw record](instruction-compression.json). No separate compression skill was created.
