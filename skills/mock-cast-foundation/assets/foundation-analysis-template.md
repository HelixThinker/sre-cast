# CAST Foundation Analysis

## Analysis Status

- Status: `mock-draft`
- Skill: `mock-cast-foundation`
- Incident: {{incident-name}}
- Evidence coverage: {{complete-or-partial}}
- Human review: required
- Scope note: This demonstration draft does not complete CAST.

## Source Inventory

| Evidence ID | Source | Access state | Relevance |
| --- | --- | --- | --- |
| E-001 | {{source}} | {{available-or-unavailable}} | {{relevance}} |

## Losses

### L-001

- Statement: {{classification-label}} {{loss}}
- Evidence or gap: {{evidence-ids-or-question-id}}

## System Boundary

- Included: {{classification-label}} {{included-systems-and-actors}}
- Excluded: {{classification-label}} {{explicit-exclusions}}
- Time window: {{classification-label}} {{time-window}}
- Boundary gaps: {{question-ids-or-none}}

## Hazards

### H-001

- Statement: {{classification-label}} {{hazardous-system-state}}
- Related loss: L-001
- Evidence or gap: {{evidence-ids-or-question-id}}

## Safety Constraints

### SC-001

- Statement: {{classification-label}} {{constraint}}
- Addresses hazard: H-001

## Neutral Event Description

{{classification-labeled-event-sequence-with-evidence-ids}}

## Open Questions

### Q-001

- Gap: [UNKNOWN] {{missing-information}}
- Why it matters: {{analytical-impact}}
- Owner: {{owner-or-unknown}}
- Status: `open`

## Traceability

| From | Relationship | To |
| --- | --- | --- |
| E-001 | supports | L-001 |
| H-001 | may lead to | L-001 |
| SC-001 | constrains | H-001 |
| Q-001 | exposes gap in | H-001 |

## Human Review

- Confirmed by: `unreviewed`
- Material disagreements: {{disagreements-or-none}}
- Highest-impact open questions: {{question-ids}}
