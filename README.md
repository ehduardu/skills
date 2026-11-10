# skills

Agent skills I use every day, shared with the world.

Each skill is a folder with a `SKILL.md` file, in the open [Agent Skills](https://agentskills.io) format. They work in Claude Code, Codex, Cursor, and any other agent that reads that format.

## Skills

| Skill | What it does |
| --- | --- |
| [brio](skills/brio/SKILL.md) | Explains a topic until you truly understand it: a change, a piece of code, a flow, a concept, or one word. |

### brio

> "Como pode o cara escrever uma coisa que eu não entenda?" — Clóvis de Barros Filho

Brio is being personally offended by non-understanding. When you do not understand, the text failed, and the writer repairs it.

The agent works in four steps:

1. **Ground truth.** It studies the topic first: it reads the real code, diff, or sources before it explains anything.
2. **Explain.** It writes one explanation in short, plain sentences. Each term has a definition. Each abstraction comes with its real excerpt.
3. **Doubts.** You ask about what you did not understand. It answers that doubt alone, with precision.
4. **Close.** When you understand, it offers to save a learning note with the explanation and your doubts.

```
/brio the retry logic in src/queue/worker.ts
/brio idempotency
/brio
```

With no topic, brio explains the agent's latest message or change in the conversation.

## Install

### With the `skills` CLI

The [`skills`](https://github.com/vercel-labs/skills) CLI copies a skill to the right folder for your agent:

```sh
# choose interactively
npx skills add ehduardu/skills

# one skill, one agent, available in all your projects
npx skills add ehduardu/skills --skill brio -a claude-code -g
```

Use `-a codex`, `-a cursor`, or another agent name. Without `-g`, the skill is installed in the current project only.

### By hand

Clone the repository and copy the skill folder to the folder your agent reads:

```sh
git clone https://github.com/ehduardu/skills.git
cp -r skills/skills/brio ~/.claude/skills/
```

| Agent | For all your projects | For one project |
| --- | --- | --- |
| Claude Code | `~/.claude/skills/` | `.claude/skills/` |
| Codex | `~/.agents/skills/` | `.agents/skills/` |
| Cursor | `~/.cursor/skills/` | `.cursor/skills/` or `.agents/skills/` |

## Use

| Agent | How to start a skill |
| --- | --- |
| Claude Code | `/brio <topic>` |
| Cursor | `/brio <topic>` in Agent chat |
| Codex | `$brio <topic>`, or pick it from `/skills` |

Brio starts only when you ask for it. The agent does not start it on its own.

## License

[MIT](LICENSE)
