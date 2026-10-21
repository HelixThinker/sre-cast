# SRE CAST

SRE CAST is an open project for AI-assisted review of SRE postmortems using
CAST (Causal Analysis based on System Theory).

It helps an engineer examine an incident explanation, find gaps in the evidence,
understand decisions and feedback, and prepare useful questions and improvements.

## First product

The first product is the [sre-cast-review skill](skills/sre-cast-review/SKILL.md)
for engineers preparing or reviewing a postmortem.

Give it an incident report and the available supporting material. The
result is a concise review containing:

- **Supported conclusions and gaps:** what the sources establish, what is an
  interpretation, where accounts conflict, and what remains unknown.
- **Control and feedback analysis:** who or what made relevant decisions, which
  signals were available, and which constraints applied.
- **Prioritized questions:** what to ask incident participants next and why each
  answer matters.
- **Improvement discussion:** how existing action items and new proposals relate
  to the analysis, and how their intended effect could be observed.

When the evidence is incomplete, a useful result is a clear set of next questions
and explicit limits on the conclusions. The review can continue as new evidence
arrives.

## Get started

Follow the [installation and usage guide](skills/sre-cast-review/README.md) to
install the skill in Codex. Then invoke it with your incident material:

```text
$sre-cast-review
Review this postmortem using the attached timeline and deployment notes.
Identify supported conclusions and gaps, prioritize questions that would change
our decisions, and explain how the action items address the findings.
```

The guide includes Cloudflare and Facebook examples, local-file inputs, and
continuing a review with new answers. The package includes its CAST notes and
an adaptable output template; no additional runtime dependencies are required.

## Example of the intended interaction

An incident report says:

> An incorrect configuration caused the outage. We will add configuration review.

A useful review asks:

- What limited the scope of the configuration rollout?
- Which signals determined whether the rollout should continue?
- What information was available to the engineer at the time?
- How would the proposed review detect this particular class of problem?

These are illustrative questions. Answers must come from the incident material
or its participants.

## How the analysis works

CAST examines why the control structure did not prevent a loss and helps identify
which questions still need answers. Its analysis areas can be revisited as more
is learned. See the [CAST Handbook](https://psas.scripts.mit.edu/home/get_file4.php?name=CAST_Handbook.pdf),
printed pages 31–35.

The project applies these principles to incident reviews:

- Link important factual claims to specific supporting source passages.
- Distinguish what a source reports from what has been independently confirmed.
- Keep facts, interpretations, hypotheses, contradictions, and unknowns visible.
- Explain decisions in their context using blameless language.
- Relate improvement proposals to the evidence and the analyzed control
  weaknesses.
- Keep proposed improvements distinct from actions already agreed by a team.
- State the scope and limits of each review, including missing internal context.

## Worked reviews

[Cloudflare WAF outage — July 2, 2019](examples/cloudflare-2019-07-02/README.md)
is the first published example. It includes the evidence boundary, a control
model, prioritized questions, and improvement proposals. The
[source notes](examples/cloudflare-2019-07-02/sources.md) link to the relevant
passages and explain the choice of incident.

[Facebook backbone outage — October 4, 2021](examples/facebook-2021-10-04/README.md)
shows how to review incomplete evidence. It separates the operator's explanation
from external observations, prioritizes questions that change the choice of
improvements, and shows how to continue when new evidence arrives. Its
[source notes](examples/facebook-2021-10-04/sources.md) identify the three public
accounts and the limits of their support.

## Plan for v0.1

| Order | Deliverable | Issue |
| --- | --- | --- |
| 1 — done | [Cloudflare worked review](examples/cloudflare-2019-07-02/README.md) with sources, questions, and improvement discussion. | [#9 — First worked review](https://github.com/HelixThinker/sre-cast/issues/9) |
| 2 — done | [Usable review skill and quickstart](skills/sre-cast-review/README.md), based on the first worked review. | [#6 — Review skill and quickstart](https://github.com/HelixThinker/sre-cast/issues/6) |
| 3 — done | [Facebook worked review](examples/facebook-2021-10-04/README.md) with incomplete evidence, prioritized questions, and conditional proposals. | [#10 — Incomplete-evidence example](https://github.com/HelixThinker/sre-cast/issues/10) |

The v0.1 deliverables are the skill, its quickstart, and two worked reviews.

## Development approach

Development is kept lightweight while the project is built by its maintainer
with AI assistance. Work directly on the examples and skill, and improve them
through use.

The active plan has no standalone infrastructure workstream: source registries,
formal artifact or portability contracts, validators, CI, eval frameworks,
model benchmarks, and separate re-review or approval stages are outside v0.1.

Use ordinary Markdown, direct source links, and only the structure needed by the
current example. Add tooling when a concrete recurring need appears.

The locations are `skills/sre-cast-review/` for the skill and
`examples/` for worked reviews. Bundle the method references and output
resources that the skill actually uses. Broader template libraries, additional
skills, integrations, and a public website can follow practical use.

## Current status

The v0.1 scope is complete: a usable review skill, its installation and usage
guide, and two worked reviews. Improve them through use on further incidents.

The earlier `mock-cast-foundation` prototype is retained in the history of
[closed PR #8](https://github.com/HelixThinker/sre-cast/pull/8). Use
`sre-cast-review` for the current workflow. Earlier standalone infrastructure
tasks have been closed as not planned.

## Method sources

- [CAST Handbook](https://psas.scripts.mit.edu/home/get_file4.php?name=CAST_Handbook.pdf)
  — the primary reference for incident analysis.
- [MIT PSASS Books and Handbooks](https://psas.scripts.mit.edu/home/books-and-handbooks/)
  — official method publications.

Method references identify the relevant printed handbook pages. Cite incident
evidence alongside the analysis it supports.
