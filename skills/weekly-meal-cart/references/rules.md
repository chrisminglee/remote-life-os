# The rules, and why each one exists

These came out of a weekly dinner system that has run since August 2026. Every rule here
is the scar tissue from a specific failure. Keep the reasoning attached: a rule someone
does not understand is a rule they will quietly drop the first week it costs them
something.

---

## 1. Never buy anything

Build the list. Stage the cart if you can. Then stop, and tell the person what to click.

Never enter a checkout flow, never submit payment, never store or read payment details,
and never place an order "to be helpful."

**Why:** groceries are the one household decision where being wrong is expensive, slow to
reverse, and lands in somebody's kitchen. A staged cart is fully reversible. A placed
order is not. The five minutes the person spends checking out is also the last quality
check on everything upstream: they see the total, they see the substitutions, they catch
the thing you got wrong.

There is a second reason that matters more over time. A system that spends money without
asking is a system people stop trusting, and a meal planner only works if it is used every
week for years.

## 2. Never clear a shared list or cart

If the household keeps a shared shopping list, read it. Do not check items off it, and do
not empty a shared cart to make room for yours.

**Why:** someone else in the house is probably using it right now. Clearing a list before
the shopping actually happened destroys household state that nobody wrote down anywhere
else. Check items off only after the person confirms they bought them, and only when they
ask.

## 3. A calendar block between roughly 4 and 8 PM is a constraint, not a question

When the calendar shows soccer at 5:30, that night does not "probably not need a cook." It
is not allowed to be offered a from-scratch evening cook at all. It gets a set-and-forget
option (something started in the morning) or a named order-in.

**Why:** this is the single highest-value rule in the system, and it was learned the
expensive way. A from-scratch plan proposed for a busy night dies, every time, because
there was never a window to cook it in. Then dinner becomes whatever is fastest at 6:45,
which is the exact failure the whole ritual exists to prevent. Asking "will you have time?"
just moves the optimism from the planner to the person, who is answering on Thursday about
a Tuesday they cannot yet feel.

Weekends get the same treatment by default. Saturday and Sunday evenings look free on a
calendar and are almost never free in a house with kids.

## 4. Order-in is a planned choice, proposed by name

"Order in" is not a fallback and not a failure state. It is an option, and it gets named:
the actual pizza place, the actual Thai place. It appears in the proposal next to the cook
options, with equal weight.

**Why:** most people do not mind ordering in. What they mind is ordering in *because there
was no plan*, at 6:45, while everyone is asking what is for dinner. Naming it in advance
converts the same dinner from a small failure into a chosen night off. Nothing about the
food changes. The whole difference is whether it was decided.

## 5. Menu of options, never a single answer

Two options per open night. The person picks.

**Why:** a planner that hands down one answer is a planner that gets overridden and then
abandoned, because it does not know about the mood, the leftovers, or the fact that
somebody had a big lunch. Two options preserve the household's authority and still remove
the hard part, which is generating candidates from nothing at 6 PM.

The one exception is a same-night decision. When it is already 4 PM on an unplanned
Saturday, offering a menu is another job. Offer one thing.

## 6. Closed nights get confirmed, not re-offered

If the person has already said "Friday is my mother's birthday dinner," that night is
closed. Repeat it back as part of the plan. Do not propose two alternatives for it.

**Why:** re-offering a decided night reads as not listening, and it trains people to skim
the proposal instead of reading it.

## 7. A set-and-forget cook's real dependency is a morning, not an evening

When a slow-cooker night gets picked, three things have to be true, and it is never the
recipe that fails:

1. The ingredients are actually in the house. Not on a list. In the house.
2. The start-by time is still ahead, not behind.
3. That start-by time comes *after* the shop that brings the ingredients.

So the shopping is part of the pick, not an afterthought. And on the day, check the food
was bought before cheerfully sending the recipe.

**Why:** in the original system the slow cooker was proposed almost every week and cooked
once in a month. It did not fail because the recipe was bad. It failed once because the
night lost out to pizza, and once because the chicken thighs were on the list and never
actually purchased. The plan was fine. The morning was the problem.

Point three is the one a planner gets wrong on its own. Proposing an 8 AM start for meat
collected at 9, or a morning start on a night whose groceries arrive two days later, is
the same failure committed by the system that was built to prevent it.

## 7a. An allergy is absolute, and it extends to takeout

An allergy is the only true filter in the system. It applies to every proposal, and it
does not stop at the kitchen door: a restaurant whose cross-contact the household has not
cleared does not get proposed on a night the allergic person eats.

Hold it back and say why in one line. Never drop it silently.

**Why:** the households that most need this system are the ones where dinner is already
complicated, and an allergy is the most common complication. A planner that names a Thai
place to a family with a tree-nut child has broken its hardest rule while looking helpful,
and it will only be caught by the parent who is already doing the checking. Saying "this
place is off the board until you ask them" is more useful than the option would have been.

## 7b. A soft preference demotes a dish, it does not ban it

"Nobody loves fish" and "one of us does not eat pork" are ranking inputs, not filters. The
dish drops down the order. It still appears when it is the right answer, and when it does,
say so on the line: "pork, so one of you sits it out."

**Why:** treating every preference as a ban shrinks the rotation to nothing within a month,
and treating it as invisible produces a proposal somebody quietly ignores. Naming it on the
line lets the household make the call with one glance, which is the whole design.

## 8. Nothing cooked in the last three weeks

Build the exclusion list from the **picks recorded in the last three week files**, since a
picked dish is the best available evidence of a cooked one. Keep `last cooked` in the
recipe log updated from the same source.

**Why:** without this, a planner converges on the same four dinners, because those are the
ones with the best signal. Three weeks is long enough that repetition stops being obvious
and short enough that the rotation does not sprawl past what the household can actually
shop for.

**On a household's first weekly run this rule cannot run at all,** because there are no
week files yet and the starter log says `last cooked: unknown` on every line. That is fine.
Say it on the did-not-run line and let the rule start working in week two. What is not
fine is a proposal that implies an exclusion happened when nothing was excluded.

## 9. Loud errors beat false success

If the calendar was not available, say so. If the menu could not be read, say so. If the
shared list would not load, say so, in plain words, in the output, every time.

**Why:** a proposal that quietly skipped the calendar looks exactly like a proposal for a
clear week. The person acts on it, and finds out on Tuesday. A planner that hides its gaps
is worse than no planner, because it converts a known unknown into an unknown one.

Never report a clean run that was not clean.

## 10. Never invent a menu item, a real price, or a recipe the household "already has"

If a meal-delivery menu could not be read, skip that section. Do not guess at what is on
it this week. If a recipe is being written fresh rather than pulled from the household's
own log, label it **NEW, never made here**, in the log and in the proposal both.

Costs are the one place where a number is still useful without being knowable. Give a
range, and label it as your estimate: "roughly $95 to $125, my estimate, not a store
price." That is honest and it still lets a budget flag do its job. A precise figure
presented as if you had priced the cart is the forbidden version.

**Why:** a fabricated menu item wastes a real order deadline. A recipe presented as "your
usual" when nobody has made it before quietly erodes the thing that makes the whole system
work, which is that the person believes what the planner tells them.

Expect this rule to collide with the requirement for a set-and-forget option every week,
because most households own the equipment and have no dish for it. The label is the
resolution. Write the dish, mark it NEW, and never let it drift into the log as theirs
until they have actually made it.

## 11. Two blocks, and only the near one drives the shopping

The **near block runs from tonight through the end of the coming weekend**, and it gets
detail. Everything after that is the far block, and it gets an outline. Buy groceries only
for the near block.

Note that the near block is not a fixed length. A Thursday ritual makes it four days; a
Sunday ritual makes it eight. Both are correct. What defines it is the weekend boundary,
because a household plans in weeks and the weekend is where a week's cooking capacity
actually sits.

**Why:** food bought ten days early is food thrown away. Splitting the horizon lets the
person see far enough ahead to catch a bad week, without committing produce to it. The far
block is marked provisional, and it firms up in the next cycle.

## 12. Write only inside the household's own folder

Everything the system generates lives in one folder the person chose. Never write
elsewhere on their machine, and never put anything sensitive in it.

**Why:** obvious, and worth stating anyway. A tool that scatters files is a tool people
delete.
