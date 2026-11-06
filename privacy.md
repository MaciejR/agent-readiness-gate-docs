# Privacy notice — Agent Readiness Gate evaluation prototype

Updated: 6 November 2026. Maintainer and contact: Maciej Rubczyński, **rubczynski.maciej@gmail.com**.

## Data handled by the app

The app reads the requesting user's Jira issue access and permissions. It stores submitted release/evidence fields, issue references, deterministic assessments, actor account identifiers, approval identifiers, timestamps, assessment history, and remediation proposal/idempotency records in Atlassian Forge storage. These records support access control, version-specific approval, history, and duplicate prevention.

Use synthetic release evidence only. Do not enter secrets, client records, medical/financial information, or other sensitive personal information. Free-text inputs can contain information supplied by the user; the app does not independently verify it.

## Services and access

The core app uses Atlassian Jira and Forge. No external model service or external analytics service is configured by the core app. Jira tasks are written only after an authorized user explicitly confirms their preview. Optional Rovo actions send assessment metadata, rule explanations and evidence identifiers to Atlassian Rovo; they do not expose a write or approval action.

App data is accessed through server-side Jira permission checks. Administrators and the app maintainer may have platform-level operational access subject to Atlassian's controls. Support emails are handled through the maintainer's email service. Do not include sensitive evidence in a support email.

## Retention and requests

The current prototype has no automatic application-level retention deadline or end-user deletion screen. Normal assessment history is append-only through the app APIs. A remediation proposal expires for use after 15 minutes; this is not a promise that its stored record is deleted at that time.

Forge-hosted data also follows [Atlassian's storage lifecycle](https://developer.atlassian.com/platform/forge/storage-reference/hosted-storage-data-lifecycle/). Uninstalling must not be interpreted as immediate erasure from all platform backups or retention systems.

For questions, access, correction or deletion requests, contact the maintainer above with the site and issue reference, without sending credentials. The maintainer will assess and coordinate the request with the site administrator and applicable Atlassian controls. This notice does not claim a certification or that production customer-data requirements have been validated.

Atlassian services are additionally governed by [Atlassian's privacy policy](https://www.atlassian.com/legal/privacy-policy).
