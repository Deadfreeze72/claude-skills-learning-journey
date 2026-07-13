---
name: meeting-debrief-actions
description: Turns a raw meeting transcript or messy notes into decisions made, clear owners and deadlines, and a drafted follow-up message. Use right after a meeting when you have a transcript or notes and need to capture what was decided and who is doing what.
---

# Meeting Debrief & Actions

## Purpose

The value of a meeting evaporates the moment everyone closes the tab, unless someone captures what was actually decided. This skill takes a raw transcript or rough notes and produces the artifact that should exist after every meeting: decisions made, owners, deadlines, and a follow-up message ready to send.

## What to ask for if the input is incomplete

1. **The transcript or notes** — doesn't need to be clean; this skill is built for messy input
2. **Who was in the room** — needed to assign owners accurately
3. **Anything explicitly deferred** — decisions the meeting punted on should be captured as open questions, not dropped

If the transcript doesn't make an owner clear for an action item, mark it **[owner unclear — confirm]** rather than guessing. A wrong owner is worse than a flagged gap.

## Output format

```
# Meeting Debrief — [meeting name/topic] — [date]

## Decisions Made
- [Decision, stated as a completed fact] — [who decided / who was aligned]

## Action Items
| Action | Owner | Deadline |
|---|---|---|
| ... | ... | ... |

## Open Questions
- [Anything raised but not resolved, so it doesn't get lost]

## Suggested Follow-up Message
[A ready-to-send recap, 3-6 sentences, in the leader's voice, suitable
for Slack or email to the meeting's attendees. Leads with decisions,
then actions, then a close.]
```

## Voice rules

- Decisions are written as facts ("We will launch on the 15th"), not summaries of discussion ("There was a discussion about launch timing").
- Every action item needs an owner and a deadline. If the meeting didn't produce one, that's a gap worth surfacing, not smoothing over.
- The follow-up message should sound like something the leader would actually send — direct, warm, no corporate throat-clearing ("Per our discussion...").
- If the meeting revisited a decision from a prior meeting, note the change explicitly rather than only recording the latest state.

## Example

**Input (transcript excerpt):** "...ok I think we're aligned on pushing the Meridian go-live to the 15th, that gives their ops team the extra week to finish mapping their SKUs. Priya can you own the updated rollout timeline doc? ...yeah I'll have it out by Friday. On the overage pricing for extra automations we're still not aligned, Marcus wants to test a usage-based tier and I'm not sold yet, let's revisit next week. Also someone needs to loop in Meridian's ops lead so she's not blindsided by the new date..."

**Output (excerpt):**

```
## Decisions Made
- Meridian go-live moved to the 15th, giving their ops team the extra
  week to finish SKU mapping — aligned by full team on the call.

## Action Items
| Action | Owner | Deadline |
|---|---|---|
| Publish updated rollout timeline doc | Priya | Friday |
| Loop in Meridian's ops lead on the new go-live date | [owner unclear — confirm] | ASAP |

## Open Questions
- Usage-based pricing for overage automations (Marcus's proposal) — not
  resolved, revisit next week's meeting.

## Suggested Follow-up Message
Quick recap from today: Meridian's go-live is moving to the 15th to
give their ops team the extra runway to finish SKU mapping. Priya's
getting the updated rollout timeline out by Friday. Usage-based pricing
for overage automations is still open — we'll pick that back up next
week. One thing we need to nail down fast: who's looping in Meridian's
ops lead so she's not blindsided by the new date. Let me know if that's
you, otherwise I'll assign it today.
```
