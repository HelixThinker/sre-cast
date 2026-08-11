---
name: mock-cast-foundation
description: "Draft a traceable, explicitly provisional CAST foundation from supplied SRE incident evidence. Use when demonstrating or testing the SRE CAST skill infrastructure, or when an analyst wants a mock draft of losses, system boundaries, hazards, safety constraints, neutral event description, and open questions before controller analysis. Do not use as a final incident report or as a substitute for human review."
---

# Mock CAST Foundation

Create a provisional foundational CAST artifact without inventing missing facts.
Keep evidence, interpretation, hypotheses, and unknowns visibly distinct.

## Operating rules

- Work only from evidence supplied by the user or retrieved from sources the user
  authorized.
- Treat absence of evidence as an unknown, not as proof that an event did not
  occur.
- Use neutral explanatory language. Do not assign blame or stop at a single root
  cause.
- Give every evidence item and analytical entity a stable ID.
- Preserve contradictions and unresolved questions instead of silently choosing
  one account.
- Mark the result `mock-draft`; require a human analyst to review it.
- Stop at the foundation. Do not perform controller analysis, systemic-factor
  analysis, or recommend corrective actions.

## Workflow

1. Read [the foundation contract](references/foundation-contract.md) before
   classifying incident material.
2. Inventory the supplied sources as `E-001`, `E-002`, and so on. Record source,
   access state, and a short relevance note. Never claim to have read an
   inaccessible source.
3. Establish the provisional system scope, relevant time window, and explicit
   exclusions. Turn missing scope decisions into open questions.
4. Draft losses, hazards, and safety constraints using the relationships and
   labels in the foundation contract. Attach evidence IDs to facts; label every
   unsupported analytical proposition as an interpretation or hypothesis.
5. Write a neutral event description that reports sequence and context without
   converting uncertainty into certainty.
6. Create stable `Q-###` items for every material gap, contradiction, or
   unverified hypothesis. State why each answer matters to the analysis.
7. Populate [the output template](assets/foundation-analysis-template.md).
   Replace every placeholder; use `Unknown — see Q-###` when information is
   missing.
8. Review the draft before returning it. Confirm that no placeholders remain,
   every substantive statement has a classification label, IDs are consistent,
   and the human-review boundary is explicit. Never invent content to make the
   draft appear complete.
9. Return the artifact and a short list of the highest-impact questions requiring
   human investigation.

## Output contract

- Produce one Markdown artifact based on the bundled template.
- Preserve all required headings even when a section contains only an explicit
  unknown.
- Use the exact classification labels defined in the foundation contract.
- Keep traceability directional: evidence supports statements; hazards relate to
  losses; safety constraints address hazards; questions expose gaps.
- State that the output is a demonstration draft and has not completed CAST.

If the runtime cannot read a bundled resource, complete only the supported part
of the analysis and state the limitation explicitly.
