# Template: `meal-system.md`

This is the file setup writes. It is the household's own rules, in their words, and it is
the first thing every later run reads.

Write it in their language, not the template's. If they said "Tuesdays are a write-off,"
that sentence goes in the file. Generic phrasing here means a generic proposal later.

Only the `## Learned` section is ever appended to automatically. Everything else belongs
to the household, and they edit it by hand.

---

```markdown
# {Household name} — weekly meal system

Generated {date} by weekly-meal-cart. Files live in `{path}`.
Edit anything here by hand. The planner appends only under "Learned" and never
rewrites your lines.

## The system in one paragraph

{Two or three sentences, in their words, describing what happens each week: which nights
come from where, when the shopping happens, and what the ritual is for. This is the
paragraph that orients anyone reading the file cold, including the planner. Write it last,
after the rest of the file exists.}

## Household

- {N} adults, {N} kids ({ages})
- Cooking for {N} at dinner on a normal night
- {Anything about who cooks, or who is home}

## Hard rules

- **Allergies:** {list, or "none"}. Never propose anything containing these. Extends to
  takeout: {which of their named places are cleared, which are held back and why}.
- **Never buy.** The planner builds the list or stages the cart. {Name} checks out.
- **Event nights** (anything blocking 4 to 8 PM): set-and-forget or a named order-in only.
- **Weekend rule:** Saturday {on/off}, Sunday {on/off}. {Their own reason, in their words.}
  Record it per day; a split answer is common and it is the most specific thing they said.
- **Soft preferences** (demote, never ban): {list}. When one gets proposed anyway, say so
  on the line.
- {Any other absolute: meatless Mondays, whatever they said}

## The week's shape

- Realistic from-scratch cooks per week: {N}
- Weeknight ceiling: {N} minutes
- Set-and-forget equipment: {slow cooker / pressure cooker / sheet pan / none, so
  make-ahead instead}
- {Anything they said about which nights are good for cooking}

## Calendar

- Recurring busy evenings: {Tue soccer 5:30, Thu piano 4:30, one parent late Wednesdays}
- Shared each week by: {pasting it / a connected calendar / telling the planner}
- Treated as constrained: anything blocking roughly 4 to 8 PM, plus {Sat and Sun}

## Food sources

**Meal delivery:** {name, or "none"}
- Covers: {which nights}
- Menu posts: {day} · Order cutoff: {day and time} · Delivery: {day} · Minimum: {amount}

**Groceries:** {store}, {delivery / pickup / in person}
- Shop or order by: {day}
- {App or storefront, if any}

**Order-in defaults:** {Place A (pizza), Place B (quick), Place C (the treat)}

**Weekly staples:** {milk, bananas, bread, rice, ...}

**Shared household list:** {app or "none"} — read every run, never cleared

**Budget flag:** {amount per week, or "none"} — mentioned when exceeded, never enforced

## The weekly ritual

- Proposal lands: {day, time}, via {chat / a file / an email you send yourself}
- You reply with picks like: `{Thu A, Fri B, Sat A}` or `{1, 3, 4}`
- Then the planner produces {the shopping list / the staged cart} and stops
- {Name} buys it

The planner does not: place orders, check out, clear your shared list, or decide a night
you have already decided.

## Recipe source

{`recipes.md` in this folder / the path or doc they named}

## Learned

_Dated notes appended by the planner. Newest at the bottom._

- {date} — Setup completed.
```

---

## Notes on filling it in

**The one-paragraph section is the most important line in the file.** It is what a fresh
session reads to understand this household in five seconds. Write it concretely: "Home
delivery covers Monday through Wednesday, we cook Thursday and Friday, and the weekend is
slow cooker or takeout" beats "we plan our meals weekly."

**Keep perishable facts out of it.** Specific nights, a specific store, a specific practice
schedule: those live in the Calendar and Food sources sections, where learn mode is allowed
to update them. The paragraph belongs to the household and never gets rewritten, so
anything inside it that can change will eventually be wrong and nothing will be able to fix
it. Describe the shape of their week, not this month's version of it.

**Put the allergy in two places** if there is one: the Hard rules section, and a note next
to the affected recipes in `recipes.md`. Redundancy is correct here.

**If the household turned the weekend rule off,** record that they turned it off and the
date, not just its absence. A future run should be able to tell the difference between "we
decided against this" and "nobody ever asked."

**Never put a payment detail, an account, or a password in this file.** If a service needs
a login, the file says which service, and nothing else.
