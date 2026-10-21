# CAST guide for an SRE review

This is an SRE adaptation of CAST, not a substitute for the full method.
Use it to explain interactions and select useful questions, not to require a
fixed report size.

## Loss, hazard, and constraint

A **loss** is an unacceptable outcome for stakeholders. Separate an observed
impact from a possible loss the review wants to prevent.

A **hazard** is a system state or set of conditions that, with relevant
environmental conditions, can lead to a loss. It is not simply a component
failure or a restatement of the trigger.

A **constraint** states behavior needed to control that hazardous condition.
Distinguish documented requirements from requirements proposed by the review.

Example framing: if expensive work can exhaust a shared serving pool, an
availability constraint could bound the work while preserving useful service.
The budget, measurement boundary, and behavior at the limit remain decisions
for the system's owners. This framing alone establishes no actual policy.

## Follow the control loop

A controller can be a person, team, policy process, or software component. It
acts on a controlled process and uses feedback to maintain an adequate model
of that process.

For a relevant action, consider whether it was missing, inappropriate in
context, too early or late, applied in the wrong order, or continued or stopped
at the wrong time. These are prompts for investigation, not mandatory labels
or proof that the action was unsafe.

Ask what the controller could observe and influence at the time. Separate a
signal existing somewhere from that signal reaching the decision maker in time
and in an actionable form. Consider authority, execution paths, dependencies,
coordination between controllers, and competing constraints.

Do not infer an engineer's beliefs from the incident outcome. A report may
establish that a check passed without establishing what anyone believed that
check guaranteed. Ask what the check covered and how its result was used.

Explain local actions in their operational and organizational context. Extend
the boundary only when an interaction matters to the loss or a decision.
Unknown staffing, incentives, or management priorities must stay unknown.

## From evidence to a useful next decision

A strong finding connects an observation to a control problem and states the
limit of that inference. It remains possible to identify a useful question
without declaring a cause.

For example, an account can establish that admission checks passed and a
change still caused resource exhaustion. This supports examining what the
admission decision established about resource use. It does not establish that
a reviewer was careless.

Prioritize a question when its answer could change an important proposal,
resolve competing explanations, or reveal whether intervention was feasible.
Request the smallest useful evidence: a decision record, a configuration
version, the timing of a signal, or an attributed explanation.

## Improvements and follow-up

Connect each action to a constraint, control action, feedback path, or model
assumption it is meant to improve. An action's completion and its effect are
different claims.

Describe observable behavior without inventing success thresholds: for
example, an authorized intervention remains executable under the relevant
degraded conditions and its result is visible to responders. Who agrees the
conditions and target remains a decision if the record does not say.

A proposed controller, safeguard, or feedback link is a design suggestion.
Label it accordingly and consider how it interacts with other objectives.
Do not present a single safeguard as guaranteed prevention.

## Method source

[CAST Handbook, Nancy Leveson](https://psas.scripts.mit.edu/home/get_file4.php?name=CAST_Handbook.pdf):

- Printed pages 9–10: losses, hazards, and system constraints.
- Printed pages 31–35: control, feedback, and iterative analysis.
- Printed page 56: controller responsibilities, process models, and context.
- Printed pages 90–91: responsibility, implementation, and effectiveness of
  improvements.

Page references identify the method basis. They do not support factual claims
about an incident. The workflow, question prioritization, and output shape in
this package are the project's adaptation.

