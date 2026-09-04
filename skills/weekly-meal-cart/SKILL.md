---
name: weekly-meal-cart
description: Set up and run a weekly family dinner system. The first run interviews the user to build THEIR rules (household, allergies, busy nights, delivery service, grocery method, recipe log) and writes a personal meal-system.md. Every later run sweeps the calendar, treats evening commitments as constraints, proposes two blocks of dinner options with numbered picks, and produces the shopping list or a staged cart without ever buying anything. Use whenever someone wants to plan dinners for the week, build a meal-planning routine, turn a calendar into a grocery list, stop the 6 PM dinner scramble, figure out what to cook on busy nights, or says "weekly meal cart" or "meal cart blueprint". Modes are inferred rather than typed, covering setup, weekly, picks, tonight and learn. This is the shareable version of a private /meal-plan command; if that command exists in this environment, it owns its author's household and this skill must not run.
license: MIT
---

# Weekly Meal Cart

A weekly ritual that turns a calendar into dinner. Once a week you sweep the days ahead,
treat every evening commitment as a constraint rather than a hope, propose two options a
night, take the household's picks, and hand back a shopping list or a staged cart.

You never buy anything. They click pay.

The spine of the whole thing, in one sentence: **ordering in is fine, ordering in because
there was no plan is the thing this prevents.** A planned takeout night and an unplanned
one produce identical food and completely different weeks.

This is generalized from a private system that has run weekly since August 2026 for a
household of six. Nothing here depends on that setup, and no part of it needs a paid
service, a particular store, or a particular notes app.

---

## Step 0: work out which mode you are in

Modes are inferred from state, not typed by the user. Check in this order.

| Signal | Mode |
|---|---|
| The user says "set up", "start over", "new household" | **setup** |
| No `meal-system.md` can be found (glob `**/meal-system.md` from the working directory). If you cannot read files at all, ask once: "have we set this up before? paste your meal-system.md if so" | **setup** |
| A system file exists and the message is about the coming week, groceries, the menu, or is just "run it" | **weekly** |
| A system file exists and the message is a reply of numbers or nights, like "1, 3, 4" or "Thu A, Sat B" | **picks** |
| The message is about tonight only: "what's for dinner tonight" | **tonight** |
| The message is feedback about a meal already eaten: "the kids hated it", "that worked", "never again" | **learn** |

**One guard before anything else.** If a `/meal-plan` command exists in this environment,
it belongs to this skill's author and it knows his household's actual services. Say so in
one line and stop. Do not run an interview for someone who already has the real thing.

---

## Step 1: setup, the interview

Read `references/interview.md` first. It carries the full question list with the reasoning
and the default for each one.

Ask in **four batches**, not fifteen turns. Every question carries a bracketed default, so
"use the defaults" is a complete answer to any batch.

**Batch A, who is eating.** Household size and kids' ages. Allergies and hard restrictions,
then separately the soft preferences. Three dinners the kids reliably eat and three the
adults miss.

**Batch B, the shape of the week.** Realistic from-scratch cooks per week and the weeknight
time ceiling. Which evenings are usually busy, and how the calendar gets shared each week.
Whether they actually cook on weekend evenings, offering the default rule first and letting
them opt out. What set-and-forget equipment they own.

**Batch C, where the food comes from.** A meal-delivery service, if any, with its menu day,
cutoff, delivery day and minimum. Groceries: delivery, pickup or in person, which store,
which day. Two or three order-in places by name, which is required. Weekly staples and any
shared household list. An optional weekly budget number to flag.

**Batch D, the ritual.** Proposal day, time and channel. Where recipes live, or build a
starter log. Confirm the numbered-picks reply format. Where the files should live.

**Then, before writing anything:** read the derived rules back as a short bullet list in
their own words, and ask for a yes or the one thing to change. This read-back is the only
moment where a wrong answer is cheap to fix. Do not skip it.

On yes, write three things using `references/system-template.md` and
`references/recipe-log-template.md`:

```
{their folder}/meal-system.md     their rules, in their words
{their folder}/recipes.md         the starter log, from the dinners they named
{their folder}/weeks/             empty, one file per week from here on
```

Close with a short "here is what happens next," naming the actual day and the actual first
thing they will do.

---

## Step 2: the weekly run

1. **Read the state.** `meal-system.md`, `recipes.md`, and the last three files in
   `weeks/`. The week files give you the no-repeat list and any night they already closed.

2. **Sweep the calendar,** today through the end of next week, roughly twelve days. For
   every dinner night, ask one question: is there anything blocking the 4 to 8 PM window?
   Mark those nights **constrained**. Mark Saturday and Sunday constrained too, unless this
   household turned the weekend rule off. If the calendar was not shared, ask for it. Never
   assume a week is clear.

3. **Read the delivery menu,** only if a service is configured, and only from a menu they
   pasted or a page you can actually fetch. If you cannot read it, say so and skip the
   section. Never invent a menu item. See `references/carts-and-lists.md`.

4. **Build the near block,** tonight through the end of the weekend or through the buy-by
   day, whichever comes first. Two options per open night. Constrained nights get a
   set-and-forget option and a named order-in, never a from-scratch evening cook. At least
   one set-and-forget in the block. Nothing cooked in the last three weeks. A night they
   already closed gets confirmed, not re-offered. **This block drives the shopping list.**

5. **Build the far block,** next week in outline. Delivery-service picks first if there is
   a service, numbered with quantities. Then the following nights, two options each, marked
   PROVISIONAL. Do not shop for this block; its food would sit for ten days.

6. **Produce the shopping list.** Near block ingredients, plus staples, plus anything on
   their shared list, grouped by store section. Buy-by day at the top. Flag the budget
   number if the list looks over it.

7. **Add the structural note, only if it earns its place.** If every night in the near
   block is constrained, say so in one line: "every night this week has something in it, so
   this is a slow-cooker and takeout week." Without that line four takeout options read
   like you gave up. With it, they read like an accurate week.

8. **Write the week file,** deliver the proposal in their configured channel, end with the
   reply-format line and the "did not run" line, and **stop.** Do not proceed to a shopping
   list before they have picked.

Format for all of this is in `references/proposal-template.md`.

---

## Step 3: their picks

Parse generously. Never bounce a reply back for reformatting. Bare numbers inherit the
quantity you proposed. "Sat B" is the second Saturday option. "Fri pizza" is their named
pizza place. "Skip carrots" drops an item. A misspelled restaurant matches their defaults.

**Sum the picks against any minimum or box size before you build.** Short or over, say so
and ask. Never add an item nobody chose in order to clear a minimum.

**Ask at most one clarifying question.** If two readings are both plausible, take the more
conservative one, build it, and name the assumption.

Record the picks in the week file. Then produce the final shopping list, or stage the cart
if you have browser access and they asked for that, and stop before any checkout.

Echo everything: every pick, every substitution, every item you could not find.

---

## Step 4: tonight

One decision, not a menu. This is the exception to the two-options rule, because at 4 PM on
an unplanned Saturday a menu is another job.

- **Set-and-forget night:** give the recipe, the ingredients to pull, and the start-by
  time. **First check the food is actually in the house.** If the ingredients went on a
  list and no shopping has happened since, lead with that instead. That failure is why this
  mode exists.
- **Order-in night with a timing edge:** one line, what and when to order by. If there is
  no timing edge, say nothing. This must not become a weekend alarm clock.
- **A from-scratch cook is on the books for a constrained night:** name it, say plainly
  that it is an evening cook on a night with something in it, offer the two compliant
  swaps, and drop it. Their call, said once.
- **Open night, no plan:** name one thing they can still do right now.

Never touch a cart in this mode.

---

## Step 5: learn

Append one dated bullet under `## Learned` in `meal-system.md`. Kid reactions, a dish that
stuck, a dish that is retired, a new recurring busy night. Update `last cooked` in
`recipes.md` for anything they made. Confirm in one line what changed.

**Never rewrite their own lines.** Append only.

---

## The rules, every mode

Full reasoning for each of these is in `references/rules.md`. Read it once; the short form:

- **Never buy.** Build the list, stage the cart, stop. Never enter a checkout flow, never
  submit payment, never store payment details. They click pay, every time.
- **Never clear a shared list or cart.** Somebody else in the house is using it.
- **A 4 to 8 PM calendar block is a constraint, not a question.** That night is not allowed
  to be offered a from-scratch evening cook.
- **Order-in is a planned choice, proposed by name.** Never a fallback.
- **Menu of options, never a single answer,** except in tonight mode.
- **Closed nights are confirmed, not re-offered.**
- **A set-and-forget cook's real dependency is a morning,** and its ingredients being bought
  is part of the pick.
- **Nothing cooked in the last three weeks.**
- **Loud errors beat false success.** Name every leg that did not run. Never report a clean
  run that was not clean.
- **Never invent a menu item, a price, or a recipe they "already have."** A recipe you wrote
  fresh is labelled as new.
- **Write only inside their own folder.**

---

## What good output looks like

**Setup, the final turn:**

```
Written to meal-cart/:
  meal-system.md   your rules
  recipes.md       8 dinners to start
  weeks/           empty until Thursday

The rules I'll follow:
  - Nut allergy is an absolute filter, checked before anything is proposed
  - 3 from-scratch cooks a week, 40 minutes max on a weeknight
  - Tue and Thu are constrained, so those nights get the slow cooker or a named takeout
  - Sat and Sun same, by the weekend rule
  - I build the Kroger list, you place the pickup order

Thursday morning, say "run the week" and paste your calendar through next Sunday.
```

**A weekly proposal:**

```
DINNERS — week of Thu 9/10 (reply with picks by Fri noon)

Every weeknight this week has something in it, so this is mostly a slow-cooker week.

THIS THU–SUN — your plan for the next four days
Thu 9/10 (piano 4:30) — A) slow-cooker honey garlic chicken, start by 9 AM  B) Thai Garden
Fri 9/11 (clear) — A) sheet-pan salmon and broccoli  B) chicken tacos
Sat 9/12 (birthday party 5–7) — A) slow-cooker pulled pork, start by 8 AM  B) Domino's
Sun 9/13 (weekend rule) — A) pulled pork leftovers, no cooking  B) Chipotle

NEXT WEEK — Mon 9/15 onward (provisional)
Mon–Wed: cook nights, options next Thursday
Thu–Sun: PROVISIONAL, firms up in the next run

SHOPPING LIST — buy by Sat 9 AM pickup
Kroger produce: broccoli (2 heads), lemons (2), slaw mix
Kroger meat: chicken thighs (2 lb), salmon fillets (4), pork shoulder (3 lb)
Kroger pantry: honey, soy sauce, bbq sauce, buns, jasmine rice
Staples: milk (2 gal), bananas, bread, rice
From your shared list: paper towels
Roughly $165, under your $180 flag.

Reply like: "Thu A, Fri B, Sat A, Sun A" or "1, 3, 4".
Did not run: none.
```

A fully worked example, from setup through a week to a learn entry, is in
`references/example-household.md`.

---

## When there is no filesystem and no tools

On claude.ai, or pasted into any chat model, everything above still works. Two changes:

- Emit each file as a fenced code block and tell them to save it, or keep it in a Project
  so it comes back next week.
- Ask for pastes instead of fetching: the calendar, the menu, the shared list.

Nothing else changes. The calendar sweep, the two blocks, the constrained nights and the
never-buy rule are all just judgment, and they work in a chat window.

---

## Reference files

- `references/rules.md` — the rules and the failure behind each one. Read once.
- `references/interview.md` — before running setup.
- `references/system-template.md` — the file setup writes.
- `references/proposal-template.md` — the weekly proposal, reply parsing, the week file.
- `references/recipe-log-template.md` — the dinner log and its fields.
- `references/carts-and-lists.md` — in-person, delivery, pickup, and menu-based services.
- `references/example-household.md` — one household, worked end to end.
