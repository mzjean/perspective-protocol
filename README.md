# The Perspective Protocol
 
An agent skill for stress-testing decisions and drafts from multiple perspectives. Works with any agent that supports the open Agent Skills format. A portable adaptation of Stanford's [STORM](https://github.com/stanford-oval/storm) method.
 
Most "ask five experts" prompts produce roleplay with headings. This one works because of three things:
 
1. **Perspectives derived from the topic**, not from a stock list
2. **Retrieval** grounding claims in real sources
3. **Iteration** in the questioning, not one pass
What you get is coverage. The protocol widens the question surface before you commit to an answer, so you find out what you missed while it is still cheap to fix.
 
## How it runs
 
| Stage | What happens |
|---|---|
| 0. Derive | Find the 4 to 6 perspectives that ask non-overlapping questions |
| 1. Scan | Each perspective asks sourced questions, run separately |
| 2. Probe | Go again on conflicted, unsourced, or too-convenient answers |
| 3. Map | Outline by the shape of the disagreement, mark thin and contested areas |
| 4. Synthesize | Write from the outline, conflicts shown, not smoothed over |
| 5. Peer review | Check the draft against the outline for lost findings and false certainty |
 
## When to use it
 
Good for strategy documents, positioning decisions, financial or legal choices with irreversible consequences, and anything you will defend to someone who knows more than you.
 
Not worth it for factual lookups, single-right-answer tasks, or short outputs.
 
## Install
 
This skill follows the open [Agent Skills](https://agentskills.io) format, so it works in any agent that supports `SKILL.md` skills, including Claude Code, GitHub Copilot, Codex, Cursor, and OpenCode.
 
**Any agent, with the skills CLI**
 
```
npx skills add mzjean/perspective-protocol
```
 
The CLI detects which agents you have installed and puts the skill in the right place.
 
**Manual install**
 
Clone the repo and copy the skill folder into your agent's skills directory:
 
```
git clone https://github.com/mzjean/perspective-protocol
cp -r perspective-protocol/skills/perspective-protocol <your-agent-skills-directory>/
```
 
| Agent | Personal skills directory |
|---|---|
| Claude Code | `~/.claude/skills/` |
| GitHub Copilot | `~/.github/skills/` |
| OpenCode | `~/.config/opencode/skills/` |
| Others | See your agent's docs for its skills path |
 
To share it with a team instead, copy the folder into the project repo (for example `.claude/skills/` or `.github/skills/`).
 
**Chat apps**
 
For apps that take skill uploads, such as the Claude app, zip the `skills/perspective-protocol` folder and upload it in settings.
 
**No skill support?**
 
The protocol is plain markdown. Paste the contents of [`SKILL.md`](skills/perspective-protocol/SKILL.md) into any capable model with search turned on and it will run.
 
## Use
 
Ask for it by name or describe the job:
 
> Run the Perspective Protocol on this positioning doc. I'm presenting it to the exec team next week.
 
> Stress-test my plan to move our billing system to usage-based pricing.
 
The skill needs a search or retrieval tool to do its job. Without one it will tell you so and label findings as unsourced.
 
## Example panel
 
For a technical architecture review of an agent system:
 
- **The operator at 3am**: what breaks, and can I see why?
- **The cost model**: what does this run at scale?
- **The next maintainer**: can anyone but the author understand this?
- **The adversary**: what is the attack surface?
More in [`worked-examples.md`](skills/perspective-protocol/references/worked-examples.md).
 
## Limits
 
This is not a debiasing tool, and the output is a pre-writing aid, not a finished verdict. For financial, legal, or tax topics, treat the result as input to a professional.
 
## Credit
 
Adapted from STORM (Synthesis of Topic Outlines through Retrieval and Multi-perspective Question Asking) by Stanford's OVAL Lab. Shao et al., NAACL 2024. For work that needs citable sources, use the original at [storm.genie.stanford.edu](https://storm.genie.stanford.edu). This project is independent and not affiliated with Stanford.
 
## License
 
MIT. See [LICENSE](LICENSE).
 
