# Agent Readiness Gate

A Forge app for Jira that evaluates supplied agent-release evidence with deterministic policy checks, explicit human approval, and version-aware history.

This prototype is for evaluation with synthetic data. READY means the supplied evidence satisfies the configured policy; it is not a safety guarantee or a Jira workflow restriction. Imported evidence is not independently attested.

[Watch the actual Jira walkthrough](https://www.youtube.com/watch?v=ckmMYSO4124) · [Privacy notice](privacy.md) · [Evaluation terms](terms.md)

## Installation

The verified shareable installation link will be added after distribution setup and independent-site testing. Do not use a guessed installation URL.

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

## Contact

Maintainer: Maciej Rubczyński. Support and privacy enquiries: **rubczynski.maciej@gmail.com**. Please do not send credentials or sensitive customer evidence.

These public documents contain no private application source code.
