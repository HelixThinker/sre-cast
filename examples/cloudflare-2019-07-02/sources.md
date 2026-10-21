# Source notes

[Read the review](README.md).

Accessed October 21, 2026. These notes identify the passages used without copying
the articles. Source labels are local navigation aids for this example.

## Primary accounts

- **Detailed account:** [Cloudflare, July 12, 2019](https://blog.cloudflare.com/details-of-the-cloudflare-outage-on-july-2-2019/), by John Graham-Cumming.
- **Early account:** [Cloudflare, July 2, 2019, updated](https://blog.cloudflare.com/cloudflare-outage/), by John Graham-Cumming.

Both come from the operator. Agreement between them is not independent
corroboration. Internal dashboards, screenshots, and log descriptions in the
articles remain publisher-provided evidence. We did not inspect the underlying
logs, private tickets, or repositories.

## Passage guide

Each link below highlights a distinctive passage in the original article.
The section and subject also provide a locator if the browser does not support
text fragments.

### Execution mode

[Detailed account: deployment mode](https://blog.cloudflare.com/details-of-the-cloudflare-outage-on-july-2-2019/#:~:text=This%20particular%20change).
Locate the paragraph about simulation under the section describing operations.

### Admission

[Detailed account: test coverage](https://blog.cloudflare.com/details-of-the-cloudflare-outage-on-july-2-2019/#:~:text=What%20it%20didn%E2%80%99t%20do).
Locate the WAF-threat section's discussion of the test suite and its scope.

### Exposure

[Detailed account: deployment policy](https://blog.cloudflare.com/details-of-the-cloudflare-outage-on-july-2-2019/#:~:text=The%20SOP%20for).
Use the operational-policy paragraphs, the distribution section, and item 5 in
the retrospective list of weaknesses.

### Runtime

[Detailed account: removed protection](https://blog.cloudflare.com/details-of-the-cloudflare-outage-on-july-2-2019/#:~:text=A%20protection).
Use item 2 in the retrospective list of weaknesses, alongside the discussion of
the runtime engine in the distribution section.

### Recovery

[Detailed account: intervention obstacles](https://blog.cloudflare.com/details-of-the-cloudflare-outage-on-july-2-2019/#:~:text=But%20getting).
Use the chronological account between identification and intervention, and
items 6 and 9–11 in the retrospective list of weaknesses.

### Early account

[July 2 update](https://blog.cloudflare.com/cloudflare-outage/).
Use the evening update beginning at 20:09 UTC for impact, deployment, recovery,
and restoration. The earlier opening paragraph provides only an approximate
duration.

### Timeline precision

[Detailed chronology](https://blog.cloudflare.com/details-of-the-cloudflare-outage-on-july-2-2019/#:~:text=Eventually).
The later account places disable-command execution at 14:07 and traffic recovery
at 14:09. The early update compresses these events. Treat this as a precision
difference rather than silently replacing one statement or inventing a
contradiction. The review's milestone table keeps the shared recovery endpoint.

### Published actions

[Detailed account: follow-up measures](https://blog.cloudflare.com/details-of-the-cloudflare-outage-on-july-2-2019/#:~:text=Firstly).
Use the numbered list after the account of the failure mechanisms. Statuses
describe what the publisher reported then; they are not current verification.

## Why this incident was selected

We considered all three supplied reports:

| Candidate | Useful material in the public account | Selection judgment |
| --- | --- | --- |
| [GitLab, January 31, 2017](https://about.gitlab.com/blog/postmortem-of-database-outage-of-january-31/) | Database recovery, backup failures, and restoration choices | Strong future example for recoverability; broader recovery history would make the first review less compact. |
| [AWS US-EAST-1, December 7, 2021](https://aws.amazon.com/message/12721/) | Internal-network congestion, retries, and impaired operational visibility | Strong future example for dependency and feedback analysis, with a larger cross-service boundary. |
| [Cloudflare, July 2, 2019](https://blog.cloudflare.com/details-of-the-cloudflare-outage-on-july-2-2019/) | The passages indexed above | Selected for a bounded path from change admission to intervention, with explicit policy and follow-up material. |

The selection is our editorial judgment, not a ranking of incident severity or
postmortem quality. Neither alternative has been completed as an SRE CAST review.

## Evidence limits

The articles support a retrospective analysis of reported events. They do not
supply a complete organizational decision history, the original safeguard's
implementation, customer-specific losses, or independent evidence that all
announced follow-up measures were effective. No assumptions about current
Cloudflare practices are made.

For the analytical method, consult the
[CAST Handbook](https://psas.scripts.mit.edu/home/get_file4.php?name=CAST_Handbook.pdf);
the review lists printed page references separately from incident evidence.
