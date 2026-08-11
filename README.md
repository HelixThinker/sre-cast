# SRE CAST

An open toolkit for applying CAST (Causal Analysis based on System Theory) to
SRE incidents with AI assistance.

The project will provide reusable AI rules, guided analysis skills, templates,
worked examples, and a public website. It is not limited to storing individual
postmortems.

CAST is an analysis method rather than an incident investigation technique. It
helps analysts determine which questions still need answers and why the existing
control structure did not prevent a loss. See the
[CAST Handbook, pp. 34-35](https://psas.scripts.mit.edu/home/get_file4.php?name=CAST_Handbook.pdf#page=34).

## Project goals

- Make systems-based incident analysis accessible to SRE teams.
- Provide reusable rules that improve the quality and integrity of AI-assisted
  analysis.
- Provide AI skills that guide people through CAST without turning it into a
  rigid checklist.
- Publish worked examples that show both the analysis process and its outputs.
- Present the method, skills, and examples through GitHub Pages.
- Keep every method-related recommendation traceable to the source books.

The workflows must remain iterative. The five parts of CAST are not rigid,
linear steps, and an analysis should revisit earlier results when new evidence
appears. See the
[CAST Handbook, p. 35](https://psas.scripts.mit.edu/home/get_file4.php?name=CAST_Handbook.pdf#page=35).

## Repository structure

```text
.
├── README.md
├── rules/            # Portable rules for AI-assisted CAST analysis
├── skills/           # Reusable AI workflows and supporting resources
├── templates/        # Shared, tool-independent analysis templates
├── examples/         # Worked CAST cases and their evidence
└── docs/             # GitHub Pages source
```

Possible automation and validation tools will be added only when a concrete
workflow requires them.

## Method references

The project is based on the official handbooks published by the MIT Partnership
for Systems Approaches to Safety and Security:

- [CAST Handbook](https://psas.scripts.mit.edu/home/get_file4.php?name=CAST_Handbook.pdf)
- [STPA Handbook](https://psas.scripts.mit.edu/home/get_file.php?name=STPA_handbook.pdf)
- [MIT PSASS Books and Handbooks](https://psas.scripts.mit.edu/home/books-and-handbooks/)

Methodological claims in rules, skills, templates, examples, and documentation
must link to an official publication and the relevant page.

### `rules/`

Contains short, portable instructions that can be added to an AI assistant's
project rules or system prompt. Rules define non-negotiable analysis properties,
such as evidence handling, uncertainty labeling, blameless language, terminology,
and source citation.

The no-blame rule follows CAST's explanatory approach: describe what happened
and why it made sense in context instead of stopping at a person or component
"failure." See the
[CAST Handbook, pp. 19-23](https://psas.scripts.mit.edu/home/get_file4.php?name=CAST_Handbook.pdf#page=19).

See [`rules/`](rules/README.md).

### `skills/`

Contains complete AI-assisted workflows. A skill may guide a user through one
part of CAST or orchestrate an end-to-end analysis. Skills may include their own
references, templates, validation scripts, and small usage examples.

A skill must generate and track open questions instead of inventing missing
facts. CAST uses these questions to guide evidence collection and deepen the
causal explanation. See the
[CAST Handbook, p. 35](https://psas.scripts.mit.edu/home/get_file4.php?name=CAST_Handbook.pdf#page=35).

See [`skills/`](skills/README.md).

### `templates/`

Contains shared Markdown and diagram templates used by skills and examples.
Templates provide structure without pretending that CAST is a fixed recipe.

See [`templates/`](templates/README.md).

### `examples/`

Contains worked CAST analyses. Each example keeps evidence, open questions,
analysis artifacts, diagrams, recommendations, follow-up, and the final report
together. Examples are the canonical source material that will later be rendered
for the website.

See [`examples/`](examples/README.md).

### `docs/`

Contains the GitHub Pages source. The site will explain the method, publish the
available rules and skills, and present worked examples in a readable visual
form. The website must consume or link to canonical content from `examples/`
rather than create a second independent analysis.

Hyperlinks are especially appropriate for CAST because the final representation
should preserve relationships among evidence, questions, controllers, causal
factors, and recommendations. See the
[CAST Handbook, p. 92](https://psas.scripts.mit.edu/home/get_file4.php?name=CAST_Handbook.pdf#page=92).

See [`docs/`](docs/index.md).

## Development sequence

1. Define the first portable AI rules.
2. Create the first focused CAST skill and its templates.
3. Apply the skill to one public SRE incident and publish it under `examples/`.
4. Build the GitHub Pages presentation around the real example.
5. Add validation and automation only after the manual workflow is understood.

## Current status

The repository structure and responsibilities are defined. Rules, skills,
templates, examples, and the website will be implemented incrementally.
