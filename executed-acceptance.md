# Executed evaluation and two-account acceptance — 6 November 2026

## Measured model evidence

Two actual Azure GPT-5 mini executions used candidate version 2.1, 100 synthetic exact-match triage cases and 12 model/platform injection probes. Each completed 100/100 quality cases, 11 passing model responses to security probes and one explicit Azure content-filter block. Raw reports, failed earlier attempts, exporter and source fingerprints are [public](https://github.com/MaciejR/agent-readiness-gate-docs/tree/main/runs).

The cases are template-correlated and the classifier proposes decisions without executing external actions. This is not a representative benchmark, security audit, customer study or safety certification. Provider blocks are disclosed separately. The supplied rollback document is a plan, not an exercised rollback. Report hashes support integrity comparison, not independent attestation.

## Actual Jira flow

Production 2.1.0, site agent-readiness-gate-test.atlassian.net, issue AGA-5. Evidence was explicitly pasted and saved through the installed Forge panel; no local mock or direct storage write was used.

| UTC | Action | Observed result |
|---|---|---|
| 12:55:51.117 | Distinct test account imports eval-760e65d073d549a7960ee077d52f4b06 | BLOCKED; all evidence controls pass, security-approval fails |
| 12:58:17.033 | Project-authorized owner explicitly approves | READY |
| 12:58:29.181 | Reload | READY persists |
| 12:58:51.818 | Import eval-15c3b44738c444d88f7222b34fe97328, same candidate version 2.1 | BLOCKED; prior approval invalidated; history retained |
| 13:03:07.978–13:04:01.571 | Repeat first import, explicit approval, second import for recording | Same BLOCKED → READY → BLOCKED sequence |

Original model completion times remain 12:44:32.983Z and 12:48:17.571Z. Scores, run IDs and report digests are visible in Jira. Repeating the demonstration adds historical records; it does not rerun the model or refresh evidence timestamps.

## Two identities, one operator

The user-created test identity has Jira User access, not organization administration. It successfully read AGA-5 and imported the measured evidence. Its approval checkbox and button were disabled with the stated Edit Issues + Administer Projects requirement. The owner account could explicitly approve. Both accounts are controlled by the same person: this is permission acceptance, not independent usability research.

The negative live test covers UI behavior and successful edit access. It is not proof of a direct hostile backend approval invocation. Server-side denial is covered by automated tests; hidden-issue denial, direct live bypass attempts and concurrency remain additional acceptance work.

## Actual Rovo response

On development 2.3.0 at one-atlas-loku.atlassian.net, Release Readiness Advisor retrieved numeric issue 66400 (ARG-1) at 13:01:25.117Z. It returned BLOCKED, agent 1.5, policy 1.0, critical-findings/security-approval and evidence evaluation-1-5/security-1-5/rollback-1-5. It explicitly stated that it cannot approve, override policy, change evidence or create tasks and directed review to the Jira panel.

This Rovo scenario uses the development site's seeded regression; the measured model scenario uses AGA-5 on the second site. No cross-site Rovo read is claimed. Rovo reads the current assessment, not historical report contents.

## Verification boundaries

179 automated tests plus lint, typecheck, build and Forge lint passed for merged PRs 61/62. Development 2.3.0 and production 2.1.0 deployed successfully; installations reported up to date. Full-page Forge loading intermittently stalled; switching the authenticated account and opening AGA-5 from the board restored it. Root cause has not been established.

The Devpost story was saved and read back with these measured results and limitations. The existing public main video remains unchanged until a new concrete file is approved for upload. A clean 2:10 supplemental capture shows Rovo, actual report imports, separate approval and history; earlier obstructed desktop captures are excluded from publication.
