---
name: setup-adr
description: Set up ADR inclusion criteria and maintenance rules in a project's AGENTS.md, with an optional inline glossary. Run once to establish conventions that guide subsequent work.
disable-model-invocation: true
---

# Set Up ADR Rules

Write ADR management rules and, optionally, a glossary directly into the target project's `AGENTS.md`. Subsequent work follows those rules without invoking this skill again.

## Initialization

1. Read the project's existing agent instructions and documentation conventions. Reuse the ADR location specified by the user or established by the project; ask where to store ADRs only when no location has been determined.
2. Explore the project's code and documentation for candidate terms that meet the glossary criteria below. If any qualify, present concise definitions and unresolved ambiguities, and ask whether to include them. Reuse established definitions; do not treat permission to enable the glossary as agreement with inferred meanings. Keep unsettled definitions out of the glossary. Terms belong directly in `AGENTS.md`.
3. Merge the applicable rules below into the project root's `AGENTS.md`. Replace the example ADR path with the chosen location, relative to that file. Preserve unrelated instructions and merge equivalent rules. If existing conventions materially conflict with the inclusion criteria and the user has not resolved the conflict, explain it and ask.
4. Populate the ADR index with existing ADRs in the chosen directory, using links relative to `AGENTS.md` and a one-sentence description for each. Do not invent historical decisions to fill the index.

Preserve the meaning of the rules below while adapting their wording and language to the project. After initialization, check paths, duplicates, and conflicts, and report where the rules were written and whether the glossary was included.

## Rules to Write into AGENTS.md

### ADR Rules

```markdown
## ADR

| ADR | Description |
| --- | --- |

### Inclusion Criteria

Store ADRs in `docs/adr/`. They preserve the context and rationale for significant architectural decisions. Create an ADR only when all three conditions hold:

- Costly to reverse: changing the decision would involve data migration, external contracts, coordination across modules, or other substantial migration costs beyond a local replacement.
- Not self-explanatory: future maintainers could not understand why this option was chosen from the code or outcome alone.
- A real trade-off: viable alternatives existed, and the chosen option accepts explicit costs in exchange for benefits.

If any condition is missing, do not write an ADR. Do not invent alternatives or rationale to satisfy these criteria.

Local implementation details, routine dependency upgrades, straightforward bug fixes, progress reports, meeting summaries, and to-dos do not belong in ADRs. Keep requirements, acceptance criteria, and implementation steps in specs or plans, and procedures in the appropriate guides. If an architectural choice within that work meets all three criteria, record it separately and link to the source instead of duplicating it.

### Maintenance

- Maintain the index in this section when adding, moving, renaming, or deleting an ADR. Use links relative to this `AGENTS.md` and a one-sentence description for each entry. Update descriptions when the content changes their meaning.
- Before changing something governed by an existing decision, read the relevant ADRs and check their status and scope. Record choices and their rationale; never present an option still under discussion as an accepted decision. Mark decisions awaiting agreement as proposed.
- Keep each ADR focused on one decision, including its status, context, choice, alternatives actually considered, rationale, and accepted consequences. Use enough detail to explain the trade-off rather than listing only the conclusion. Follow the project's template; otherwise use sequentially numbered `NNNN-short-title.md` files and the statuses proposed, accepted, superseded, or deprecated.
- When reversing a decision, create a new ADR explaining the change, link both records to each other, and mark the old record superseded. Mark a decision deprecated if it no longer applies and has no replacement. Preserve its original context and rationale; correct typos and add links without rewriting history to match the current conclusion.
- Record settled decisions that meet the criteria as part of the relevant work. Do not infer historical rationale solely from existing code. Clarify missing evidence instead of fabricating records.
```

### Glossary Rules (Optional)

```markdown
## Glossary

| Term | Definition |
| --- | --- |

### Inclusion Criteria

- Include a term only when it is important to the project, has a project-specific meaning, and is difficult to understand or easy to misinterpret even with the broader project context.
- Define each concept and its necessary boundaries in one or two sentences. Do not expand entries into requirements, business processes, or implementation plans.
- Exclude general programming vocabulary, code symbol inventories, field dictionaries, and similar reference material.

### Maintenance

- Maintain term entries directly in this section of `AGENTS.md`. The glossary reflects current meanings, not decision history.
- Reuse established definitions and add or revise entries when their meanings are settled. Do not write unresolved interpretations as canonical definitions.
- When the glossary, code, and the user's statements disagree, point out the specific contradiction and seek clarification.
```
