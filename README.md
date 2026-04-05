# Claude Code Philosophy

[![Featured in awesome-agent-skills](https://img.shields.io/badge/featured%20in-awesome--agent--skills-2563eb?style=flat-square)](https://github.com/heilcheng/awesome-agent-skills)

Design better agents.

`claude-code-philosophy` is a public skill and plugin package for developers who want to build agentic systems that are actually useful: controllable, legible, recoverable, and grounded in real product constraints.

It is inspired by the design philosophy behind Claude Code-class agent systems, but written as **vendor-neutral guidance** that can help builders working with Codex, Claude Code, or their own custom agent runtimes.

This project is unofficial. It is not affiliated with Anthropic.

## Why this exists

A lot of agent projects are still too shallow:

- great demo, weak product
- many tools, no capability model
- “memory” with no boundaries
- autonomy with no control surface
- impressive output, fragile runtime

This project exists to push in the other direction.

The core belief is simple: the difference between a toy agent and a useful one is usually **the harness**, not just the model or the prompt.

## What you get

This repository currently ships one installable skill:

- `agent-design-coach`

It helps developers:

- turn fuzzy agent ideas into concrete system designs
- review an existing agent for harness, tool, memory, safety, and UX gaps
- decide whether a workflow needs a real agent or a simpler tool
- make vibe-coded AI projects more disciplined and useful

## What the skill teaches

The skill is built around a few strong principles:

- harness-first design
- explicit tool and permission boundaries
- layered memory instead of one giant blob
- recovery and durability as first-class features
- human control as part of the product
- practical usefulness over fake autonomy

## Quick install

### Codex: install the skill directly

Inside Codex, run:

```text
$skill-installer install https://github.com/dadwadw233/claude-code-philosophy/tree/main/skills/agent-design-coach
```

Then restart Codex.

### Claude Code: install through the repository marketplace

Inside Claude Code, run:

```text
/plugin marketplace add dadwadw233/claude-code-philosophy
/plugin install claude-code-philosophy@claude-code-philosophy
```

Then invoke the installed skill with:

```text
/claude-code-philosophy:agent-design-coach
```

### Manual install

- Codex: copy this repo to `~/.codex/plugins/claude-code-philosophy` and register it in `~/.agents/plugins/marketplace.json`
- Claude Code: copy `skills/agent-design-coach` to `~/.claude/skills/agent-design-coach`

Detailed examples are below.

## Installation details

### Codex: direct skill install

This is the simplest path if you only want the skill itself.

```text
$skill-installer install https://github.com/dadwadw233/claude-code-philosophy/tree/main/skills/agent-design-coach
```

After installation, restart Codex.

### Codex: local plugin install

Clone the repo:

```bash
git clone git@github.com:dadwadw233/claude-code-philosophy.git
```

Copy it into your local plugin area:

```bash
mkdir -p ~/.codex/plugins
cp -R /absolute/path/to/claude-code-philosophy ~/.codex/plugins/claude-code-philosophy
```

Create or update `~/.agents/plugins/marketplace.json`:

```json
{
  "name": "personal-plugins",
  "interface": {
    "displayName": "Personal Plugins"
  },
  "plugins": [
    {
      "name": "claude-code-philosophy",
      "source": {
        "source": "local",
        "path": "./.codex/plugins/claude-code-philosophy"
      },
      "policy": {
        "installation": "AVAILABLE",
        "authentication": "ON_INSTALL"
      },
      "category": "Productivity"
    }
  ]
}
```

Restart Codex. The plugin should appear in the plugin directory.

### Claude Code: marketplace install

This repository includes a Claude Code marketplace manifest at `.claude-plugin/marketplace.json`.

Register the marketplace:

```text
/plugin marketplace add dadwadw233/claude-code-philosophy
```

Install the plugin:

```text
/plugin install claude-code-philosophy@claude-code-philosophy
```

After installation, the explicit slash command is:

```text
/claude-code-philosophy:agent-design-coach
```

### Claude Code: manual skill install

Copy the skill directory:

```bash
mkdir -p ~/.claude/skills
cp -R skills/agent-design-coach ~/.claude/skills/agent-design-coach
```

For a manually installed standalone skill, invoke:

```text
/agent-design-coach
```

## How to use it

### Codex

- `Use $agent-design-coach to turn this coding-agent idea into a real system architecture.`
- `Use $agent-design-coach to review this repo's agent design for harness, memory, permissions, and UX gaps.`

### Claude Code plugin install

- `/claude-code-philosophy:agent-design-coach`
- `/claude-code-philosophy:agent-design-coach Review this coding agent and tell me what is weak in its harness design.`

### Claude Code standalone skill install

- `/agent-design-coach`
- `/agent-design-coach Turn this vibe-coded AI product into a disciplined agent design.`

## What a good output should look like

When the skill is working well, it should produce guidance that includes:

- user value and task framing
- recommended system shape
- harness and execution loop
- tool and permission boundaries
- memory and context strategy
- human control and UX surfaces
- failure modes and evaluation criteria
- immediate implementation next steps

## Repository structure

```text
.
├── .claude-plugin/
│   ├── marketplace.json
│   └── plugin.json
├── .codex-plugin/
│   └── plugin.json
├── .agents/plugins/
│   └── marketplace.json
└── skills/
    └── agent-design-coach/
        ├── SKILL.md
        ├── LICENSE.txt
        ├── agents/
        │   └── openai.yaml
        └── references/
            ├── design-principles.md
            ├── review-rubric.md
            └── system-patterns.md
```

## Design notes

The repository is intentionally layered:

- `SKILL.md` stays procedural and activation-focused
- `references/` contains the heavier philosophy and review material
- `.codex-plugin/` packages the project for Codex
- `.claude-plugin/` packages the project for Claude Code

This keeps the skill lean while still preserving enough depth to be genuinely useful.

## Inspiration

This project draws from:

- Claude Code as an example of a strong agent runtime and product
- official OpenAI/Codex skill and plugin conventions
- Anthropic's public skills and skills marketplace patterns
- the broader Agent Skills ecosystem

## Non-goals

This project is not trying to:

- replicate Claude Code
- provide a universal agent framework
- replace actual engineering judgment
- encourage maximal autonomy by default

It is trying to help developers make better design decisions.
