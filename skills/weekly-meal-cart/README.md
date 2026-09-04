# Weekly Meal Cart

**Turn your calendar into the week's dinners and a shopping list. It never buys anything.**

Once a week it looks at the days ahead, treats every evening commitment as a constraint
instead of a hope, gives you two options a night, takes your picks, and hands back a
shopping list. You buy the food.

The first time you run it, it interviews you: household, allergies, how many nights you
will realistically cook, which evenings are already busy, where you shop, which takeout
places you actually order from. It writes those answers to a file and works from them
every week after.

---

## Install

**Claude Code, as a skill.**

```
git clone https://github.com/chrisminglee/remote-life-os.git
cp -r remote-life-os/skills/weekly-meal-cart ~/.claude/skills/
```

Restart Claude Code, then say "help me plan dinners for next week." Skills trigger on what
you say, so there is no command to remember.

**Claude on the web, as a Project.** Make a new Project, paste the contents of
[`SKILL.md`](SKILL.md) into its custom instructions, and start a chat. It is written to
work with no filesystem: it hands you the files as text and you keep them in the Project.

**No install at all.** Paste [`STARTER-PROMPT.md`](STARTER-PROMPT.md) into whatever chat
model you already use. You lose the memory between weeks. Everything else is the same.

---

## What a week looks like

You say "run the week" and paste your calendar. You get back something like this:

```
DINNERS — week of Thu 9/10 (reply with picks by Fri noon)

Every weeknight this week has something in it, so this is mostly a slow-cooker week.

THIS THU–SUN — your plan for the next four days
Thu 9/10 (piano 4:30) — A) slow-cooker honey garlic chicken, start by 9 AM  B) Thai Garden
Fri 9/11 (clear) — A) sheet-pan salmon and broccoli  B) chicken tacos
Sat 9/12 (birthday party 5–7) — A) slow-cooker pulled pork, start by 8 AM  B) Domino's
Sun 9/13 (weekend rule) — A) pulled pork leftovers, no cooking  B) Chipotle

NEXT WEEK — Mon 9/15 onward (provisional)
...

SHOPPING LIST — buy by Sat 9 AM pickup
Kroger produce: broccoli (2 heads), lemons (2), slaw mix
...

Reply like: "Thu A, Fri B, Sat A, Sun A".
Did not run: none.
```

You reply `Thu A, Fri B, Sat A, Sun A`. It gives you the final list. You shop.

---

## The rules it follows, and why

Four of these are the whole system. The rest are detail.

**A calendar block between roughly 4 and 8 PM is a constraint, not a question.** Soccer at
5:30 does not mean "probably no time to cook." It means that night is not allowed to be
offered a from-scratch dinner at all. It gets something started in the morning, or takeout
by name. This is the highest-value rule here and it was learned the expensive way: a
from-scratch plan on a busy night dies every time, and then dinner is whatever is fastest
at 6:45.

**Takeout is a planned choice, named in advance.** Not a fallback, not a failure. Most
people do not mind ordering in. What they mind is ordering in *because there was no plan*.
Same food, completely different evening.

**Two options a night, and you pick.** A planner that hands down one answer gets overridden
and then abandoned, because it does not know about the leftovers or the mood or the big
lunch.

**It never buys anything.** It builds the list, or stages the cart if you use grocery
delivery, and then it stops and tells you what to click. Your five minutes at the checkout
screen is also the last quality check on everything upstream: you see the total, you see
the substitutions, you catch what it got wrong.

The rest, with the specific failure behind each one, is in
[`references/rules.md`](references/rules.md).

---

## What it will never do

- Place an order, enter a checkout, or touch payment details.
- Clear your shared household shopping list. Somebody else is using it.
- Invent a menu item, a price, or a recipe you supposedly already have.
- Quietly skip a step. If it could not read your calendar, it says so in the output.

---

## Where this came from

A private version has run every week since August 2026 for a household of six, wired into
one family's specific meal-delivery service, grocery store and notes app. This is that
system with all of it stripped out. It needs no paid service, no particular store, and no
particular app.

The full write-up is in [Remote Life OS](https://www.remotelifeos.com).

MIT licensed. Take it apart.
