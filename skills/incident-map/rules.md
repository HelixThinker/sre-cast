# Incident review rules

Use these with or without a skill. The output should help someone decide what
to change or investigate next.

1. **State the loss and the boundary.** Say who was affected, what capability
   was lost, which part of the system is being examined, and which evidence and
   dates the review covers. Distinguish service recovery from full restoration.
2. **Explain the mechanism and recovery.** Connect decisions, actions,
   constraints, dependencies, and feedback to the outcome. Explain why actions
   made sense with the information and pressures available. Include what helped
   recovery and what obstructed it. Do not end at a faulty component or blame a
   person; do not invent their beliefs or organizational causes.
3. **Keep evidence attached.** Link significant claims to a source and a
   findable passage, timestamp, or log entry. Separate what a source reports from
   interpretation, hypothesis, and unknowns. An undocumented control is not an
   absent control. Several accounts from one organization are not independent
   confirmation. Preserve contradictions that the evidence cannot resolve.
4. **Make proposals concrete.** Tie each proposal to an identified weakness:
   what behavior changes, what observable result would show improvement, and
   which prerequisites or tradeoffs matter. Separate our proposals from the
   incident team's actions and date their reported status. Announced or completed
   work is not proof of effectiveness. Leave owners and thresholds unknown when
   the evidence does not establish them.
5. **Ask questions that change a decision.** Prioritize the missing evidence
   that would change a finding or next action. Say where it could be obtained and
   what different answers would imply. Do not pad the review with generic requests
   for more information.
6. **Draw a useful control map.** Show who or what controls a process, the
   actions it can take, and the feedback it receives. Label arrows with meaning
   and direction; distinguish supporting dependencies from control actions.
   Mark inferred, hypothetical, unknown, and proposed relationships explicitly
   on the map, not only in footnotes. Keep the map legible and consistent with
   the findings. A partial, honest map is better than invented completeness.

These are practical adaptations informed by Nancy Leveson's
[CAST Handbook](https://psas.scripts.mit.edu/home/get_file4.php?name=CAST_Handbook.pdf),
especially printed pages 9–10, 31–35, 56, and 90–91. They are not a substitute for
a full CAST investigation or access to incident participants.
