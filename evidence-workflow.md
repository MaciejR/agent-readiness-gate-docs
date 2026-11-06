# From evaluation results to a release review

The intended user is a release owner collecting evaluation, security and rollback evidence for one candidate agent version. The current prototype accepts a manual JSON import. The Forge panel does not call evaluation services or attest results. An optional [local evaluation runner](executed-evaluation.md) executes a scoped synthetic support-triage benchmark against your existing model deployment and exports measured evidence for import.

## Try it without preparing a file

Use **Load blocked sample**, **Load repaired sample** and **Load regression sample** inside the installed panel. These generate synthetic examples with current timestamps. Loading only fills the editor; **Save evidence** persists the input and clears any prior approval.

## Prepare evidence from your own evaluation workflow

Use synthetic or approved non-sensitive data for this prototype. Keep underlying transcripts and customer information out of the JSON.

1. Identify the exact candidate version and responsible owner. Every evidence item's `agentVersion` must match `agent.version`.
2. Export your evaluation summary. Map the evaluation's quality metric to `answerQuality` only if it has the same 0–1 interpretation as your chosen policy. Copy its actual sample count to `sampleSize`, its actual run identifier to `runId`, and the actual observation time to `observedAt`. Do not relabel an old run with today's timestamp.
3. Add the security run's critical finding count and run identifier. Missing security results must remain missing; do not substitute zero.
4. Add the candidate's rollback plan URL. It must not contain credentials. A supplied URL is not proof that a rollback was exercised.
5. Use `source.type: "user-supplied"` for manually supplied real results and a traceable, non-secret `source.reference`. Keep `synthetic` for examples. Neither label provides independent attestation.
6. Paste the combined JSON into **Evidence JSON**, then **Save evidence**. Read every failed control. Repairing evidence does not grant approval.
7. An authorized reviewer checks the sources and explicitly approves the exact release. Any subsequent evidence change clears that approval.

Example mapping for a synthetic evaluation summary:

| Evaluation export | Imported field | Example |
|---|---|---|
| Candidate version | `agent.version` and each `agentVersion` | `1.4` |
| Quality fraction | evaluation `answerQuality` | `0.91` |
| Evaluated cases | evaluation `sampleSize` | `150` |
| Run identifier | evaluation `runId` | `eval-1-4` |
| Run observation time | evaluation `observedAt` | actual UTC timestamp |
| Critical finding count | security `criticalFindings` | `0`, only when reported |
| Rollback reference | rollback `url` | non-secret HTTPS plan URL |

The complete [synthetic JSON example](examples/repaired.json) matches the import shape. Its fixed timestamp will eventually be stale; use the panel's sample loader for a fresh synthetic demonstration. Never refresh timestamps on actual evidence merely to pass a freshness check. There is no approval field in the import: approval is a separate authorized action.

## What this adds to a checklist

The distinguishing behavior is not the green badge. It is binding approval to version + evidence fingerprint + policy, invalidating it when inputs change, and preserving the earlier assessment as history. A team could build similar logic with custom automation; this app packages that review inside the issue. It does not block deployment or Jira transitions.

## Current proof and open questions

The seeded workflow passed on two sites; this does not establish customer demand or time savings. The next user test should measure whether a release owner can prepare and interpret evidence without coaching, and whether the review removes work rather than adding another data-entry step.
