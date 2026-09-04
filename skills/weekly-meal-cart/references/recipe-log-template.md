# Template: `recipes.md`

The household's dinner log. It does two jobs: it is where proposals come from, and it is
what makes the three-week no-repeat rule possible.

Start it small. Eight dinners is a working log. Thirty is a mature one. A household that
tries to write down everything they know how to cook before starting never starts.

---

```markdown
# Dinners

Last updated {date}. Add a line any time you cook something worth repeating.
The planner reads `last cooked` to avoid proposing the same four dinners forever.

## Weeknight cooks

### Sheet-pan salmon and broccoli
- Time: 30 min · Kid-safe: yes · Set-and-forget: no
- Ingredients: salmon fillets (4), broccoli (2 heads), olive oil, lemon, garlic
- Last cooked: 2026-08-22
- Notes: doubles fine, the 6-year-old eats it plain

### Chicken tacos
- Time: 25 min · Kid-safe: yes · Set-and-forget: no
- Ingredients: chicken thighs (2 lb), tortillas, cheddar, lettuce, sour cream, taco seasoning
- Last cooked: 2026-08-29
- Notes: the reliable one

## Set-and-forget

### Slow-cooker honey garlic chicken
- Time: 10 min prep, 6 hrs low · Kid-safe: yes · Set-and-forget: yes
- Start by: 9:00 AM for a 6 PM dinner
- Ingredients: chicken thighs (2 lb), honey, soy sauce, garlic, rice
- Last cooked: 2026-08-20
- Notes: NEW as of Aug 2026, worked

### Slow-cooker pulled pork
- Time: 15 min prep, 8 hrs low · Kid-safe: yes · Set-and-forget: yes
- Start by: 8:00 AM
- Ingredients: pork shoulder (3 lb), bbq sauce, buns, slaw mix
- Last cooked: never
- Notes: makes enough for a second night

## Adult nights

### Thai green curry
- Time: 40 min · Kid-safe: no · Set-and-forget: no
- Ingredients: curry paste, coconut milk, chicken, green beans, jasmine rice
- Last cooked: 2026-07-30
- Notes: make the kids' pasta alongside

## Retired
### Fish poppers — never again (kids, 2026-08-14)
```

---

## The fields, and why each one is there

**Time.** Checked against the household's weeknight ceiling. A 60-minute recipe never gets
proposed for a Tuesday.

**Kid-safe.** Not a quality judgment. It is whether this dish alone feeds everyone, or
whether it needs a second thing cooked alongside. That difference decides whether it works
on a hard night.

**Set-and-forget.** The single most load-bearing field. It is what a constrained night is
allowed to be. If it is yes, there must be a **start by** time, because the real dependency
is a morning, not an evening.

**Ingredients.** Enough to build a shopping list from. Not a recipe. The recipe can live
anywhere; this log only needs to know what to buy.

**Last cooked.** Updated by the planner after each week. Drives the three-week exclusion.
`never` is a valid and useful value: it marks the dishes that keep getting proposed and
keep not happening, which is a signal worth seeing.

**Notes.** Where the household's actual knowledge accumulates. Who eats it, what it needs
alongside, whether it doubles. Over a year this is the most valuable part of the file.

**Retired.** Do not delete a dish that failed. Record that it failed and when, so it does
not get rediscovered and re-proposed in four months.

---

## Building the starter log

At setup, build it from the dinners they named in the interview: the three the kids eat,
the three the adults miss, and any set-and-forget dish they mention. Fill in what you can
infer, leave `last cooked: unknown`, and tell them the log is a starting point they should
add to whenever they cook something worth repeating.

Do not invent ten more dinners to pad it out. A log of six real dishes the household
actually makes produces better proposals than a log of thirty generic ones, and it is the
difference between a planner that sounds like them and one that sounds like a recipe site.

If a proposal needs a dish that is not in the log yet, write it out in full inline and mark
it clearly as new. If they cook it, it earns a place in the log.
