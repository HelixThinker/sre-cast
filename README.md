# SRE CAST

Incident review rules and a skill that turns evidence into an interactive map.

**[Visit the project site](https://helixthinker.github.io/sre-cast/)** ·
**[Explore the Cloudflare map](https://helixthinker.github.io/sre-cast/examples/cloudflare.html)**

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

You can also edit the map directly:

1. Select an arrow or relationship button, then choose **Edit relationship**.
2. Edit its label, evidence status, sources, finding, question, proposal, or check.
   **Add source** and **Remove source** change the evidence list. Keep private
   file paths in the locator and leave the URL blank.
3. Choose **Apply changes** to update the page, or **Cancel** to discard the draft.
   Adding evidence never changes its status automatically.
4. Choose **Save HTML** and keep the downloaded file. Open that copy to continue.
   The original file is not overwritten; closing the page before downloading
   loses changes. Browser download restrictions may require opening the map in a
   normal browser instead of an embedded preview.

Unrelated relationships and node positions are preserved. This editor changes
relationship content; it does not add nodes or rearrange the graph.

## Example

[Cloudflare, July 2, 2019](https://helixthinker.github.io/sre-cast/examples/cloudflare.html)
maps release control, resource contention, incident feedback, and emergency
response. Open the live map, or download [its HTML file](examples/cloudflare.html)
for offline use. The [project site](https://helixthinker.github.io/sre-cast/#example)
introduces the analysis and its concrete proposals.

## Themes and readability

**Auto · system** is the default and follows live changes to the operating
system's color preference. **Light** and **Dark** override it. The browser remembers
this choice when local storage is available; maps also work when storage is blocked.
Exported maps use the viewer's preference, not the author's resolved light/dark state.

The blue palette and theme behavior are adapted from
[tsastat](https://github.com/HelixThinker/tsastat/tree/640ff8c2206679ede87e6c9835e3a0903c6086b6/site).
Text uses a system font, generous line spacing, and restrained accents. Status
names and dashed lines carry meaning alongside color. Controls have visible
keyboard focus and at least 44 px height. The layout reflows; the diagram can
scroll horizontally without squeezing its labels. Long diagram labels are
abbreviated, with the full text retained in details and the editor.

Palette targets follow WCAG: [text contrast of at least 4.5:1](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum.html),
[essential graphical cues of at least 3:1](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast.html),
and [meaning conveyed beyond color](https://www.w3.org/WAI/WCAG22/Understanding/use-of-color.html).
These are design and contrast checks, not a claim of complete WCAG certification.
A palette cannot guarantee medical comfort: lighting, glare, and screen brightness
also matter ([American Optometric Association](https://www.aoa.org/aoa/documents/healthy%20eyes/digital_eyestrain.pdf)).
Choose the theme that suits your environment; the app adds no flashing or motion.

## Project site

GitHub Pages publishes `index.html` and the existing example directly from the
root of `main`. `.nojekyll` keeps publication static: no build tools, dependencies,
or custom workflow. Changes merged into `main` update the site automatically.
To preview locally, run `python3 -m http.server 8000` and open
`http://localhost:8000/`. The landing page and maps share the same theme preference.

The repository contains the site, one rules file, one skill, one HTML template,
and one worked map. Earlier prose reviews and guides remain in Git history.
Local books in `sources/` remain ignored.
