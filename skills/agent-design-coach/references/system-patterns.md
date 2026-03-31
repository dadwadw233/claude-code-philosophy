# System Patterns

Use these patterns as starting points, not as rigid templates.

## Pattern 1: Guided copilot

Use when:

- the user stays in the loop
- actions are relatively cheap
- correctness matters more than speed

Shape:

- user provides task and context
- system proposes a plan
- user approves key steps
- system executes bounded actions
- system reports back with evidence

Why it works:

- easier to trust
- easier to debug
- easier to adopt in real teams

## Pattern 2: Tool-using single-agent loop

Use when:

- the task is operational and multi-step
- the system must inspect state between actions
- progress depends on reading results from tools

Shape:

- gather context
- choose an action
- run one or more tools
- verify the result
- continue or stop

This is often the best default for coding agents.

## Pattern 3: Long-running operator

Use when:

- work spans many turns or sessions
- partial progress must survive interruption
- background tasks or follow-up work matter

Requirements:

- durable transcript or task log
- resumable state
- explicit stop and retry rules
- memory maintenance
- good human visibility

Do not build this shape unless the product genuinely needs persistence.

## Pattern 4: Reviewer + executor split

Use when:

- one component should generate changes
- another should critique or verify them
- the task has meaningful failure cost

Benefits:

- cleaner quality control
- stronger separation of concerns
- easier failure analysis

Risks:

- duplicated context
- expensive loops
- performative review with no authority

## Pattern 5: Memory layering

A practical memory stack may include:

- active turn context
- retrieved repo/file context
- durable user/project memory
- temporary working memory for the task
- compacted summaries for old turns

Questions to ask:

- what survives a new turn?
- what survives a new session?
- what can be rewritten?
- what must remain auditable?

## Pattern 6: Permission tiers

A mature agent usually needs more than one permission mode:

- read-only exploration
- write with user confirmation
- preapproved bounded edits
- destructive actions with stronger confirmation

The permission model should align with risk, not with implementation convenience.

## Pattern 7: Product legibility surfaces

Useful surfaces include:

- current plan
- current mode
- pending approvals
- recent actions
- artifacts produced
- transcript or summary
- recoverable task state

If a user cannot tell what the system is doing, trust will collapse before capability does.

