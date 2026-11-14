# STORM background

The Perspective Protocol adapts STORM (Synthesis of Topic Outlines through Retrieval and Multi-perspective Question Asking) from Stanford's OVAL Lab. Paper: Shao et al., NAACL 2024.

## What STORM found

Articles were judged better organized by a 25-point margin and broader in coverage by 10 points versus an outline-driven retrieval baseline. It got there by discovering perspectives from the topic, asking questions iteratively against retrieved sources, stabilizing an outline, and only then writing.

STORM's second hypothesis is that in-depth questions require iterative research. That is the basis for Stage 2 (Probe).

## What it does not do

This is not a debias tool. STORM's own authors flagged source bias transfer and over-association of unrelated facts as unsolved problems in the system. What the method buys is coverage.

STORM's own repository says it cannot produce publication-ready articles and usually needs significant editing. Experienced Wikipedia editors found it useful at the pre-writing stage. That is the honest claim, and it applies to this protocol too.

## What this adaptation changes

- Portable: runs as a sequence of stages in any agent with search, no dedicated pipeline
- Adds Stage 5 (peer review), which is not in the original paper, to catch blind spots the perspectives shared
- Adds a fallback panel for low-stakes topics

## The real tool

For anything needing citable sources, use the original system:

- Live demo: storm.genie.stanford.edu
- Code: github.com/stanford-oval/storm
- Co-STORM adds human-in-the-loop collaboration

Use the real system when you need the citations. Use this protocol when you are thinking and will supply or verify the facts.
