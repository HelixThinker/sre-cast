# AI Skills

This directory contains portable Agent Skills for CAST-based SRE incident
analysis. Each skill is an executable workflow rather than a product-specific
prompt.

## Compatibility contract

The canonical package follows the
[Agent Skills specification](https://agentskills.io/specification) and targets
ChatGPT/Codex, Claude, and Cursor. Product-specific metadata may supplement a
skill but must not duplicate or change its core workflow.

Every skill must:

- keep its canonical instructions in `SKILL.md`;
- use only `name` and `description` in the portable frontmatter;
- use product-neutral capability language in its instructions;
- state missing runtime capabilities instead of silently skipping required work;
- keep detailed method material in `references/` and output resources in
  `assets/`;
- preserve uncertainty, open questions, and human review boundaries.

## Package structure

```text
skills/
└── <skill-name>/
    ├── SKILL.md        # Portable workflow and trigger metadata
    ├── agents/         # Optional product-specific UI metadata
    ├── references/     # Focused method references loaded on demand
    ├── assets/         # Templates and other output resources
    └── evals/          # Trigger prompts, quality assertions, and fixtures
```

Project-wide templates belong in [`templates/`](../templates/README.md). Complete
incident analyses belong in [`examples/`](../examples/README.md).

## Mock skill

[`mock-cast-foundation`](mock-cast-foundation/SKILL.md) demonstrates the complete
package contract. It produces a provisional foundational artifact from a bundled
Markdown template and deliberately stops before controller analysis and
recommendations.

The mock is not a completed CAST implementation. It is a test fixture for the
repository architecture and a starting point for the first production skill.

## Installation targets

Keep `skills/<skill-name>/` as the canonical package. Install or link that folder
into the discovery location used by the target product:

| Product | Project-level location or delivery |
| --- | --- |
| ChatGPT/Codex | `.agents/skills/<skill-name>/`; package as an OpenAI plugin for broader distribution |
| Claude Code | `.claude/skills/<skill-name>/`; upload the skill folder as a ZIP to claude.ai |
| Cursor | `.agents/skills/<skill-name>/` or import the repository |

Do not maintain copied product-specific instruction bodies. Product adapters may
provide metadata or installation packaging while `SKILL.md` remains canonical.
