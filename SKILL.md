---
name: agent-stack
description: Route a production-stakes agent situation to the smallest fitting runsagents artifact or composition of artifacts.
---

# Agent stack router

Use this skill to choose controls, not to claim that a control has run. Select the smallest artifact set that addresses the current failure mode. Read the selected artifact's own repository before installing or applying it; those repositories are authoritative.

## Route the situation

| Current situation | Route to | Why this fits | Boundary to preserve |
| --- | --- | --- | --- |
| Multiple writing agents need to work concurrently | `agent-fleet-control` | Creates separate worktrees, explicit path territory, task contracts, verification evidence, and local receipts. | It does not enforce paths at the OS level and never commits, pushes, or merges. |
| A meaningful diff needs an independent attack | `rival-review` | Gives the diff to a different model and preserves standing disagreement for the human. | Agreement is evidence, not proof; keep tests and gates. |
| You need to test whether a second reviewer adds recall | `rival-review-bench` | Measures local verdicts against 12 synthetic planted defects, including pair uplift. | It makes no model calls and does not estimate production defect rates. |
| An agent says work is merged, deployed, passing, published, or fixed | `airlocks` | Verifies the claim against the system of record from an independent context. | It checks state claims, not design quality. |
| A payment outcome needs cross-system evidence | `settlement-proof` | Compares processor, ledger, idempotency, and reconciliation state in a read-only packet. | It does not repair, retry, reverse, refund, or post. |
| Work is moving between agents or to a human | `handoff-receipts` | Requires a validated record of scope, decisions, risks, verification, artifacts, and acceptance checks. | Structural validity does not prove the claims are true. |
| Open questions need a risk-first order | `loss-weighted-unknowns` | Ranks stated unknowns by the loss shape of a bad outcome. | Scores are judgments; ranking neither discovers everything nor approves release. |
| The human needs to remain able to answer for shipped code | `quiz-me` | Examines the human on recent changes, grades eight answers, and reteaches misses. | It is an exam, not a code review. |
| Agent memory may outlive its source or scope | `memory-ledger` | Records and audits provenance, scope, confidence, expiry, supersession, and action eligibility. | Memory never expands current permission or replaces fresh approval. |
| A scheduled or unattended agent should inspect a repo | `night-watch` | Performs read-only checks, files validated findings, and stops. | File, don't fix; human triage remains required. |
| Model routing needs economic evidence | `route-ledger` | Prices observed inference, review, correction, rerun, and loss-proxy costs by task and model. | Require enough local evidence and a quality floor; synthetic demos make no benchmark claim. |
| An agent artifact is being considered for installation | `permission-surface` | Statically surfaces capability and risk signals without executing scanned content. | A quiet scan is not a safety certificate; inspect provenance and source. |
| Outbound writing should sound like the human | `voice-calibration` | Derives a corrected style guide and exemplars from corpus patterns, then blind-tests drafts. | Keep the corpus local where possible and treat the guide as personal data. |

## Compose when the stakes cross boundaries

- Before parallel work: `permission-surface` for incoming artifacts, then `agent-fleet-control` for writers and territory.
- Before merge: `rival-review`; use `rival-review-bench` separately to validate the reviewer pairing.
- Before accepting done: `airlocks`, plus `settlement-proof` when the claim is a payment outcome.
- Before transfer: `handoff-receipts`, carrying the exact verification evidence and unresolved risks.
- Before a consequential human decision: `loss-weighted-unknowns`, then `quiz-me` if the decision depends on understanding agent-written code.
- After the decision: `memory-ledger` for durable context, `night-watch` for read-only unattended sweeps, and `route-ledger` for routing economics.
- For words sent in the human's name: `voice-calibration` after the substantive decision, never as a substitute for it.

## Routing rules

1. Name the failure mode and the system of record before choosing an artifact.
2. Do not infer authorization from any artifact, receipt, memory entry, or prior approval.
3. Keep doer, adversarial reviewer, and state verifier independent when the stakes justify the cost.
4. Preserve uncertainty and disagreement verbatim for the human instead of letting agents negotiate it away.
5. If no row fits, say so. Do not stretch an artifact beyond the limitations in its source repository.
