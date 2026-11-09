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

A subsequent direct backend approval attempt from the distinct reviewer account on AGA-5 was denied, despite explicit confirmation and the exact revision/policy hash. All six history IDs/actions/timestamps were unchanged. This used the actual Forge bridge on production 2.1.0, not a mocked request or merely a disabled button. Both identities are controlled by one person. Hidden-issue denial was pending at this checkpoint; the 9 November update below closes it. Concurrency is covered by automated tests, not a live race experiment. Intermittent initial panel loading remains under investigation. A duplicate-form lifecycle defect was reproduced and corrected in development 2.10.0. Two live Reload actions retained one editable runner form; revision-change resets are covered by automated tests. No independent participant study was performed.

Historical checkpoint before publication: the videos then available predated this benchmark. See the publication and production updates below for the current state.


## Published measured demonstration

On 6 November 2026, the [new main video](https://www.youtube.com/watch?v=w7z_YXPiMbc) was published with user approval and public playback verified. The [Devpost project](https://devpost.com/software/agent-readiness-gate) now uses this URL both in the submission field and its public embedded player. The film shows development 2.10.0, not a newly upgraded production installation. It distinguishes live footage, stored evaluation/history review, and recorded acceptance summaries. At publication, hidden-issue testing and the remaining startup matrix were incomplete; see the updates below.


## Production update — 7 November 2026
Production 2.2.0 now includes the evaluated feature set and failed-read UI recovery from development 2.11.0. Deployment and Forge lint succeeded; the existing test-site AGA-5 release and six history entries loaded with the new resource. No release data was changed during this check. This is an existing-installation read smoke test, not a clean installation or production ingestion/Rovo acceptance. Those checks and complete individual hidden-issue history-denial evidence remain pending. The film retains its accurate historical development 2.10.0 label.

## Production acceptance — 9 November 2026

The same original measured reports were imported to synthetic AGA-6 through two explicitly authorized, report-bound runner grants. This was a new transport/UI acceptance test, not another model run.

- Baseline: 251/270, initially BLOCKED until a separate explicit owner approval produced READY snapshot `9b44b551-37a2-4746-b1c2-01962ebb0efe`.
- Replay of the baseline was acknowledged with no additional history entry.
- Regression: 199/270, BLOCKED snapshot `a1f87606-f1d1-4eef-aec5-eae88a8c9b2e`, approval cleared and linked to the prior READY snapshot. Three history entries remained.
- Runner access was revoked. A subsequent exact-report request returned HTTP 403 and history stayed unchanged.
- With AGA-6 temporarily owner-only, the independently authenticated reviewer received separate application denials from both actual `getRelease` and `getHistory` resolvers. They returned no release/history data. Jira also returned 404, but that alone was not treated as proof of resolver authorization.
- On failed Reload, the panel cleared previously displayed release, provenance and history, removed release actions and disabled import controls.
- Original visibility and permission associations were restored; the temporary owner permission was absent. Reviewer reads and the panel recovered, with history unchanged. Both accounts are controlled by one operator.

At this checkpoint, production Rovo comparison, the complete startup matrix and fresh-install UI testing remained open; the follow-up below records their results. These results do not establish independent user research, general security certification or universal loading reliability. The main film remains accurately labelled as historical development 2.10.0 footage.

### Fresh installation, Rovo and entry paths — 9 November follow-up

A new production installation on the first Jira site started empty, alongside the existing development installation. Manual import of the original baseline evidence produced BLOCKED; explicit approval produced READY and survived Reload. Manual regression import produced BLOCKED and cleared approval, with three new history entries. Development history remained separate. This is a manual-evidence acceptance flow; authenticated transport was verified separately on AGA-6 above.

The actual production Rovo response identified current snapshot `48611cab-f380-4fc3-a654-6c14283c7131` at 10:47:15.482 UTC and previous snapshot `19cce101-744f-4842-8cc4-687b5ba4aa8b` at 10:46:37.680 UTC. It reported 92.96% to 73.70%, 270 cases each, changed `answer-quality` and `security-approval` controls, and `CLEARED_BY_IMPORT`. On follow-up it identified both origins as `manual-user-supplied`. The initial question using only ARG-1 failed until the numeric issue ID was supplied; this remains a usability limitation. The response used generic runner-provenance caveats even for manual input, so the actual method was explicitly clarified.

The final native-Chrome entry matrix passed all four observed paths on production AGA-6: owner/direct, owner/board modal, reviewer/direct in a new incognito tab, and reviewer/board modal. The reviewed application fixes address duplicate lifecycle forms and stale display after a failed authorization read. Earlier host-level skeletons/delayed frame loading were observed separately and are not claimed to have a confirmed upstream root cause or a universal fix.

A repeated production Rovo comparison was bracketed by independent application reads. Both snapshot IDs matched the stored pair, and the current snapshot plus complete three-entry history were identical before and after the response. This verifies the observed comparison was read-only; it is not a general guarantee of all future model responses.
