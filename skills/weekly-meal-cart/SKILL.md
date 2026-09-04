---
name: weekly-meal-cart
description: Set up and run a weekly family dinner system. The first run interviews the user to build THEIR rules (household, allergies, busy nights, delivery service, grocery method, recipe log) and writes a personal meal-system.md. Every later run sweeps the calendar, treats evening commitments as constraints, proposes two blocks of dinner options with numbered picks, and produces the shopping list or a staged cart without ever buying anything. Use whenever someone wants to plan dinners for the week, build a meal-planning routine, turn a calendar into a grocery list, stop the 6 PM dinner scramble, figure out what to cook on busy nights, or says "weekly meal cart" or "meal cart blueprint". Modes are inferred rather than typed, covering setup, weekly, picks, tonight and learn. Not for one-off recipe questions, single dinner parties, or fitness meal prep.
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

This is generalized from one family's private system that has run weekly since August
2026. Nothing here depends on that setup, and no part of it needs a paid service, a
particular store, or a particular notes app.

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

**One check before setup.** If this environment already has a personal meal-planning
command or skill of its own, one that names actual stores, services or accounts, that one
knows the household's real setup and this one does not. Say so in a line and ask which
they want. Do not refuse silently, and do not assume a command called `meal-plan` is
necessarily the author's rather than the user's own.

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
them opt out. What set-and-forget equipment they own, **and one thing they already make in
it** (see the note below, this question matters more than it looks).

**Batch C, where the food comes from.** A meal-delivery service, if any, with its menu day,
cutoff, delivery day and minimum. Groceries: delivery, pickup or in person, which store,
which day. Two or three order-in places by name, which is required. **If there is a serious
allergy in the house, ask which of those places they have already cleared for it.** Weekly
staples and any shared household list. An optional weekly budget number to flag.

**Batch D, the ritual.** Proposal day, time and channel. Where recipes live, or build a
starter log. Confirm the numbered-picks reply format. Where the files should live.

**Then, before writing anything:** read the derived rules back as a short bullet list in
their own words, and ask for a yes or the one thing to change. This read-back is the only
moment where a wrong answer is cheap to fix. Do not skip it. If you are running
unattended and no confirmation can arrive, say that you are proceeding without one.

On yes, write three things using `references/system-template.md` and
`references/recipe-log-template.md`:

```
{their folder}/meal-system.md     their rules, in their words
{their folder}/recipes.md         the starter log, from the dinners they named
{their folder}/weeks/             empty, one file per week from here on
```

**The set-and-forget gap, and how to be honest about it.** Most households name six
dinners and none of them are slow-cooker dinners, so the starter log has nothing that can
fill a constrained night. Every weekly run needs at least one such option, and inventing
one and calling it theirs is forbidden. The resolution: write the dish out in full, label
it **NEW, never made here** in the log and again in the proposal, and say so plainly. Do
not paper over it. Say it in the setup close too, so the first proposal is not a surprise.

Close with a short "here is what happens next," naming the actual day and the actual first
thing they will do.

---

## Step 2: the weekly run

1. **Read the state.** `meal-system.md`, `recipes.md`, and the last three files in
   `weeks/`. **The picks recorded in those files are your no-repeat list**, because a
   picked dish is the best available evidence of a cooked dish. On a household's first
   weekly run there is no list and the three-week rule cannot run at all. Say that on the
   did-not-run line rather than implying it ran.

2. **Sweep the calendar,** today through the end of next week, roughly twelve days. For
   every dinner night, ask one question: is there anything blocking the 4 to 8 PM window?
   Mark those nights **constrained**. Apply the household's weekend rule per day, since it
   is recorded per day and a split answer is common. If the calendar was not shared, ask
   for it. Never assume a week is clear.

3. **Read the delivery menu,** only if a service is configured, and only from a menu they
   pasted or a page you can actually fetch. If you cannot read it, say so and skip the
   section. Never invent a menu item. See `references/carts-and-lists.md`.

4. **Build the near block:** tonight through the end of the coming weekend. Two options per
   open night. Constrained nights get a set-and-forget option and a named order-in, never a
   from-scratch evening cook. At least one set-and-forget in the block. Nothing on the
   no-repeat list. A night they already closed gets confirmed, not re-offered.

   **Two timing checks that decide whether an option is real.** Run both on every night
   before you print it.

   - **Is the food in the house yet?** Nothing bought at the next shop can be eaten before
     that shop. For any night falling before the buy-by day, propose only what they already
     have, or a named order-in, or a dish whose ingredients they can grab on the way home,
     and say which. This usually means **tonight has no set-and-forget option at all.** Say
     that in one line rather than offering an impossible one.
   - **Has the start time already passed?** A set-and-forget dish proposed after its
     start-by time is not an option. And its start-by time has to come *after* the shop
     that brings its ingredients. An 8 AM start on meat collected at 9 is the exact failure
     `references/rules.md` §7 exists to prevent.

5. **Build the far block:** next week in outline. Delivery-service picks first if there is a
   service, numbered with quantities. Then the following nights, two options each, marked
   PROVISIONAL. Do not shop for this block; its food would sit for ten days.

6. **Draft a provisional shopping list into the proposal.** It has to cover every cook
   option you offered, so it over-lists on purpose. Label it: "this covers every cook
   option above, lines drop once you pick." Near block only, plus staples, plus anything on
   their shared list, grouped by store section, buy-by day at the top. If you give a cost,
   mark it as your estimate. A guessed number presented as a real price is forbidden; a
   number they can sanity-check against a budget is useful, so give a range and label it.

7. **Add a structural note at the top when the week has a shape worth naming.** If most of
   the near block is constrained, or the only open night falls before the shop, say so in
   one line. Without it, four takeout options read like you gave up. With it, they read
   like an accurate week. Skip it on an ordinary week.

8. **Write the week file, deliver the proposal, and stop.** End with the reply-format line
   and the did-not-run line. **Do not produce the final shopping list yet**, and never stage
   a cart before they have picked. The provisional list from step 6 is inside the proposal;
   the real one comes next.

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

Record the picks in the week file. Then produce the final shopping list, cut down from the
provisional one now that the options are settled, or stage the cart if you have browser
access and they asked for that, and stop before any checkout.

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

Never touch a cart in this mode. Append one line to the current week file recording what
you sent, so the week's record stays complete.

---

## Step 5: learn

Append one dated bullet under `## Learned` in `meal-system.md`. Kid reactions, a dish that
stuck, a dish that is retired, a new recurring busy night.

**When they state a change of fact, update the section that holds that fact too**, and date
the change. A freed-up Wednesday belongs in `## Calendar`, a new store belongs in `## Food
sources`. Leaving the old fact standing while the truth sits in a footnote makes the file
lie to every future run. Update `last cooked` in `recipes.md`, and move a failed dish to
`## Retired` with the reason rather than deleting it.

**What you never rewrite:** their one-paragraph description, their hard rules, and anything
written in their own voice. Facts you maintain, prose is theirs.

Confirm in one line what changed.

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
- **A set-and-forget cook's real dependency is a morning,** its ingredients have to be in
  the house before that morning, and its start-by time has to be still ahead.
- **Nothing on the no-repeat list**, taken from the last three weeks of picks.
- **An allergy is an absolute filter, and it extends to takeout.** A restaurant whose
  kitchen they have not cleared does not get proposed on a night the allergic person eats.
  Say why you withheld it rather than dropping it silently.
- **A soft preference demotes a dish, it does not ban it.** When you propose one anyway,
  say so on the line.
- **Loud errors beat false success.** Name every leg that did not run. Never report a clean
  run that was not clean.
- **Never invent a menu item, a real price, or a recipe they "already have."** A recipe you
  wrote fresh is labelled NEW. A cost you estimated is labelled an estimate.
- **Write only inside their own folder.**

---

## What good output looks like

**Setup, the final turn:**

```
Written to meal-cart/:
  meal-system.md   your rules
  recipes.md       7 dinners to start, 5 of them yours
  weeks/           empty until Thursday

The rules I'll follow:
  - Tree nuts are an absolute filter, checked before anything is proposed. Not a
    preference, not a ranking.
  - 3 from-scratch cooks a week, 40 minutes max on a weeknight.
  - Tue (soccer 5:30) and Thu (piano 4:30) are constrained, so those nights get the slow
    cooker or a named takeout. Sat and Sun the same, by the weekend rule you kept on.
  - Pork gets demoted, not banned. When I propose it anyway I'll say so on the line.
  - I build the list. You place the Saturday pickup and you check out. I never enter a
    checkout, and I never clear your shared list.

Two things on the record before we start. Your slow cooker has no dish in the log, because
none of the six dinners you named were slow-cooker dinners. So the set-and-forget options
I write this week are marked NEW. You have not made them, I wrote them. If one works it
earns a real entry.

And Thai Garden is one of your three, with an epi-pen kid in the house. Ask them about
cross-contact before I put it on a board where she is eating.

Thursday morning, say "run the week" and paste your calendar through next Sunday.
```

**A weekly proposal** (note what it refuses to offer, and why it says so out loud):

```
DINNERS — week of Thu 9/10 (picks by Fri 6 PM, so the pickup order is in before Saturday.
Thursday and Friday need an answer today.)

Three of the four nights in this block have something in them, and the one that doesn't,
Friday, lands before your Saturday 9 AM pickup. So this is a slow-cooker and takeout week
with one real cook, and whatever you pick for Friday needs a grab on the way home.

THIS THU–SUN — your plan for the next four days
Thu 9/10 (piano 4:30) — A) Domino's  B) Chipotle
  No slow-cooker option tonight. It would have needed a 9 AM start that has already
  passed, and the ingredients are not in the house until Saturday.
Fri 9/11 (clear, but before Saturday's pickup) — A) sheet-pan chicken thighs and broccoli,
  35 min  B) pasta with meatballs, 30 min. Either needs a Friday stop on the way home.
Sat 9/12 (party 5–7, plus weekend rule) — A) slow-cooker pulled pork, start by 10 AM right
  after the pickup, ready by 6, holds on warm until you're back at 7:15. Pork, so one of
  you sits it out.  B) Domino's, ordered before you leave
Sun 9/13 (weekend rule) — A) Saturday's pulled pork again, reheat only  B) Chipotle

Thai Garden is not on this week's board. The cross-contact question is still open and the
6-year-old eats every one of these dinners.

NEXT WEEK — Mon 9/14 onward (provisional, nothing bought for it)
Mon 9/14 — dinner with Rob & Kim. You're out. Not planning this one.
Tue 9/15 (soccer 5:30) · Wed 9/16 (home ~8) · Thu 9/17 (piano) — slow cooker or a named
  order-in. PROVISIONAL
Fri 9/18 (clear) — the cook night. PROVISIONAL

SHOPPING LIST — buy by Sat 9/12, 9:00 AM pickup
This covers every cook option above. Lines drop once you pick.
Produce: broccoli (2 heads), lemons (2), coleslaw mix, yellow onions (2)
Meat: chicken thighs (2.5 lb), pork shoulder (3 lb), meatballs (1 lb)
Pantry: pasta, marinara, bbq sauce, slider buns, taco seasoning, olive oil
Staples: milk (2 gal), bananas, bread, rice, eggs
Rough estimate $95 to $125. That is my estimate, not a store price. Under your $180 flag.

Reply like: "Thu A, Fri B, Sat A, Sun A".

Did not run:
- Your shared list. I cannot read it here. Paste it and I'll fold it in before you order.
- The three-week no-repeat rule. Your log was built this morning, so nothing was excluded
  from this proposal. It starts working next week.
- Both set-and-forget dishes are marked NEW in your log. You have not made either one.
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

- `references/rules.md`: the rules and the failure behind each one. Read once.
- `references/interview.md`: before running setup.
- `references/system-template.md`: the file setup writes.
- `references/proposal-template.md`: the weekly proposal, reply parsing, the week file.
- `references/recipe-log-template.md`: the dinner log and its fields.
- `references/carts-and-lists.md`: in-person, delivery, pickup, and menu-based services.
- `references/example-household.md`: one household, worked end to end.
