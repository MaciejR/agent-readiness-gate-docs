# Agent Readiness Gate

A Forge app for Jira that evaluates supplied agent-release evidence with deterministic policy checks, explicit human approval, and version-aware history.

This prototype is for evaluation with synthetic fixtures and a disclosed hybrid-synthetic public benchmark. READY means the supplied evidence satisfies the configured policy; it is not a safety guarantee or a Jira workflow restriction. Imported evidence is not independently attested.

[Watch the measured Jira and Rovo demo](https://www.youtube.com/watch?v=UfXcsoULgiA) · [Privacy notice](privacy.md) · [Evaluation terms](terms.md)

The 2:21 video shows actual development 2.10.0 Jira/Rovo footage with edited excerpts and synthetic English narration. It reviews the stored 270-case benchmark results, historical approval invalidation and read-only Rovo comparison. It does not depict a new evaluation during filming. The [earlier core workflow video](https://www.youtube.com/watch?v=5ffNGOeyhG0) covers explicit approval, regression and duplicate-safe remediation on production. [Codegeist project](https://devpost.com/software/agent-readiness-gate).

## Installation

[Install on your Jira test site](install.md). Independent-site installation and the seeded workflow were verified on 6 November 2026.

The app needs Jira access, Jira write access for explicitly confirmed remediation tasks, and Forge app storage. A site administrator installs it. No external model/API key is required for the core panel. The optional Rovo advisor is read-only and depends on Rovo availability.

## Try the synthetic scenarios

1. Create a new synthetic Jira issue in a project where you have Create Issues, Edit Issues and Administer Projects. Note its key (for example, DEMO-1). Open the issue’s app actions menu and select **Agent Readiness Gate**. Use a new issue so sample imports cannot overwrite an existing review.
2. Select **Load blocked sample**, then **Save evidence**. Version 1.4 is BLOCKED because rollback and approval are missing.
3. Select **Load repaired sample**, then save. Rollback passes; approval is still required.
4. An authorized reviewer checks the explicit approval box and selects **Approve this release**. The exact release becomes READY.
5. Reload to verify persistence. Historical results remain visible.
6. Load and save the regression sample. Version 1.5 becomes BLOCKED and cannot inherit the earlier approval.
7. Optional: preview remediation for a failed control. Review the proposed task and explicitly confirm creation only if you want a Jira task. Creating a task does not change readiness.

Reading requires access to the Jira issue; imports require Edit Issues; approval also requires Administer Projects. Remediation requires Create Issues and a supported issue type. An unknown Jira write outcome needs manual reconciliation, not blind retry.

## Ask Rovo for a review brief

Open **Ask Rovo**, choose the installed **Release Readiness Advisor**, and use the key of the issue you just tested. For example: **“Give me a release-review brief for DEMO-1: what changed, why is approval invalid, and what should I review next?”** Replace DEMO-1 with your own key; ARG-1 in our recording is not an issue on your site.

After the regression step, expect BLOCKED, a comparison with the immediately preceding READY assessment, and a fresh-approval requirement. The built-in samples are synthetic; their scores differ from the measured Bitext benchmark below. If Ask Rovo or the agent is unavailable on your site, the core panel and history remain the complete manual review path. Rovo is optional.

Production 2.3.0 returns the immediate-predecessor comparison and a suggested order: repair failed evidence, resolve any requested review, then seek explicit human approval. It distinguishes manual input from authenticated submission. Rovo cannot perform these steps or approve the release.

## Evidence and limits

Actual GPT-5 mini evaluations on a frozen [270-case Bitext benchmark](benchmarks/bitext/README.md) scored 251/270 and 199/270 for a disclosed intentional regression. This is a bounded intent-classification example, not broad agent safety validation. [Original reports and live acceptance](benchmarks/bitext/live-acceptance.md) document imports, approval invalidation, replay, revocation, separate-account denials and production Rovo responses.

The two accounts belong to one operator. There was no independent participant study. Report authentication does not attest execution or metric truth. Earlier owner/reviewer entry checks loaded. A later fresh-issue walkthrough on 9 November encountered a persistent host loading placeholder and remains under investigation; no universal startup reliability is claimed.

The currently published 2:21 film opens with a release-owner scenario and separately summarizes completed production acceptance on 9 November. Screen recordings remain historical development 2.10 footage; the film does not depict the later key-based Rovo update. The [earlier core workflow video](https://www.youtube.com/watch?v=5ffNGOeyhG0) demonstrates explicit approval and remediation; [earlier measured-run evidence](executed-acceptance.md) and the [optional runner](executed-evaluation.md) remain available separately.

## Prepare your own review

See [how evaluation results map into evidence](evidence-workflow.md), including a complete synthetic JSON example and the current manual-import limitations.

## Contact

Maintainer: Maciej Rubczyński. Support and privacy enquiries: **rubczynski.maciej@gmail.com**. Please do not send credentials or sensitive customer evidence.

These public documents contain no private application source code.
