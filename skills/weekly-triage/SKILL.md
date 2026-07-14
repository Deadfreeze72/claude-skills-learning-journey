---
name: weekly-triage
description: Generates the user's weekly email triage brief. ALWAYS trigger when the user types the exact command "/weekly-triage", or close variants like "weekly triage", "run my weekly triage", "do my weekly triage". Produces a single one-page markdown brief covering three things from the past week's Gmail: missed business opportunities, other buried important emails needing a reply, and people the user is still waiting to hear back from (7+ days, no response). Every flagged item gets a one-line "why it matters" and a drafted reply the user can copy and send themselves — this skill never sends email or creates Gmail drafts on its own. Do not use for general one-off email questions or unrelated inbox searches outside the explicit /weekly-triage trigger.
---

# Weekly Triage

Produces a single, scannable, one-page brief of the past week's email — the things that would otherwise slip through the cracks. Runs on Gmail (call `tool_search` for "gmail" first if the tools aren't already loaded).

**Why this exists:** most of what actually matters in a busy inbox — a new prospect, a partner who's still waiting to hear back, a client question buried under newsletters — doesn't announce itself. This skill's whole job is to surface those things once a week so nothing important goes cold.

## Hard rule: never send or draft in Gmail

This skill only ever writes to the brief document. It never calls `create_draft`, `send`, or any Gmail write action, even though it's producing "drafted replies." Every drafted reply in the brief is text inside a markdown file for the user to read, edit, and send themselves. If this expectation ever changes, the user will say so explicitly — don't infer it from context.

## Step 1: Gather the raw material

Don't run two separate directional searches (inbox vs. sent) and treat them independently — a thread where the user sent something 12 days ago that got a same-day reply he never saw will fall through the cracks of a pure "last 7 days" inbox scan, because the unanswered inbound message is now older than 7 days. The reliable approach:

1. Pull every thread the user has touched in roughly the last 30–45 days — both `in:inbox newer_than:45d` and `in:sent newer_than:45d`, excluding promotions/updates/social/forums categories. Gmail's date operators aren't perfectly precise, so don't fully trust the query filter — check the actual message dates in what comes back.
2. For each unique thread, find the chronologically **last** message and who sent it. That single fact determines everything:
   - **Last message is from the user** → a candidate for *waiting on a response*, if 7+ days have passed since they sent it.
   - **Last message is inbound (not from the user)** → the user owes a reply. Candidate for *missed opportunity* or *buried important email* (see Step 2), regardless of whether that inbound message arrived 2 days ago or 3 weeks ago — if it's still sitting unanswered, it's still relevant.
3. Exclude, on sight, regardless of which bucket it might otherwise fall into: automated notifications (deploy alerts, build failures, magic-link sign-ins, calendar auto-notices), receipts and invoices, newsletters, and threads that are actually resolved (a "thanks!"/"sounds good" that doesn't need a reply, a meeting that's simply confirmed on the calendar). Also exclude anything personal or sensitive — a family or health matter mixed into an otherwise-professional thread doesn't belong in a business triage brief even if it happens to be the most recent message.
4. Put an upper bound on staleness for the waiting-on-response bucket: past ~45 days with no response, treat it as a cold lead rather than something to keep resurfacing weekly, unless the user says otherwise.

## Step 2: Sort what's left into three buckets

For each inbound-unanswered candidate, decide:

- **Missed opportunity** — a new or unfamiliar sender, or a familiar one raising something new: interest in working together, a partnership or referral, a request for a proposal or a call, an introduction to someone new, a speaking/press/investor inquiry, momentum on an existing deal that needs one more push to close. The signal is *this could turn into something if picked up in time*. Watch direction carefully: a vendor cold-pitching the user their own product or service is not an opportunity for the user's business — it's noise, even when it's well-written and personalized.
- **Buried important email** — doesn't fit "opportunity," but still clearly needed a reply and didn't get one: a direct question from a colleague or client, a decision someone's waiting on, a formal notice (contract, termination, legal), anything with an implicit or explicit deadline.

If a thread doesn't reasonably fit either bucket (a newsletter that slipped past the filter, a pure FYI, something the user is deliberately letting sit), leave it out. When genuinely torn between the two labels, pick whichever better explains *why it's worth the user's time* — the label matters less than making sure real signal doesn't get dropped.

Every last-message-from-the-user candidate (7+ days, within the staleness bound) goes in the third bucket:

- **Waiting on a response** — the user reached out, 7+ days have passed, still nothing back. This can include internal teammates, not just outside contacts — flag both, since either can genuinely stall.

## Step 3: Rank and cap

Cap each bucket at 3 items — the highest-signal ones. Rank by a mix of: how recent, how explicit the ask, how high-stakes the relationship or deal looks, and (for the waiting-on-response bucket) how long it's been sitting balanced against how many times it's already been followed up on without a response (a fourth ping on a lead that's ignored the last three isn't high-signal). If a bucket has fewer than 3 real candidates, show what's there — don't pad it to hit the number. If a bucket is empty, say so plainly rather than dropping the section.

## Step 4: Write the brief

Use this exact structure:

```markdown
# Weekly Triage — [Month Day–Day, Year]

## 🎯 Missed Opportunities

### [N]. [Sender/Company] — [Subject line]
**Why it matters:** [one sentence — what makes this worth acting on]
**Suggested reply:**
> [2–4 sentence draft, direct and professional — ready to copy, tweak, and send]

*(repeat, up to 3; if none: "Nothing landed this week that looks like a new opportunity.")*

## 📥 Buried Important Emails

*(same structure as above)*

## ⏳ Waiting on a Response

### [N]. [Recipient] — [Subject line] — sent [X] days ago
**Why it matters:** [one sentence — what's riding on this, or why the silence is notable]
**Suggested follow-up:**
> [short, low-pressure nudge — 1–3 sentences]

*(repeat, up to 3; if none: "Everyone you've reached out to this week has gotten back to you.")*
```

Keep the whole thing to one page — this is a Monday-morning read, not a report. Drafted replies and follow-ups should sound like a direct, busy founder wrote them: short, no throat-clearing, no corporate padding.

## Step 5: Save and deliver

Save the brief as `weekly-triage-[YYYY-MM-DD].md` (today's date) to the outputs directory and present it as a file, not just pasted into the chat — the point is a document the user can hold onto and revisit.

## A note on judgment calls

This skill leans on real judgment — is this an opportunity, has enough time really passed, is this reply-worthy — more than on rigid rules. When genuinely torn, err toward flagging rather than silently dropping something: a false positive costs the user five seconds of skimming, a missed real opportunity costs more. The user's corrections over time (via feedback on the brief) are the best signal for recalibrating where that line should sit.
