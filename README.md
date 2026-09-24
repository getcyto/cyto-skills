# Cyto skills

`// we build adaptive systems`

Free skills for Claude Code and Codex, from the Cyto lab. Small files that make your agent make better decisions.

Keep missing data honest. Give a calculation one home. Finish long jobs with
a clear outcome. Carry context into a handoff. Choose web effects that fit.
Check every legal citation before it leaves your hands.

| Skill | What it helps with |
|---|---|
| absent-is-not-zero | Keep zero, missing data, and failed measurements distinct |
| one-place-to-be-wrong | Stop the same business rule drifting across two implementations |
| supervise | Give a long job a measured budget, progress checks, and an ending |
| context-does-not-travel | Make agent handoffs explicit and their results verifiable |
| web-design-patterns | Match layout and motion to the visitor's task |
| cite-gate | Hold legal writing until every cite exists, says it, is still good law, and is in form |

## Install

Clone or download this repo, then open `skills`. Copy the skill
folders you want, including their contents, into the location for your app:

| App | Personal skills folder |
|---|---|
| Claude Code | `~/.claude/skills/` |
| Codex | `~/.agents/skills/` |

Create the destination folder if needed. If a folder with the same name
already exists, compare it before replacing it.

For example, the installed entry should be
`~/.claude/skills/absent-is-not-zero/SKILL.md` or
`~/.agents/skills/absent-is-not-zero/SKILL.md`.
Copy each skill folder, not the outer bundle folder. Keep `techniques.md`
beside `web-design-patterns/SKILL.md`.

These paths work on macOS, Linux, and Windows with WSL. For a project-only
install, use `.claude/skills/` or `.agents/skills/` inside that project.

Installation references:
[Claude Code skills](https://code.claude.com/docs/en/skills) and
[OpenAI skill documentation](https://learn.chatgpt.com/docs/build-skills).

## Try one

In Claude Code:

```text
/absent-is-not-zero review this parser's missing-data handling
```

In Codex CLI or the IDE:

```text
$absent-is-not-zero review this parser's missing-data handling
```

You can also ask your agent to use a skill by name. Start a new session if it
does not appear.

The same files work with either app. Your app controls which tools and agent
capabilities are available. These are instructions, not a background service
or additional permissions. Each skill works on its own.

## Community

These came out of real work, and each one exists because something broke
without it. If a skill saved you, or failed you, open an issue and say how.
New skills are welcome: see CONTRIBUTING.md.

Want one built for your team, wired into your own tools, with the security
done alongside? That's Cyto+: [getcyto.ai](https://getcyto.ai).

From [Cyto](https://getcyto.ai).
