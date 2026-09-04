# Carts, lists, and menus

Households buy food in different ways. The planning logic is identical in every case; only
the last step changes. This file covers that last step.

**The rule that does not change in any variant: you build it, they buy it.** Never enter a
checkout flow, never submit payment, never place an order.

---

## Variant 1: in-person shopping (the default)

Produce a printed-and-readable list, grouped by store section so it can be walked.

```
SHOPPING LIST — buy by Sat AM

Produce: broccoli (2 heads), lemons (2), green beans (1 lb)
Meat: chicken thighs (2 lb), salmon fillets (4)
Dairy: cheddar (block), sour cream, milk (2 gal)
Pantry: jasmine rice, taco seasoning, soy sauce
From your shared list: paper towels, bananas
```

Group by section, not by recipe. Nobody shops by recipe. Combine duplicate ingredients
across dishes into one line with the total quantity.

## Variant 2: grocery delivery or pickup, with browser access

If the environment can drive a browser and the household asked for a staged cart:

1. Open their store's storefront. It must already be logged in. If it is not, say so and
   fall back to the list. Never attempt to log in on their behalf.
2. Search and add each item. For an ambiguous match, pick the obvious one, and record it
   as a substitution.
3. **Report your subtotal separately from anything already in the cart.** Somebody else in
   the household may have added things. Do not clear them, and do not count them as yours.
4. Stop at the cart. Do not open checkout. Tell them what to click and roughly what it
   costs.
5. List every substitution and every item you could not find. An unfound item that goes
   unmentioned becomes a missing ingredient on a night they were counting on.

## Variant 3: grocery delivery, no browser access

Produce the list in the order their app wants it, and say plainly that you cannot add the
items yourself in this environment. Do not pretend to have staged something.

## Variant 4: a meal-delivery or prepared-food service

These have a menu that changes weekly and a hard cutoff. Both matter.

**Reading the menu.** Use only what you can actually read: a menu the household pasted, or
a public page you can fetch. If you cannot read this week's menu, say so and skip that
section entirely. **Never guess at what is on a menu.** A fabricated entrée wastes a real
order deadline, and it is the fastest way to lose a household's trust in the whole system.

**Ranking.** Offer five to eight entrées and three or four sides, numbered, with a proposed
quantity on each. Rank against what they have ordered before: repeat what scored, vary the
proteins, keep the reliably kid-eaten items in the higher quantities.

**Minimums and box sizes.** Sum the picks against the minimum before building anything. If
they are short, say by how much and offer two additions. If they are over, say so and ask.
Never add an item nobody chose in order to clear a minimum.

**The cutoff is the deadline in the proposal header.** Missing it costs a week, so it goes
at the top, not the bottom.

## The shared household list

If the household keeps one, read it every run and fold its items into the shopping list
under their own heading, so they can see what came from where.

**Never check items off it.** They may not shop for hours, and someone else may be adding
to it right now. Clearing a shared list before the shopping happened destroys household
state that exists nowhere else. Check things off only when they explicitly ask, after they
have bought them.

---

## What "done" looks like

The last message of a weekly run says four things, in this order:

1. What is in the list or cart, and the rough total.
2. Every substitution you made.
3. Everything you could not find or could not read.
4. What they do next, in one sentence, with the actual button or the actual store.

Then stop. Do not offer to check out. Do not ask if they want you to place the order.
