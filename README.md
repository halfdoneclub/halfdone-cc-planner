# halfdone-cc-planner

A Claude Code skill that turns a rough project idea into a ready-to-use design document — saved directly to `docs/` so your next coding session can start immediately without copy-pasting.

Tell Claude what you want to build. The skill diagnoses complexity (Tier 1 / 2 / 3) and writes the right artifact:

| Tier | Condition | Output file |
|------|-----------|-------------|
| **1 — Simple** | Single feature, no AI judgment needed | `docs/REQUEST.md` — structured Claude Code prompt |
| **2 — Medium** | 2–5 features wired together, no runtime AI | `docs/PRD.md` — full Product Requirements Document |
| **3 — Complex** | Runtime AI judgment or failure recovery required | `docs/AGENT_DESIGN.md` (+ `docs/PRD.md` if external product) |

## Install

```bash
claude plugin install halfdoneclub/halfdone-cc-planner
```

## Usage

Just describe what you want to build — the skill activates automatically.

**Example prompts:**
- "I want a Python script that batch-converts images to WebP"
- "Build me a workout tracker website with monthly stats"
- "Automate email triage and draft replies, send results to Slack every morning"
- "Write a PRD for my SaaS idea", "scaffold a project plan", "make an agent design spec"

The skill asks up to 3 clarifying questions if needed, then writes the artifact to `docs/` and shows you the file path + a 3–5 line summary.

## What gets generated

### Tier 1 → `docs/REQUEST.md`
A single Claude Code request prompt structured as: purpose → input → processing → output → constraints → completion criteria. Paste it into a new Claude Code session to start building immediately.

### Tier 2 → `docs/PRD.md`
A full PRD with: overview · users · features (P0/P1/P2 priority) · technical requirements · out-of-scope · implementation guide.

### Tier 3 → `docs/AGENT_DESIGN.md`
An agent design spec with: task context · workflow steps (AI vs. code roles explicit) · agent structure · implementation spec · implementation guide. Includes failure handling and validation patterns per step.

## Starting your build

After the artifact is saved, open a new Claude Code session and run:

```
# Tier 1
Read docs/REQUEST.md and implement it.

# Tier 2
Read docs/PRD.md and implement. Start with P0 features, confirm each one before moving on.

# Tier 3
Read the design spec in docs/ and implement. Start with workflow step 1, confirm success criteria at each step before moving on.
```

## License

MIT — [한국어 README](README.ko.md)
