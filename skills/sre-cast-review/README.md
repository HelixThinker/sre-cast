# Use SRE CAST Review

Give the skill a postmortem and the evidence available to you. It returns a
review of supported conclusions, control and feedback gaps, prioritized
questions, and improvement proposals. It works with partial reports and can
continue when new answers arrive.

The skill uses the language you request. No scripts, API keys, or additional
runtime dependencies are required by the package. Reading a URL requires the
host's browsing capability; pasted text and local files can be reviewed without
web access.

## Install in Codex

Clone this repository, or use your existing checkout:

```sh
git clone https://github.com/HelixThinker/sre-cast.git
cd sre-cast
```

From the repository root, link the complete skill folder into your personal
skills directory on macOS or Linux:

```sh
mkdir -p "$HOME/.agents/skills"
ln -s "$PWD/skills/sre-cast-review" "$HOME/.agents/skills/"
```

Keep the checkout at that path. If a skill with this name is already installed,
use that installation or deliberately replace its link instead of creating a
second copy. A linked installation picks up changes when you update the
checkout.

For a single-project installation, use that project's
`.agents/skills/` directory instead of `$HOME/.agents/skills/`. Alternatively,
copy the whole `sre-cast-review` folder there, including `references/`,
`assets/`, and `agents/`; copying only `SKILL.md` leaves out resources it uses.
Choose one location to avoid duplicate entries.

Codex detects new skills and changes automatically. If the skill does not
appear, restart Codex. In the CLI or IDE extension, use `/skills` or type `$`
to select it. These discovery locations and behaviors are described in the
[official skills documentation](https://developers.openai.com/codex/skills).
This quickstart covers local Codex installation; it does not claim tested
compatibility with other hosts.

## First run: a public postmortem

After installation, send:

```text
$sre-cast-review
Review this public postmortem:
https://blog.cloudflare.com/details-of-the-cloudflare-outage-on-july-2-2019/

Use this source only. Keep the review concise and distinguish the author's
observations from your interpretation. Give me the three most useful questions
for an incident discussion, explain which decisions their answers would change,
and connect improvement proposals to the evidence. Do not assume that announced
follow-up work was completed or effective.
```

You should receive a review with source passages, control relationships,
unanswered questions, and proposals identified as suggestions. For this case,
a useful interpretation is that admission evidence, production exposure, and
emergency intervention need to be considered together. For example:

- **Reported observation:** functional checks passed, but the test suite did
  not cover runaway CPU consumption. See the postmortem's
  [test-coverage passage](https://blog.cloudflare.com/details-of-the-cloudflare-outage-on-july-2-2019/#:~:text=What%20it%20didn%E2%80%99t%20do).
- **Interpretation:** a successful admission result did not establish an
  adequate resource bound. This does not establish what a reviewer believed.
- **Open question:** what resource ceiling was intended, where was it enforced,
  and what happened at the limit? The answer changes whether a proposal should
  address per-rule work, aggregate request work, or both.
- **Proposal:** define the containment behavior and observe whether expensive
  evaluation stays within the agreed bound while useful service remains
  available. The owner, limit, and security behavior at exhaustion remain
  decisions; this is not a team commitment or proof of prevention.

The [full worked review](https://github.com/HelixThinker/sre-cast/blob/main/examples/cloudflare-2019-07-02/README.md)
uses both the detailed postmortem and the early incident update. Its
[source notes](https://github.com/HelixThinker/sre-cast/blob/main/examples/cloudflare-2019-07-02/sources.md)
explain the evidence boundary. It is a reference for depth and reasoning, not
an exact output to reproduce or a claim of an internal investigation.

## Review with incomplete evidence

The [Facebook 2021 review](https://github.com/HelixThinker/sre-cast/blob/main/examples/facebook-2021-10-04/README.md)
is the second worked example. Use it when you want to see how open questions
guide improvement decisions without filling missing details with assumptions.
Its [source notes](https://github.com/HelixThinker/sre-cast/blob/main/examples/facebook-2021-10-04/sources.md)
separate operator accounts from an external observer's own measurements.

To review the same material, send:

```text
$sre-cast-review
Review the Facebook outage of October 4, 2021 using these three public sources:
https://engineering.fb.com/2021/10/04/networking-traffic/outage/
https://engineering.fb.com/2021/10/05/networking-traffic/outage-details/
https://blog.cloudflare.com/october-2021-facebook-outage/

Focus on command admission, reachability, and authorized recovery. Distinguish
the operator's claims from independently observed external symptoms; a source
repeating another source's explanation is not independent corroboration.
Make decision-changing questions the main result. Keep missing command details,
dependencies, owners, and effectiveness evidence unknown. Relate proposals to
the evidence needed to choose them, and explain how to continue the review.
```

A useful result can leave the implementation choice unresolved. For example,
requesting the operation record and validation result can distinguish the need
to change an admission rule from the need to repair its implementation. A new
approval step should not be presented as the answer before that distinction is
understood. These are analytical possibilities, not additional incident facts.

When actual new evidence becomes available, provide it alongside the saved
review and ask which questions it answers, which control relationships change,
and which proposals should be revised or withdrawn. The published example
includes a clearly labeled hypothetical update rule, not invented participant
testimony.

## Review your own incident

Provide paths the assistant can read, attach files, or paste the text. Identify
which sources are in scope and whether you want a saved artifact. For example,
replace these illustrative paths with yours:

```text
$sre-cast-review
Review incidents/payment-timeout/postmortem.md using the timeline and
deployment notes in that same directory. Use only those files.
Write the review in Russian to incidents/payment-timeout/review.md.
Focus on the rollback decision and whether the existing action items address
it. Keep missing evidence explicit and prioritize questions for the discussion.
```

A short report is enough to begin. If all you know is "a configuration change
caused errors; we plan to add review," paste that statement and ask for the
next useful questions. The skill should identify what is unknown about
admission, exposure, feedback, or recovery as relevant; it should not assert
which of those controls failed without evidence.

## Continue the same review

Keep the earlier review in the conversation or provide its saved file:

```text
$sre-cast-review
Continue incidents/payment-timeout/review.md with these new notes:
The incident commander recalls that the rollback alert arrived only after
full rollout. The deployment event times have not yet been retrieved.

Treat this as an attributed recollection, not independent confirmation.
Update the affected findings and proposals, show which questions are now
partly answered, and identify what evidence would resolve the remaining gap.
```

The result should explain the changes and retain unanswered questions and
conflicting accounts. Source-reported or agreed actions remain distinct from
new suggestions. Reviewing an incident does not itself publish the result,
contact participants, assign owners, or change production.

## Package

- [SKILL.md](SKILL.md): invocation scope and review workflow.
- [Review guide](references/review-guide.md): focused CAST method notes.
- [Output template](assets/review-template.md): optional writing scaffold.
- [Codex metadata](agents/openai.yaml): display name and starter prompt.

The package is self-contained. The published Cloudflare and Facebook examples
provide context but are not required at runtime.

