# The setup interview

Read this before running setup mode. It carries the full question list, why each one
matters, the default to offer, and what to do with the answer.

## How to run it

Ask in **four batches**, not fifteen separate turns. Each batch is a short numbered list.
Every question carries a default in brackets, so "use the defaults" is a complete and
valid answer to any batch.

Keep it to four messages. Someone setting up a dinner system on a Thursday night does not
want an intake form. If an answer is missing and the default covers it, take the default
and note it in the system file rather than asking again.

Do not explain the whole system up front. Ask the questions, then read back the rules you
derived. That is the moment they understand it.

---

## Batch A — who is eating

**A1. How many adults, how many kids, and what ages?**
*Why:* portion counts, and the kid-safety split. A household with a two-year-old needs a
different proposal than one with three teenagers.
*Default:* none, this one is required.
*Maps to:* the Household section; portion sizing on every recipe; whether "kid-safe" is a
real constraint or just a preference.

**A2. Any allergies or hard restrictions? Then, separately, the soft ones.**
*Why:* allergies are the only true filter in the system. Everything else is ranking. Keep
them in separate lists so you never treat "nobody loves fish" as if it were a nut allergy,
or the reverse.
*Default:* none.
*Maps to:* Hard rules (allergies, always checked before proposing anything) and Food
sources (preferences, which only affect ranking).

**A3. Name three dinners the kids reliably eat, and three the adults miss having.**
*Why:* this seeds the recipe log with real dishes instead of a generic list, and it
surfaces the tension every family has. The kid-safe dishes carry the busy nights. The
adult ones are what makes the week feel like more than logistics.
*Default:* none, but accept fewer than three of either.
*Maps to:* the starter `recipes.md`, tagged kid-safe or not.

---

## Batch B — the shape of the week

**B1. Realistically, how many nights a week do you cook from scratch? And what is the most
time you have on a weeknight?**
*Why:* the proposal must never offer more cooking than the household will actually do.
Over-proposing is how a planner teaches someone to ignore it. Ask for the realistic number,
not the aspirational one, and say so.
*Default:* 3 cooks a week, 30 to 45 minutes on a weeknight.
*Maps to:* how many cook nights appear in each block; the max time on any weeknight recipe.

**B2. Which evenings are usually busy, and how do you want to share your calendar each
week?**
Three ways to share it: paste it in, connect a calendar tool if this environment has one,
or just tell the planner each week.
*Why:* the calendar sweep is the core mechanism. Without a channel for it the whole system
degrades into a recipe generator. Recurring commitments get recorded once so they apply
even in a week where the calendar is not shared.
*Default:* paste it in each week; no recurring busy nights.
*Maps to:* the Calendar section; the constrained-night logic in every weekly run.

**B3. Do you actually cook from scratch on Saturday and Sunday evenings?**
Offer the default rule before they answer: weekend and event nights get a set-and-forget
option or a named order-in, never a from-scratch evening cook. Explain it in one line, the
honest way. A from-scratch plan on a busy night dies, and then dinner becomes whatever is
fastest at 6:45.
*Why:* people say yes to weekend cooking and then do not do it. Naming the rule and letting
them opt out gets a much more honest answer than asking cold.
*Default:* rule on.
*Maps to:* Hard rules; whether Saturday and Sunday are auto-constrained.

**B4. What set-and-forget equipment do you own? Slow cooker, pressure cooker, sheet pan,
none of the above?**
*Why:* this decides what a constrained night is actually allowed to be. Without any of it,
"set and forget" becomes make-ahead or assembly, and the proposal has to say so.
*Default:* whatever they name; if nothing, use make-ahead and cold assembly.
*Maps to:* the Week's shape section; the required set-and-forget option in every block.

---

## Batch C — where the food comes from

**C1. Do you use a meal-delivery or prepared-food service? If so: name, which nights it
covers, what day the menu posts, the order cutoff, the delivery day, and any minimum.**
*Why:* a service with a cutoff turns the weekly ritual into a real deadline, which is
mostly good. It also becomes the spine of the far block. The cutoff is the single most
important fact here, because missing it costs a week.
*Default:* none.
*Maps to:* Food sources; the far block's structure; the deadline printed at the top of
every proposal.

**C2. Groceries: delivery or pickup through an app, or in person? Which store, and which
day do you shop?**
*Why:* this determines whether the output is a staged cart or a printed list, and it sets
the buy-by day that everything in the near block depends on.
*Default:* in person, Friday or Saturday.
*Maps to:* Food sources; how the shopping list is delivered; the buy-by date on every
proposal.

**C3. Name two or three places you order from. The pizza place, the quick one, the treat.**
*Why:* order-in has to be proposable by name or it is not really an option, it is a
fallback wearing an option's clothes. This question is required for that reason. A
household that will not name a takeout place will get a planner that quietly pretends
takeout does not exist, and then they will order takeout anyway.
*Default:* none, required, but one is enough.
*Maps to:* Food sources; every constrained night's second option.

**C4. What do you buy every single week regardless? And is there a shared list the
household adds to?**
*Why:* staples ride along on every list so nobody has to remember them. A shared list is
read every run and never cleared.
*Default:* no staples, no shared list.
*Maps to:* Food sources; the staples block appended to every shopping list.

**C5. Is there a weekly grocery number you want flagged when the list goes over?**
*Why:* a soft guardrail, not a hard limit. The planner mentions it, it does not enforce it.
*Default:* skip.
*Maps to:* Food sources; a one-line flag on the shopping list.

---

## Batch D — the ritual

**D1. What day and time do you want the proposal, and where should it land? In chat, as a
file, or as an email you send to yourself?**
*Why:* the ritual needs a fixed slot or it does not happen. The channel matters less than
the fixedness. If a meal-delivery cutoff exists, the proposal day has to be before it, and
say so if they pick a day that does not work.
*Default:* Thursday morning, in chat.
*Maps to:* the Weekly ritual section.

**D2. Where do your recipes live? A doc or note you will paste, a file the planner can
read, or should it build you a starter log from the dinners you already named?**
*Why:* the recipe log is what makes the three-week no-repeat rule possible and what stops
the proposal from being generic. Most people do not have one, which is fine; building it
from Batch A's answers is a good start and it grows.
*Default:* build the starter log.
*Maps to:* the Recipe source section; `recipes.md`.

**D3. When you get the proposal, you will reply with picks. Confirm the format: numbers
and nights, like "Thu A, Fri B, Sat A" or "1, 3, 4."**
*Why:* setting the reply convention once removes the friction from the only step the human
has to do every week. Say that any reasonable reply will be understood and that this is
just the shortest version.
*Default:* yes.
*Maps to:* the Weekly ritual section; the reply-format line printed at the bottom of every
proposal.

**D4. Where should these files live?**
*Why:* one folder, chosen once.
*Default:* a `meal-cart/` folder in the current directory.
*Maps to:* the path recorded at the top of the system file.

---

## Closing the interview

1. Read the rules back as a short bullet list, in their words, not yours. Include the
   weekend rule, the never-buy rule, the allergy filter, and the cook-nights number.
2. Ask for a yes, or for the one thing to change.
3. On yes, write the files and print a short "here is what happens next" with the actual
   day and the actual first thing they will do.

Do not write the files before the confirmation, and do not skip the read-back. It is the
only moment where a wrong answer is cheap to fix.
