# agent-stack

The runsagents agent stack: how one human runs a company where agents do the work.  
Every piece assumes production stakes: real money, real state, real consequences.

## The operating loop

```text
territory (agent-fleet-control) → build → attack (rival-review, measured by rival-review-bench)
→ verify state (airlocks, settlement-proof) → receipts (handoff-receipts)
→ ranked unknowns (loss-weighted-unknowns) → the human decides (quiz-me keeps the human able to)
→ memory with provenance (memory-ledger) → unattended sweeps file-don't-fix (night-watch)
→ economics (route-ledger) → back to territory

permission-surface guards what enters the stack
voice-calibration governs the human's outbound words
```

This is a control loop, not a toolbox shelf. Give every writer territory before it builds. Make a different model attack consequential work, then measure whether that rivalry adds recall. Believe system state over success-shaped language, carry evidence across every handoff, and put the costliest unknowns in front of the human while the human can still explain the system. Preserve memory only with provenance and expiry. Let unattended agents observe, file, and stop. Price routes from outcomes, not model folklore. Inspect every new artifact before it joins the loop, and calibrate the words that leave it in the human's name.

## Catalog

| Artifact | What it does | Install |
| --- | --- | --- |
| [agent-fleet-control](https://github.com/runsagents/agent-fleet-control) | Creates separate worktrees, explicit path territory, task contracts, verification evidence, and receipts; it never commits, pushes, or merges. | `git clone https://github.com/runsagents/agent-fleet-control.git /tmp/agent-fleet-control && install -m 0755 /tmp/agent-fleet-control/bin/agent-fleet "$HOME/.local/bin/agent-fleet"` |
| [rival-review](https://github.com/runsagents/rival-review) | Sends meaningful diffs to a different model to prove them wrong; unresolved disagreement goes to the human. | `npx skills add runsagents/rival-review` |
| [rival-review-bench](https://github.com/runsagents/rival-review-bench) | Grades local reviewer verdicts on 12 synthetic planted defects and reports recall, false positives, coverage, and pair uplift; it makes no model calls. | `git clone https://github.com/runsagents/rival-review-bench.git` |
| [airlocks](https://github.com/runsagents/airlocks) | Checks done claims against the system of record from a context that did not do the work, with evidence quoted in the report. | `npx skills add runsagents/airlocks` |
| [settlement-proof](https://github.com/runsagents/settlement-proof) | Builds a read-only payment evidence packet across processor, ledger, idempotency, and reconciliation state, blocking done when they disagree. | `npx skills add runsagents/settlement-proof` |
| [handoff-receipts](https://github.com/runsagents/handoff-receipts) | Validates structured handoff receipts for scope, territory, decisions, unresolved risks, verification, artifacts, and acceptance; validation is not proof. | `git clone https://github.com/runsagents/handoff-receipts.git` |
| [loss-weighted-unknowns](https://github.com/runsagents/loss-weighted-unknowns) | Ranks stated unknowns by severity × likelihood × irreversibility × blast radius × compliance exposure; it does not discover every unknown or approve a release. | `git clone https://github.com/runsagents/loss-weighted-unknowns.git` |
| [quiz-me](https://github.com/runsagents/quiz-me) | Examines the human on recent repo changes with eight questions, honest grading, and explanations for what they missed. | `npx skills add runsagents/quiz-me` |
| [memory-ledger](https://github.com/runsagents/memory-ledger) | Provides a format and audit tool for memory with source, scope, confidence, expiry, supersession, and explicit action-authorization eligibility. | `git clone https://github.com/runsagents/memory-ledger.git` |
| [night-watch](https://github.com/runsagents/night-watch) | Runs read-only unattended repository sweeps that write validated evidence packets under `findings/` and never fix what they find. | `mkdir -p .agents/skills/night-watch && cp -R /path/to/night-watch/{SKILL.md,checks,templates,schemas,scripts} .agents/skills/night-watch/` |
| [route-ledger](https://github.com/runsagents/route-ledger) | Groups observed runs by task and model, prices full operating cost plus an expected-loss proxy, and recommends only qualified routes with enough evidence. | `git clone https://github.com/runsagents/route-ledger.git` |
| [permission-surface](https://github.com/runsagents/permission-surface) | Statically surfaces executable, install-hook, network, shell, outside-write, secret, mutable-ref, and capability signals before install; it never executes the artifact or certifies it safe. | `git clone https://github.com/runsagents/permission-surface.git` |
| [voice-calibration](https://github.com/runsagents/voice-calibration) | Turns patterns in a private message corpus into a corrected style guide and template, refined through blind tests. | `git clone https://github.com/runsagents/voice-calibration.git` then copy `TEMPLATE_SKILL.md` into your skills as `write-as-<name>` |

Install lines follow each source README's documented mode. A clone is a checkout, not a claim that the repository has an installer; read that artifact's requirements before running it.

## Start here

Start with three controls that cover human comprehension, independent state verification, and adversarial review:

1. Install [quiz-me](https://github.com/runsagents/quiz-me) and prove that you can still answer for what the agents shipped.
2. Put [airlocks](https://github.com/runsagents/airlocks) in front of consequential claims such as merged, deployed, passing, published, or fixed.
3. Use [rival-review](https://github.com/runsagents/rival-review) before merging production-stakes changes, while keeping tests and ordinary gates in place.

## Sources of truth

The separate artifact repositories are the sources of truth for behavior, installation, compatibility, limitations, and releases. This repository is the map: it explains how the pieces compose, but does not replace their documentation.
