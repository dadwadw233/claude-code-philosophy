# Design Principles

This skill is inspired by systems like Claude Code, but it intentionally expresses the lessons as vendor-neutral principles.

## 1. Start from repeated user value

An agent is justified when a user wants to delegate a job repeatedly, not when a demo looks impressive once.

Ask:

- What job is being delegated?
- Why is delegation useful?
- What parts require judgment versus execution?
- What happens when the system is wrong?

If there is no repeated user value, prefer a simpler tool.

## 2. The harness matters more than the prompt

Strong agent systems are not “one great prompt.” They are a harness:

- a runtime loop
- state boundaries
- tool contracts
- permission rules
- memory rules
- retry and recovery behavior
- human control surfaces

When a system feels unusually capable, it is often because the harness is coherent.

## 3. Request assembly is a product decision

Before a model acts, the system decides:

- what context enters the turn
- what instructions are durable
- what memory is injected
- what tool affordances are exposed
- what runtime state is visible

This assembly layer is where product intent becomes machine behavior. Treat it as architecture, not glue code.

## 4. Tools are capability boundaries

Each tool should represent a bounded, inspectable ability.

Good tool design makes it obvious:

- when a tool should be used
- what risk it carries
- what evidence of success exists
- whether the result can be rolled back

Bad tool design turns the agent into an opaque shell wrapper with no safety or product semantics.

## 5. Memory is not one thing

Different memory layers solve different problems:

- turn context for local reasoning
- project memory for durable guidance
- user memory for personalization
- working memory for long tasks
- summaries and compaction for context pressure

The mistake is to collapse all of these into one undocumented blob.

## 6. Human control is part of the product

Useful agents let humans:

- see what the system is about to do
- approve or reject risky actions
- interrupt bad trajectories
- recover from partial failure
- understand what happened after the fact

This is not a secondary UX layer. It is part of the system’s safety and trust model.

## 7. Legibility beats fake autonomy

A system that is slightly less autonomous but much easier to understand, debug, and trust is often the better product.

Push back on architecture that only increases the appearance of sophistication:

- unnecessary multi-agent splits
- uncontrolled memory growth
- too many tools without policy
- invisible background work
- no clear stop conditions

## 8. Recovery is a first-class feature

Long-running agentic work creates partial state:

- files changed
- tickets opened
- plans drafted
- tool calls made
- memory updated

Systems should be designed to resume, inspect, and recover from those states rather than pretending every run is stateless.

## 9. Evaluate the system, not just the answer

An agent can return a good-looking answer while still being a bad product.

Evaluate:

- usefulness
- correctness
- controllability
- safety
- cost
- latency
- operator burden
- recoverability

The right question is not just “did it answer?” but “would you want to run this every day?”

