# Source notes

[Read the review](README.md).

Accessed October 21, 2026. This review uses the three articles below as currently
available. It does not claim access to a complete internal postmortem, logs,
interviews, or later implementation evidence.

## Source boundary

| Source | Publication and version | Use in this review |
| --- | --- | --- |
| [Facebook: initial update](https://engineering.fb.com/2021/10/04/networking-traffic/outage/) | October 4, 2021; page identifies an October 5 update | Operator's impact account |
| [Facebook: additional details](https://engineering.fb.com/2021/10/05/networking-traffic/outage-details/) | October 5, 2021 | Operator's explanation and follow-up intentions |
| [Cloudflare: external observations](https://blog.cloudflare.com/october-2021-facebook-outage/) | October 4, 2021; current page includes subsequent updates without a separate timestamp for each | Published BGP and DNS observations |

The two Facebook pages are one organization's accounts, not independent
corroboration. Cloudflare's own observations have a separate vantage point.
Its retelling of Facebook's internal explanation does not independently verify
that explanation. We read the articles, not the underlying telemetry.

This is a boundary on the evidence used, not a claim that no additional public
material exists. No present-day architecture or completion status is inferred.

## Passage locations

Links use text fragments for convenience. The accompanying subjects locate
the same material if a browser does not support them.

### Initial account

[Opening account and updated impact statement](https://engineering.fb.com/2021/10/04/networking-traffic/outage/#:~:text=Our%20engineering%20teams).
Use the opening three paragraphs, including the explicit update note.

### Maintenance and audit

[Maintenance paragraph](https://engineering.fb.com/2021/10/05/networking-traffic/outage-details/#:~:text=During%20one%20of%20these).
Use the paragraph following the description of router maintenance.

### Reachability

[DNS/BGP explanation](https://engineering.fb.com/2021/10/05/networking-traffic/outage-details/#:~:text=To%20ensure%20reliable%20operation).
Use the middle paragraphs about health and advertisements.

### Intervention

[Access and onsite intervention](https://engineering.fb.com/2021/10/05/networking-traffic/outage-details/#:~:text=Our%20primary%20and%20out-of-band).
Use the access paragraphs and the later discussion of the security tradeoff.

### Follow-up

[Restoration and future work](https://engineering.fb.com/2021/10/05/networking-traffic/outage-details/#:~:text=Once%20our%20backbone).
Use the final restoration, exercises, review, and resilience paragraphs.

### External observations

[Cloudflare's routing observations](https://blog.cloudflare.com/october-2021-facebook-outage/#:~:text=At%2015%3A58).
Use the routing section's observations and route-table examples, then the DNS
section's resolver results. Retained routes for other addresses prevent a
claim that every Facebook prefix disappeared.

### External recovery

[Cloudflare's concluding update](https://blog.cloudflare.com/october-2021-facebook-outage/#:~:text=At%20around%2021%3A00).
Use the final update for BGP activity and resolver availability. These
measurements do not establish end-to-end restoration for every user.

## Why this is an incomplete-evidence example

The material identifies useful subjects for investigation without supplying
the records needed to select a precise corrective design. The review therefore
keeps command semantics, admission conditions, access dependencies, decision
signals, responsibility, and effectiveness as questions.

The incompleteness is natural to these public accounts; we have not removed
known answers to create a test. Neither the earlier project example nor this
one is a benchmark. Their purpose is to show what a useful review can produce
within its actual evidence boundary.
