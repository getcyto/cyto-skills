# Cyto skills

`// we build adaptive systems`

Free skills for Claude Code and Codex. Small files that help your agent make better decisions. Each one exists because something broke without it.

| Skill | What it does |
|---|---|
| [absent-is-not-zero](skills/absent-is-not-zero) | Keeps zero, missing data and failed measurements distinct |
| [one-place-to-be-wrong](skills/one-place-to-be-wrong) | Stops one business rule drifting across two implementations |
| [supervise](skills/supervise) | Gives a long job a budget, progress checks and a clear ending |
| [context-does-not-travel](skills/context-does-not-travel) | Makes agent handoffs explicit and their results verifiable |
| [web-design-patterns](skills/web-design-patterns) | Matches layout and motion to the visitor's task |
| [cite-gate](skills/cite-gate) | Holds legal writing until every cite exists, says it, is still good law and is in form |

## Install

Claude Code:

```sh
git clone https://github.com/getcyto/cyto-skills.git
mkdir -p ~/.claude/skills && cp -R cyto-skills/skills/* ~/.claude/skills/
```

Codex:

```sh
git clone https://github.com/getcyto/cyto-skills.git
mkdir -p ~/.agents/skills && cp -R cyto-skills/skills/* ~/.agents/skills/
```

Want only one? Copy that one folder. For a single project, copy into `.claude/skills/` or `.agents/skills/` inside the project instead. If a skill with the same name is already installed, compare before replacing.

Docs: [Claude Code skills](https://code.claude.com/docs/en/skills) · [Codex skills](https://developers.openai.com/codex/skills)

## Try one

```text
/absent-is-not-zero review this parser's missing-data handling
```

In Codex, use `$absent-is-not-zero`. You can also just ask your agent to use a skill by name. Start a new session if it does not show up.

These are plain instructions: no background service and no extra permissions.

## Community

If a skill saved you, or failed you, [open an issue](https://github.com/getcyto/cyto-skills/issues) and say how. New skills are welcome: see [CONTRIBUTING.md](CONTRIBUTING.md).

Want one built for your team, wired into your own tools, with the security done alongside? That's Cyto+ at [getcyto.ai](https://getcyto.ai).

MIT licensed. From [Cyto](https://getcyto.ai), an Adaptive Intelligence Systems company.
