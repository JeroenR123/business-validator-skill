# Business Validator — a Claude Code skill

Validate a business idea by running it through a team of **6 specialized agents in parallel**, then put them in a room to argue. The result is an honest GO / PIVOT / KILL verdict and — for ideas that survive — a polished business plan.

It's built as a [Claude Code](https://claude.com/claude-code) skill. Point it at an idea folder and it orchestrates the whole thing.

## The team

| Agent | Role |
|---|---|
| 🔍 Market Scout | Sizes the market, maps competitors, finds the wedge |
| 🧨 Skeptic | Hunts for the fatal flaw that kills the idea |
| 👤 Customer | Channels the buyer — is the pain real and acute? |
| ♟️ Strategist | Moat, positioning, go-to-market |
| 💰 Financials | Unit economics, pricing, path to profitability |
| 🏗️ Architect | What it takes to actually build it |

A 7th agent, the **Assembler**, compiles the final business plan — but only for ideas that earn a GO.

## How it works

```
Idea folder
   │
   ├─ Round 1  All 6 agents analyze in parallel        → each writes a verdict
   ├─ Round 2  Cross-Fire: agents challenge each other  → weak ideas die here
   ├─ Round 3  Verdict: GREEN (go) / YELLOW (pivot) / RED (kill)
   └─ Assembly Business plan (GO only)
```

## Install

Copy the `validate` folder into your Claude Code skills directory:

```bash
# Clone, then copy the skill into your personal skills folder
git clone https://github.com/JeroenR123/business-validator-skill.git
cp -r business-validator-skill/validate ~/.claude/skills/
```

Or drop it into a project's `.claude/skills/` to share it with a repo.

## Use

In Claude Code, just ask:

```
Validate the idea in Ideas/my-startup
```

The skill triggers on phrases like *"validate this idea"*, *"analyze my business idea"*, *"run the validator"*, or *"stress-test this concept"*.

### Setting up an idea folder

Create a folder per idea with at minimum a `Pitch.md` covering:

- **The problem** — and who has it
- **The solution** — what you'd build
- **The founder** — why you

The more context you give it, the sharper the analysis. All agent outputs are written back into the idea folder.

## License

MIT — see [LICENSE](LICENSE). Share it, fork it, make it meaner.
