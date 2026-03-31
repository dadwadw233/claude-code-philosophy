---
name: "agent-design-coach"
description: "Help developers design or review useful, controllable, extensible agentic systems and products. Use when the user is designing an agent architecture, harness, tool system, memory strategy, permission model, interaction loop, recovery plan, or evaluation strategy, or when they want to turn a vague vibe-coded agent idea into a disciplined product plan. Do not use for simple code generation, generic brainstorming, or purely cosmetic UI critique."
---

# Agent Design Coach

Design agents as products, not as prompt demos.

This skill helps you turn fuzzy agent ideas into systems that are:

- useful to a real user
- controllable by humans
- explicit about tools and permissions
- resilient across long-running work
- understandable enough to debug and improve

## What to optimize for

Prefer systems that are:

- legible over magical
- composable over monolithic
- recoverable over one-shot
- bounded over all-powerful
- product-useful over benchmark-impressive

## Quick start

1. Identify the user, the job, and the failure cost.
2. Decide whether the system needs a real harness or only a workflow/script.
3. Define the execution loop before adding more features.
4. Treat tools, memory, permissions, and recovery as first-class design surfaces.
5. End with a concrete design, risks, and an evaluation plan.

## Output contract

When this skill is active, prefer delivering outputs with these sections:

1. Goal and user value
2. Recommended system shape
3. Harness and execution loop
4. Tools and capability boundaries
5. Context and memory strategy
6. Safety, permissions, and recovery
7. UX and human control
8. Failure modes and evaluation
9. Immediate next implementation steps

If the user asks for a review, prioritize flaws, weak assumptions, and missing controls before praise.

## Workflow

### 1. Start from the user job, not the model

Clarify:

- who the user is
- what task they are actually delegating
- what “good” looks like
- what damage happens when the agent is wrong, slow, or overconfident

If the task is not worth repeated delegation, challenge whether an agent is needed at all.

### 2. Decide the minimum viable harness

Do not jump from “call a model” to “full autonomous agent.”

Pick the smallest useful runtime shape:

- one-shot assistant
- guided multi-step copilot
- tool-using loop
- long-running agent with persistence and recovery
- multi-agent system

Only escalate complexity when the product actually needs it.

For deeper framing, read `references/design-principles.md`.

### 3. Design the core loop before edge features

Define:

- what the system reads
- how it reasons or plans
- what actions it can take
- how it verifies work
- when it stops, retries, escalates, or asks for help

Good agent systems usually have a small, explicit loop. They do not hide the loop behind vague “AI orchestration” language.

### 4. Treat tools as governed capabilities

For each tool or action surface, specify:

- what the tool is for
- what inputs it accepts
- what outputs it returns
- what permissions gate it
- what can go wrong
- how the system checks whether the action succeeded

Do not treat tools as raw power-ups. Treat them as capability contracts.

### 5. Design memory on purpose

Separate at least these concerns when relevant:

- conversation context
- durable working memory
- reusable user or project memory
- retrieval or file grounding
- summarization and compaction

The question is not “does the agent have memory?” The question is “which facts should survive which boundary, and why?”

For patterns, read `references/system-patterns.md`.

### 6. Make human control explicit

Design:

- approval points
- visibility into pending actions
- interruption and override behavior
- recovery from partial completion
- logs, transcripts, or summaries that let a human audit what happened

The user should never feel that the system is doing mysterious work in a black box.

### 7. Plan for failure, not just happy-path output

Always analyze:

- missing context
- wrong tool choice
- stale memory
- excessive autonomy
- repeated loops with no progress
- unsafe destructive actions
- hidden coupling between components

If the design cannot fail safely, it is not ready.

### 8. End with evaluation

Define how the design will be judged:

- task success
- user trust
- latency
- cost
- reversibility
- recovery quality
- operator burden

If there is no evaluation plan, the design is still rhetorical.

For a structured scoring lens, read `references/review-rubric.md`.

## Anti-patterns

Push back on these patterns when you see them:

- “just add more tools”
- “just give the model more context”
- “the agent will figure it out”
- “memory” as one giant undocumented dump
- no permission model for destructive actions
- no transcript or recovery path
- many clever components with no clear user value
- multi-agent designs used to hide confusion rather than reduce it

## Style guidance

Be pragmatic and specific.

- Prefer concrete architecture and operating decisions over slogans.
- Prefer tradeoffs over absolutist rules.
- Prefer smaller systems with clear control over larger systems with vague autonomy.
- If the user is overbuilding, say so.

## References

- Core philosophy: `references/design-principles.md`
- Concrete patterns: `references/system-patterns.md`
- Review checklist: `references/review-rubric.md`

Load only the reference files you need. Keep the answer operational.

