---
name: perspective-protocol
description: Multi-perspective research and review method adapted from Stanford's STORM. Derives 4 to 6 non-overlapping perspectives from the topic, has each ask sourced questions, probes the weak answers, maps the disagreement, then synthesizes and peer reviews. Use when the user asks to stress-test, pressure-test, or get multiple perspectives on a strategy document, positioning decision, financial or legal choice, architecture, or any high-stakes decision or draft, or mentions the Perspective Protocol, a committee review, or STORM. Not for factual lookups, single-right-answer tasks, or short outputs.
license: MIT
---

# The Perspective Protocol

A portable adaptation of Stanford's STORM method. It buys coverage: it widens the question surface before committing to an answer, so gaps surface while they are still cheap to fix. It is not a debiasing tool, and its output is pre-writing input, not a finished verdict.

## Three load-bearing requirements

Drop any one and the result is roleplay with headings.

1. **Perspectives derived from the topic**, not from a stock list
2. **Retrieval** grounding claims in real sources
3. **Iteration** in the questioning, not one pass

If no search or retrieval tool is available, say so at the top of the output and label every finding as unsourced. Never present ungrounded output as researched.

## When to run it

Run it when the cost of missing an angle is high and the topic contains real disagreement: strategy documents, positioning decisions, financial or legal choices with irreversible consequences, anything the user will defend to someone who knows more than they do.

Skip it for factual lookups, tasks with one right answer, drafting where the user already knows what they think, and anything under about 500 words of output. If the request does not justify the overhead, say so and offer the fallback panel or a direct answer.

## Before starting

Confirm two inputs. Ask if either is missing:

- **Topic**: what is being examined
- **Artifact and stakes**: what the user is deciding or producing, and what it costs to get wrong

## The protocol

### Stage 0: Derive the perspectives

The step that matters most. Do not start from a stock panel.

Identify the 4 to 6 perspectives that would produce the most non-overlapping questions about the topic. Name the actual live disagreements in the domain: who argues with whom, and about what. A perspective earns a slot only if it asks questions the others would not think to ask.

For each perspective give: the label, the one thing it cares about most, and the question it would open with.

Then interrogate the list:

- Two roles that would ask the same opening question are one perspective. Cut one and find a real one.
- A perspective that cannot produce a question capable of changing the user's mind gets cut.
- Different job titles pointed at the same concern do not count as different perspectives.
- A panel where most perspectives are hostile to the premise is healthy, not a problem.

Show the panel to the user before continuing so they can swap or add a perspective.

### Stage 1: Scan

Each perspective asks 5 questions about the topic with its concern as the priority, then searches for the answers. Ground every claim in a source and cite it. Flag explicitly where sources disagree and where no answer was found.

Run each perspective separately (separate subagents if available, otherwise separate sequential passes). Batching them collapses them toward the same voice.

### Stage 2: Probe

One round of questions gets the obvious. From the Stage 1 findings, identify:

- (a) claims where sources conflicted
- (b) claims asserted with no source
- (c) answers that were suspiciously convenient for the topic's premise

Generate follow-up questions for each and search again. Two rounds is usually the knee of the curve. Run three if the stakes are high.

### Stage 3: Map

Outline before writing. The outline is the deliverable of this stage, not a means to the next one.

Structure the outline by the shape of the actual disagreement, not by perspective. Mark each section **well-sourced**, **thin**, or **contested**. End with a section titled "What no perspective covered." That section is where the value is, so surface it to the user first.

### Stage 4: Synthesize

Write from the outline. Every claim traces to a Stage 1 or Stage 2 source. Where sources conflicted, present the conflict instead of resolving it silently. Where evidence was thin, say so in the text.

### Stage 5: Peer review

Review the draft against the Stage 3 outline. Find:

- claims stated as settled that were contested in the research
- perspectives that were derived but whose findings did not survive into the draft
- anything asserted without a source
- conclusions that would change if the thinnest-sourced claim turned out wrong

Report the findings and revise the draft. If the review finds nothing, treat that as a warning that the panel was captured by the premise, and say so.

## Output

Deliver in this order:

1. The panel (label, core concern, opening question)
2. What no perspective covered
3. The outline with sourcing marks
4. The synthesis, with citations
5. Peer review findings and what changed

For financial, legal, tax, or medical topics, state that the output is input to a professional, not a substitute for one.

## The fallback panel

Derivation costs a round trip. For low-stakes topics where that is not worth it, use this default. The trade: a fixed panel guarantees five angles, derivation finds the right ones.

- **Practitioner**: what actually happens when this meets reality
- **Skeptic**: what has to be true for this to work, and is it
- **Economist**: who pays, who benefits, what is the second-order effect
- **Historian**: what happened last time someone tried this
- **Academic**: what does the evidence base actually say

Use it for low-stakes work. Derive for anything the user will defend.

## Failure modes to check for

- **Personas converge.** If all perspectives sound alike, they were not real perspectives. Return to Stage 0.
- **Retrieval off.** Without sources, the model generates from memory in five voices, which is more convincing and less true than one ungrounded answer.
- **One-pass questioning.** Skipping Stage 2 produces a wide, shallow scan.
- **Perspective theater.** Hostile-sounding personas that all agree with the premise manufacture false confidence.
- **Treating output as final.** The result is a pre-writing aid that needs human editing and judgment.

## References

- `references/worked-examples.md`: derived panels for a strategy document, a financial decision, property research, and a technical architecture. Read when deriving a panel for a similar topic.
- `references/storm-background.md`: what STORM found, its known limits, and links to the original system. Read when the user asks where the method comes from or needs citable sources.
