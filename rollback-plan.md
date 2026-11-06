# Support Triage evaluation candidate: rollback plan

Owner: Maciej Rubczyński. Scope: the synthetic support-triage evaluation candidate, not a deployed customer service. Prepared 2026-11-06.

If a candidate produces an unacceptable routing decision or security finding, stop using that candidate for downstream decisions. Preserve its run report and Jira assessment. The classifier proposes decisions only; it has no account, payment or release-write tools.

Select a previously reviewed configuration only if its own evidence and approval remain valid. Otherwise keep the release BLOCKED and require human triage. Do not assume candidate 2.0 is acceptable: its recorded attempts contained vocabulary errors and incomplete executions.

Before resuming, execute the full versioned evaluation against the selected configuration, inspect the raw results, import fresh actual evidence and obtain separate authorized approval. Previous Jira history must remain intact. Any change to model deployment, prompt or evidence requires review.

This is a supplied operational plan for the demonstration. Its presence is not proof of a rollback exercise, production deployment enforcement or a safety guarantee.
