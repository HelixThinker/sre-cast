# Worked Examples

This directory contains public worked examples of CAST applied to SRE incidents.
Examples are canonical analysis artifacts, not copies of website content.

## Example structure

```text
examples/
└── <incident-id>/
    ├── README.md
    ├── evidence/
    │   └── evidence-index.md
    ├── questions.md
    ├── analysis/
    │   ├── 01-foundation/
    │   ├── 02-control-structure/
    │   ├── 03-controller-analysis/
    │   ├── 04-systemic-factors/
    │   └── 05-improvement/
    ├── assets/
    └── report.md
```

The internal structure follows the five parts summarized in the
[CAST Handbook, pp. 34-35](https://psas.scripts.mit.edu/home/get_file4.php?name=CAST_Handbook.pdf#page=34):
foundational
information, the safety control structure, individual controller analysis,
system-wide flaws, and an improvement program.

Each example should:

- distinguish evidence, interpretation, hypothesis, and unknown information;
- preserve unanswered questions;
- link claims to public evidence;
- link method decisions to a book and page;
- avoid blame and single-root-cause explanations;
- trace each recommendation to a control-structure weakness;
- record ownership, implementation status, and effectiveness feedback.

The final requirement follows the continual-improvement guidance in the
[CAST Handbook, pp. 90-91](https://psas.scripts.mit.edu/home/get_file4.php?name=CAST_Handbook.pdf#page=90).
