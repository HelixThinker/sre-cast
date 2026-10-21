# SRE CAST

Incident review rules and a skill that turns evidence into an interactive map.

The rules explain what matters in a review. The skill makes a usable artifact:
select a relationship to inspect its evidence, uncertainty, finding, and proposed
change. Its value is keeping these together as the incident becomes clearer.
We do not claim that a skill makes the model a better incident analyst.

## Use

Read [the review rules](skills/incident-map/rules.md) on their own, or give an
agent [the incident-map skill](skills/incident-map/SKILL.md) and incident material:

> Use skills/incident-map/SKILL.md to map this incident: [report URL or file].
> Save the interactive map as incident.html. Mark unknown relationships and
> show which evidence would change the next decision.

The whole `skills/incident-map/` folder is the skill package. Its template and
rules travel with it. The output is one HTML file: open it in a browser, select
an arrow or relationship button, and follow the evidence links. No build,
server, account, or internet connection is needed to use the map; opening its
external sources needs internet. This is a local HTML artifact, not a native
Canvas integration.

To continue an existing map:

> Use the incident-map skill to update incident.html with this new evidence:
> [material]. Revise the affected relationship, finding, and proposal. Preserve
> the remaining unknowns and show me what changed.

The agent updates the saved file. Editing and saving directly in the map is the
next step; the current UI supports inspection only.

## Example and next step

[Cloudflare, July 2, 2019](examples/cloudflare.html) maps release control,
resource contention, incident feedback, and emergency response. Download/open
the HTML file to interact with it; GitHub displays its source.

The next task is to **edit one relationship and save the updated map**, preserving
its evidence and uncertainty. See [#15](https://github.com/HelixThinker/sre-cast/issues/15).

The repository contains one rules file, one skill, one HTML template, and one
worked map. Earlier prose reviews and guides remain in Git history. Local books
in `sources/` remain ignored.
