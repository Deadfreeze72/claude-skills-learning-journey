---
name: decision-memo
description: Turns a decision you're weighing into a clear one-page memo — context, options, trade-offs, a recommendation, and next steps. Use when you need to think through a decision before committing to it, or explain one to your team, co-founder, or board.
---

# Decision Memo

## Purpose

Leaders make decisions all day, but rarely write them down in a form anyone else could follow. This skill takes your raw thinking — notes, a voice memo transcript, a rambling Slack message to yourself — and turns it into a one-page memo that makes the decision legible: what you're deciding, what you considered, what you're choosing, and why.

Use it before a decision (to pressure-test your own thinking) or after one (to explain it to people who weren't in the room).

## What to ask for if the input is incomplete

Before writing, make sure you have:

1. **The decision itself** — one sentence, framed as a question ("Should we... ")
2. **The options considered** — at least two, including "do nothing" if that's a real option
3. **The constraints** — budget, timeline, people, anything non-negotiable
4. **A recommendation** — the leader's gut read, even if it's rough

If any of these are missing from the input, ask for them directly rather than inventing them. A decision memo is only useful if the reasoning is real.

## Output format

Produce a single-page memo, no longer than ~400 words, using this exact structure:

```
# Decision: [one-line framing, as a question]

**Date:** [date] | **Owner:** [name] | **Decide by:** [deadline if given]

## Context
2-4 sentences on why this decision exists now. What triggered it.

## Options Considered
1. **[Option name]** — one line on what it is, one line on the catch
2. **[Option name]** — one line on what it is, one line on the catch
3. **[Option name]** — (repeat as needed; include "do nothing" if relevant)

## Trade-offs
A short paragraph or 3-4 bullets naming the real tension — cost vs. speed,
risk vs. upside, short-term pain vs. long-term fit. Say the quiet part.

## Recommendation
One or two sentences. State the choice plainly. No hedging language
("it depends," "we could go either way") — if the input is genuinely
split, say that explicitly and say what would resolve it.

## Next Steps
- [ ] Concrete action, owner, date
- [ ] Concrete action, owner, date
```

## Voice rules

- Write in the leader's own voice — first person, decisive, no corporate hedging.
- Cut throat-clearing. Open with the decision, not the backstory.
- One page. If it's running long, the options list is usually the place to trim.
- Never soften a recommendation to seem balanced. A memo that doesn't recommend anything isn't a decision memo — it's a list.

## Example

**Input (rough notes):** "keep going back and forth on whether we bring on a dedicated implementation engineer now or wait til the Meridian contract closes. our onboarding backlog is already six customers deep and growing, that's real revenue sitting unlaunched. but cash stays tight until Meridian signs, could be another month out. dani thinks we wait, I think every week we wait is another week of customers not live, and that's what actually kills renewals down the line, not the extra payroll."

**Output:**

```
# Decision: Hire a dedicated implementation engineer now, or wait until the Meridian contract closes?

**Date:** July 2026 | **Owner:** Tom | **Decide by:** End of week

## Context
Onboarding backlog is six customers deep and growing — real revenue
sitting unlaunched. Cash stays tight until Meridian signs, which could
be another month out.

## Options Considered
1. **Hire now** — clears the backlog immediately, but adds payroll
   before Meridian is confirmed.
2. **Wait for Meridian to close** — protects cash, but the backlog
   keeps growing and customers stay unlaunched even longer.

## Trade-offs
This is cash discipline vs. renewal risk. Dani's read protects the
runway; mine protects the relationships already six deep in a queue.
An unlaunched customer isn't a saved cost — it's a renewal we haven't
earned yet.

## Recommendation
Hire now. A growing backlog costs more in unrenewed contracts than
one month of early payroll costs in cash.

## Next Steps
- [ ] Approve req — Tom — today
- [ ] Loop in Dani on final call before offer goes out — Tom — this week
- [ ] Ops to triage the backlog by contract value — Ops — this week
```
