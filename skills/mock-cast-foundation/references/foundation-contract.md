# Foundation contract

This mock contract demonstrates how an AI-assisted CAST workflow can preserve
traceability. It is intentionally narrower than a complete CAST analysis.

## Classification labels

Use one of these exact labels for every substantive analytical statement:

- `[FACT]`: directly supported by cited evidence available to the analyst.
- `[INTERPRETATION]`: a reasoned reading of facts, with the reasoning visible.
- `[HYPOTHESIS]`: a plausible proposition that still requires evidence.
- `[UNKNOWN]`: information required for the analysis but not currently known.

Do not upgrade an interpretation or hypothesis to a fact through repetition.

## Stable identifiers

| Prefix | Entity | Minimum traceability |
| --- | --- | --- |
| `E-###` | Evidence item | Source and access state |
| `L-###` | Loss | Classification and evidence or question |
| `H-###` | Hazard | Related loss ID and evidence or question |
| `SC-###` | Safety constraint | Related hazard ID |
| `Q-###` | Open question | Gap, owner if known, and analytical impact |

IDs remain stable when wording changes. Retire an ID explicitly instead of
reusing it for a different entity.

## Foundation boundaries

The mock foundation may contain:

- losses relevant to the incident;
- the provisional system boundary and exclusions;
- hazards and safety constraints;
- a neutral event description;
- contradictions and open questions;
- traceability among the above artifacts.

It must not contain:

- completed controller analysis;
- claims about organizational or systemic causes not established by evidence;
- a single root-cause conclusion;
- corrective recommendations presented as validated CAST results.

## Evidence rules

- Cite evidence IDs beside facts.
- Record inaccessible or unavailable sources as such.
- Preserve conflicting evidence as separate entries.
- Use short paraphrases; do not copy large passages from source material.
- Treat AI-generated summaries as interpretations unless checked against the
  underlying source.

## Method reference

The project uses the official
[CAST Handbook](https://psas.scripts.mit.edu/home/get_file4.php?name=CAST_Handbook.pdf),
especially its discussion of the iterative analysis parts on printed pages
34–45. Page references identify the printed handbook page and may differ from a
PDF viewer's physical page index.
