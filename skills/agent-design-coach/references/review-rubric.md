# Review Rubric

Use this rubric when reviewing an agent or agentic product.

Score each area as:

- Strong
- Adequate
- Weak
- Missing

## 1. User value

- Is the delegated job real and repeated?
- Is the system solving an actual user pain point?
- Is the level of autonomy justified?

## 2. Harness quality

- Is there a clear execution loop?
- Are stop, retry, and escalation conditions defined?
- Is state flow understandable?

## 3. Tool design

- Are tools bounded and purposeful?
- Are input/output contracts clear?
- Are success and failure observable?

## 4. Memory design

- Are memory layers separated by purpose?
- Is retention intentional rather than accidental?
- Is compaction or summarization handled explicitly?

## 5. Permissions and safety

- Are risky actions gated?
- Is destructive behavior treated specially?
- Are there clear human approval points?

## 6. UX and control

- Can the user see what the system is doing?
- Can the user interrupt or redirect it?
- Does the system communicate uncertainty and state clearly?

## 7. Recovery and durability

- Can work survive interruption?
- Are outputs, logs, or transcripts inspectable?
- Can partial work be resumed or audited?

## 8. Evaluation

- Is there a concrete success metric?
- Are cost and latency considered?
- Are failure cases tested rather than assumed away?

## 9. Product honesty

- Is the design legible?
- Does it avoid overstating autonomy?
- Does it hide complexity behind hype words?

## Final judgment

A good final review should name:

- the strongest design decisions
- the most dangerous weak points
- the missing controls
- the smallest changes that would most improve the system

