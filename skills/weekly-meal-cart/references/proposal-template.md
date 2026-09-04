# Template: the weekly proposal, and the week file

## The proposal

This is what the household actually reads. It has one job: make picking dinner take under
two minutes.

Chronological order, always. The near days first, so they confirm what is imminent before
they see the whole horizon.

```
DINNERS — week of {Thu M/D} (reply with picks by {deadline})

{Structural note, only when there is one. See below.}

THIS {THU}–{SUN} — your plan for the next four days
{Thu M/D} ({calendar flag, if any}) — A) {option}  B) {option}
{Fri M/D} (clear) — A) {option}  B) {option}
{Sat M/D} (weekend rule) — A) {set-and-forget, start by {time}}  B) {named order-in}
{Sun M/D} (weekend rule) — A) {option}  B) {named order-in}

NEXT WEEK — {Mon M/D} onward (provisional)
{Delivery service picks, numbered, if there is a service:}
  1. {entrée} 2. {entrée} 3. {entrée} ...
{Then the following Thu–Sun, 2 options per night, marked PROVISIONAL}

SHOPPING LIST — buy by {day}
{Store}: {item}, {item}, {item}
Staples: {item}, {item}
From your shared list: {item}, {item}
{Budget flag line, if over}

Reply like: "{Thu A, Fri B, Sat A, Sun B}" or "{1, 3, 4}".
Did not run: {none / the specific thing that failed}
```

### Rules for the proposal itself

**The deadline in the header is real.** If there is a delivery service with a cutoff, that
is the deadline. If there is not, it is the day before the shopping happens.

**Two options per open night, and never more.** Three is a decision, two is a pick.

**At least one set-and-forget option in the near block.** If the household has no
equipment for it, that becomes a make-ahead or an assembly night, and it is still marked.

**Constrained nights get a set-and-forget option and a named order-in.** Never a
from-scratch evening cook. Name the calendar reason in parentheses so the person can see
you read their week.

**Closed nights are confirmed, not offered.** `{Fri M/D} — birthday dinner at your
mother's (already set)`.

**The structural note goes at the top, and only when it earns its place.** If every night
in the near block is constrained, say so in one line: "Every night this week has something
in it, so this is a slow-cooker and takeout week." Without that line, four order-in options
read like the planner gave up. With it, they read like an accurate week.

**The "did not run" line is never omitted.** If everything worked, it says `none`. That
way its absence is noticeable and its presence is trusted.

**Only the near block's ingredients go on the shopping list.** The far block is
provisional and its food gets bought in the next cycle, so it stays fresh.

---

## Parsing the reply

Be generous. Never bounce a reply back for reformatting.

| They write | It means |
|---|---|
| `Thu A, Fri B` | those options on those nights |
| `1, 3, 4` | those numbered delivery items, at the quantity you proposed |
| `1, 3 (x2), 4` | quantity override on item 3 |
| `Sat B` | the second option for Saturday |
| `Fri pizza` | the named pizza place from their order-in defaults |
| `skip carrots` | drop that item from the shopping list |
| `no salmon this week` | drop that option, propose the alternate |
| a phonetic or misspelled place name | match it to their defaults |

**Sum the picks against any minimum before you build.** If a service has a $100 minimum or
a fixed box size and the picks come in under or over, say so and ask, rather than silently
adding or cutting. Adding an item nobody chose is worse than a short order.

**Ask at most one clarifying question.** If two readings are both plausible, pick the more
conservative one, build it, and name the assumption in the output. A reply that triggers
three questions is a reply that stops the ritual.

**Echo everything back:** every pick, every substitution, every item you could not find.

---

## The week file

One per weekly run, at `{path}/weeks/YYYY-MM-DD.md`, keyed to the Monday of the week being
planned.

```markdown
# Week of {Monday date}

## Runs
- {timestamp} proposal sent
- {timestamp} picks parsed
- {timestamp} list produced / cart staged

## Calendar flags
- {Tue: soccer 5:30–7:00 — constrained}
- {Sat, Sun: weekend rule}

## Proposal
{a copy of what was sent}

## Picks
{their reply, verbatim}
{how you read it}

## List
{the final shopping list, after their edits}

## Learnings
{anything worth folding into meal-system.md, and whether it was}
```

**Why keep the file at all:** the last three of these are what the no-repeat rule reads,
and what lets a run six weeks from now know that the pulled pork was a miss. Without them
the planner starts from zero every week and the household notices.
