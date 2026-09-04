# Remote Life OS — workflows

The systems I actually run, packaged so you can run them too.

Each one started as something I built for my own household or my own work, then got
stripped of everything specific to me. No workflow here is theoretical. Every one is
described in an issue of [Remote Life OS](https://www.remotelifeos.com), and the write-up
links back to the thing it explains.

---

## Workflows

| Workflow | What it does | Install | Written up in |
|---|---|---|---|
| [weekly-meal-cart](skills/weekly-meal-cart/) | Turns your calendar into the week's dinners and a shopping list. Interviews you once, then runs weekly. Never buys anything. | `skills/weekly-meal-cart/` | The AI plans dinner and fills the cart |

More get added as they ship. If you want to know when, the newsletter is the list.

---

## How to install a workflow

**As a Claude Code skill.** Copy the folder into your skills directory:

```
git clone https://github.com/chrisminglee/remote-life-os.git
cp -r remote-life-os/skills/weekly-meal-cart ~/.claude/skills/
```

Restart Claude Code. Then just describe what you want in plain language. Skills trigger on
what you say, not on a command, so "help me plan dinners for next week" is enough.

**As a plain prompt.** Every workflow has a `STARTER-PROMPT.md` you can paste into any
chat model with no install at all. You lose the memory between weeks and keep everything
else.

**As a project.** On claude.ai, paste the `SKILL.md` into a Project's instructions. The
skill is written to work that way, including the parts that assume no filesystem.

---

## What these will never do

Every workflow here is built on the same line: it prepares the decision, you make it.

- Nothing places an order, enters a checkout, or touches payment.
- Nothing sends an email or a message as you without showing you the text first.
- Nothing deletes or clears shared state, like a household shopping list, that someone
  else might be using.
- Everything says out loud which parts of a run failed. A workflow that hides its gaps is
  worse than no workflow.

---

## Contributing

These are personal systems, so I am not looking for feature pull requests. Bug reports and
"this broke for my household because X" are genuinely useful, and the fastest way to make
the next version less specific to me. Open an issue.

MIT licensed. Take any of it.
