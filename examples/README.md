# Worked reviews

Each example contains a readable review and links to the public evidence it
uses. Findings distinguish the operator's account, our interpretation, unanswered
questions, and proposed improvements.

## Available

- [Cloudflare WAF outage — July 2, 2019](cloudflare-2019-07-02/README.md):
  the first worked postmortem review, covering rule admission, runtime
  containment, deployment exposure, and emergency intervention.
  [Source notes](cloudflare-2019-07-02/sources.md) include passage locations and
  the rationale for selecting this case.
- [Facebook backbone outage — October 4, 2021](facebook-2021-10-04/README.md):
  a review with incomplete evidence, focusing on command admission, reachability,
  and authorized recovery. Questions drive the choice of improvements, and a
  continuation example explains how real new evidence would change the review.
  [Source notes](facebook-2021-10-04/sources.md) distinguish the operator's
  explanation from external BGP and DNS observations.

## Use the examples

Use the [review skill and quickstart](../skills/sre-cast-review/README.md) for
your own incident. Cloudflare demonstrates a detailed review; Facebook shows
how unresolved questions can be the main useful result. Neither example is a
claim of a complete internal investigation.

The example format can evolve through use. Keep sources close to conclusions
and retain the questions that available evidence cannot answer.
