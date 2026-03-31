# Claude Code Philosophy

`claude-code-philosophy` is a public skill and plugin package for people who want to build better agents.

It is inspired by what makes Claude Code-class systems feel strong in practice: coherent harnesses, clear tool contracts, memory discipline, explicit permissions, recoverability, and product legibility.

This is **not** an official Anthropic project and it is **not** a clone of Claude Code. It is an opinionated, vendor-neutral attempt to distill the design philosophy behind useful agentic systems into a reusable skill.

## What this project gives you

The core deliverable is one skill:

- `agent-design-coach`

That skill helps you:

- turn vague agent ideas into concrete system designs
- review an existing agent for harness, tool, memory, UX, and safety gaps
- push back on overbuilt or under-specified agent architectures
- design agents as products rather than prompt demos

## Philosophy

This project is built around a few hard beliefs:

- the harness matters more than the prompt
- tools are governed capabilities, not raw power
- memory should be layered and intentional
- recovery is a first-class feature
- human control is part of the product
- useful systems beat flashy autonomy

If you want more detail, start with:

- `skills/agent-design-coach/SKILL.md`
- `skills/agent-design-coach/references/design-principles.md`

## Install in Codex

### Fastest path: install the raw skill

Inside Codex, run:

```text
$skill-installer install https://github.com/dadwadw233/claude-code-philosophy/tree/main/skills/agent-design-coach
```

Then restart Codex.

### Plugin path: install locally for development or power use

Clone this repo somewhere on your machine:

```bash
git clone git@github.com:dadwadw233/claude-code-philosophy.git
```

Copy the repo into your local Codex plugin area:

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

## Install in Claude Code

### Marketplace path

This repository includes a Claude Code marketplace manifest at `.claude-plugin/marketplace.json`.

Add the repository as a marketplace:

```text
/plugin marketplace add dadwadw233/claude-code-philosophy
```

Then install the plugin:

```text
/plugin install claude-code-philosophy@claude-code-philosophy
```

### Manual skill path

If you prefer a manual install, copy `skills/agent-design-coach` into your Claude skills directory as `~/.claude/skills/agent-design-coach`.

## How to use it

Example prompts:

- `Use $agent-design-coach to turn this coding-agent idea into a real system architecture.`
- `Use $agent-design-coach to review this repo's agent design for harness, memory, permissions, and UX gaps.`
- `Use $agent-design-coach to redesign this vibe-coded AI product into something more controllable and useful.`
- `Use $agent-design-coach to decide whether this workflow needs a true agent or just a simpler tool.`

## Repository layout

```text
.
├── .claude-plugin/
│   └── marketplace.json
├── .codex-plugin/
│   └── plugin.json
└── skills/
    └── agent-design-coach/
        ├── SKILL.md
        ├── agents/
        │   └── openai.yaml
        └── references/
            ├── design-principles.md
            ├── review-rubric.md
            └── system-patterns.md
```

## Design notes

The skill is intentionally split into layers:

- `SKILL.md` stays concise and procedural
- `references/` holds the deeper philosophy and review framework
- product-specific metadata lives in `agents/openai.yaml`

That keeps the invocation surface lean while preserving richer material when it is actually needed.

## Inspiration

This project is heavily inspired by:

- Claude Code as an agent runtime and product
- official OpenAI/Codex skills and plugin design conventions
- the emerging Agent Skills ecosystem

But the wording and guidance here are aimed at broad agent builders, not only one vendor’s stack.

## License

MIT

