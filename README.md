# Agent Readiness Gate

A Forge app for Jira that evaluates supplied agent-release evidence with deterministic policy checks, explicit human approval, and version-aware history.

This prototype is for evaluation with synthetic fixtures and a disclosed hybrid-synthetic public benchmark. READY means the supplied evidence satisfies the configured policy; it is not a safety guarantee or a Jira workflow restriction. Imported evidence is not independently attested.

[Watch the 2:12 real Jira interaction demo](https://www.youtube.com/watch?v=5ffNGOeyhG0) · [Privacy notice](privacy.md) · [Evaluation terms](terms.md)

The video uses synthetic evidence and synthetic English narration. It shows a continuous cropped excerpt of the working Jira panel, including explicit approval, regression and duplicate-safe remediation. [Codegeist project](https://devpost.com/software/agent-readiness-gate).

## Installation

[Install on your Jira test site](install.md). Independent-site installation and the seeded workflow were verified on 6 November 2026.

The app needs Jira access, Jira write access for explicitly confirmed remediation tasks, and Forge app storage. A site administrator installs it. No external model/API key is required for the core panel. The optional Rovo advisor is read-only and depends on Rovo availability.

## Try the synthetic scenarios

1. Open a synthetic Jira issue, open the app actions menu and select **Agent Readiness Gate**.
2. Select **Load blocked sample**, then **Save evidence**. Version 1.4 is BLOCKED because rollback and approval are missing.
3. Select **Load repaired sample**, then save. Rollback passes; approval is still required.
4. An authorized reviewer checks the explicit approval box and selects **Approve this release**. The exact release becomes READY.
5. Reload to verify persistence. Historical results remain visible.
6. Load and save the regression sample. Version 1.5 becomes BLOCKED and cannot inherit the earlier approval.
7. Preview remediation for a failed control, review the proposed task and explicitly confirm creation. Creating a task does not change readiness.

Reading requires access to the Jira issue; imports require Edit Issues; approval also requires Administer Projects. Remediation requires Create Issues and a supported issue type. An unknown Jira write outcome needs manual reconciliation, not blind retry.

## Executed evidence and permission acceptance

[Watch the 2:10 measured-evaluation and Rovo supplement](https://www.youtube.com/watch?v=DTPsB5Yrirk). Actual Jira/Rovo capture with synthetic English narration; complements the main regression/remediation video.

Two actual GPT-5 mini runs now have [public raw reports](runs/README.md). The [acceptance record](executed-acceptance.md) documents measured JSON import, same-version approval invalidation, a distinct test account and an actual Rovo response, with explicit limitations. Use the [optional runner](executed-evaluation.md) to reproduce the narrow synthetic evaluation.

## Broader frozen benchmark

The [270-case Bitext demonstration](benchmarks/bitext/README.md) measured 92.96% for the baseline and 73.70% for a disclosed intentional regression. Both executions completed without errors. The results and limitations are public; live acceptance of the new authenticated ingestion flow is still pending.

## Prepare your own review

See [how evaluation results map into evidence](evidence-workflow.md), including a complete synthetic JSON example and the current manual-import limitations.

## Contact

Maintainer: Maciej Rubczyński. Support and privacy enquiries: **rubczynski.maciej@gmail.com**. Please do not send credentials or sensitive customer evidence.

These public documents contain no private application source code.
