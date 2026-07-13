---
name: weekly-exec-brief
description: Synthesizes team updates, key metrics, and inbox highlights into one Monday-morning brief for your leadership team. Use at the start of the week when you have a pile of Slack threads, docs, and numbers to turn into a single readable brief.
---

# Weekly Exec Brief

## Purpose

Most leaders start the week by reading everything themselves — Slack, email, three different dashboards — before they can tell their team what matters. This skill does the first pass: feed it whatever you've collected (team update docs, Slack recaps, metric screenshots described in text, meeting notes) and it produces one brief your leadership team can read in two minutes.

## What to ask for if the input is incomplete

1. **The raw material** — team updates, metrics, notable emails or threads, anything gathered since the last brief
2. **The audience** — direct reports, full leadership team, or board-adjacent (this changes how much detail belongs in the brief)
3. **Anything time-sensitive** that must be flagged even if it's not the biggest story

If the raw material is thin in a section (for example, no metrics were provided), leave that section short rather than padding it — a brief that pads weak input teaches readers to skim past everything.

## Output format

```
# Week of [date] — Exec Brief

## Top 3 Things to Know
1. [Most important item — one sentence, plus one sentence of context]
2. [Second item]
3. [Third item]

## Metrics Snapshot
- [Metric]: [value] ([up/down/flat] vs. last week)
- (only include metrics actually provided — do not fabricate a standard set)

## Team Highlights
- [Team/person]: [what happened, in one line]
- (group by team if multiple updates came in)

## Risks & Blockers
- [Risk or blocker] — [who owns resolving it]
- (this section is allowed to be empty — say "Nothing blocking" rather
  than inventing a risk)

## This Week's Focus
- [Priority 1]
- [Priority 2]
- [Priority 3]
```

## Voice rules

- The "Top 3" section is the whole point — if a reader stops there, they should still know what matters. Write it last, after drafting the rest, so it's a true summary rather than a guess.
- One line per item wherever possible. This is a brief, not a report — link out to source docs instead of restating them in full.
- Flag risks in plain language ("we're going to miss the Q3 deadline unless X"), not euphemism ("some timeline pressure exists").
- Keep the leader's own phrasing for anything opinion-bearing — don't smooth a sharp assessment into something blander.

## Example

**Input (raw notes):** "eng shipped the new exception-routing engine, early customers already seeing 30% fewer manual escalations. sales had a slow week, two deals slipped to next month but pipeline's still healthy. support tickets spiked bc of a NetSuite connector outage tuesday, need to figure out if we need dedicated on-call for integrations. marketing's webinar on 'ending the manual reconciliation spreadsheet' pulled 420 signups. board meeting thursday, need the deck by wednesday eod."

**Output (excerpt):**

```
## Top 3 Things to Know
1. Exception-routing engine shipped — early customers already seeing
   30% fewer manual escalations.
2. Tuesday's NetSuite connector outage spiked support volume; we likely
   need dedicated on-call coverage for integrations.
3. Board deck due Wednesday EOD for Thursday's meeting.

## Metrics Snapshot
- Manual escalations: -30% for customers on the new routing engine
- Webinar signups: 420 ("Ending the Manual Reconciliation Spreadsheet")

## Risks & Blockers
- Integration outages have no dedicated on-call yet — owner: Eng lead,
  needs a staffing decision this week.
- Two deals slipped to next month — pipeline still healthy overall,
  watching for a pattern.
```
