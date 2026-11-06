# Live measured regression acceptance

Observed on 6 November 2026 in the development installation, Jira issue ARG-1. Both original reports used the same frozen 270-case protocol described in [the benchmark](README.md). Model executions were not repeated for these UI tests.

| UTC | Observed action | Result |
|---|---|---|
| 15:04:35 | Baseline imported by scoped runner | 251/270 (92.96%); separate approval required |
| 15:04:59 | Authorized human explicitly approves | READY |
| 15:05:19 | Same runner request replayed | Accepted without duplicate history or removing approval |
| 15:11:51 | Regression imported with its own one-report grant | 199/270 (73.70%); BLOCKED; earlier approval cleared |
| 15:16:34 | Consumed grant revoked, then replayed before expiry | HTTP 403; latest 10 visible history action/time entries unchanged |
| 15:18:55 | Rovo explains current assessment and immediate predecessor | Exact scores and counts, READY → BLOCKED, cleared approval, provenance limitation |

Imports used the live Forge endpoint, not manual evidence pasting or direct storage writes. Each grant was explicitly confirmed, limited to one issue and exact evidence bytes, and expired after 15 minutes. The runner could not approve a release. The baseline grant expired and the regression grant was revoked.

The corrected Rovo response on development 2.9.0 identified baseline snapshot `12721e52-d764-451d-acfd-f9099287890b` and regression snapshot `2308fdd8-bc0c-45b4-bc7d-ef6ee8cff9b9`, with exact scores 0.9296296296296296 and 0.737037037037037, sample size 270 each. It described the fixed 85% gate and `CLEARED_BY_IMPORT`, and limited the comparison to the immediate predecessor.

## What provenance establishes

Authenticated-runner verifies only submission of the exact approved evidence bytes by a holder of a reviewer-issued scoped credential. Runner ID is a configured label, not an attested execution environment. Report hash is a supplied reference, not a digital signature. This does not prove test execution, runner code, log availability or metric truth; there is no independent attestation.

Rovo quoted that limitation in the observed response. One correct response does not establish universal model behavior. READY is still a deterministic assessment of supplied evidence, not a safety certification or Jira transition enforcement.

## Remaining acceptance work

The second account's earlier UI restrictions were observed, but direct live backend approval denial and hidden-issue denial remain pending. Concurrency is covered by automated tests, not a live race experiment. Intermittent initial panel loading remains under investigation. A duplicate-form lifecycle defect was reproduced locally and a correction is being validated. No independent participant study was performed.

The existing videos predate this benchmark. A new coherent main video and production update are pending; the public installer must not be assumed to include development 2.9.0.
