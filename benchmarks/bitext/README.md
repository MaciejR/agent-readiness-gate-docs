# Frozen Bitext held-out demonstration

Actual GPT-5 mini executions on 6 November 2026, using the same frozen 270 intent-classification cases and 12 separate bounded security probes.

| Candidate | Correct | Accuracy | Macro F1 | Execution errors |
|---|---:|---:|---:|---:|
| Baseline | 251/270 | 92.96% | 0.9253 | 0 |
| Disclosed intentional regression | 199/270 | 73.70% | 0.7163 | 0 |

The fixed quality threshold is 85%. The regression deliberately maps six intents to complaint; this demonstrates detection of a controlled defect, not discovery of a production incident. Both runs had 10 model probe passes, zero model probe failures and 2 provider blocks. Provider blocks are not model successes.

[Baseline summary](bitext-heldout-baseline.public.json) and [regression summary](bitext-heldout-regression.public.json) preserve all case labels, including errors, configuration fingerprints and original times. Original provider bodies were retained privately and revalidated before export. These summaries contain no ticket text, raw model responses or credentials. Hashes link retained reports; they do not independently attest execution.

## Dataset and limitations

Source: [Bitext customer-support dataset, pinned revision](https://huggingface.co/datasets/bitext/Bitext-customer-support-llm-chatbot-training-dataset/tree/430d1a89bd93bd1fa23c16f29dd53e73f0087443), by Bitext. Hybrid-synthetic data seeded from natural text, not wholly synthetic. Source license: [CDLA-Sharing-1.0](https://cdla.dev/sharing-1-0/). Derived selections/results retain this attribution and data license; this is not an official Bitext split.

The source contains 26,872 rows and 27 intents. The project froze 54 development examples (2 per intent) and 270 held-out examples (10 per intent), removing normalized duplicates and limiting selected-pair token Jaccard similarity to 0.65. No prompt, case selection or threshold was tuned after the pilot or held-out execution. Only the instruction was used as per-case model input; expected intent and source response were excluded.

Lexical separation does not establish semantic-family independence. Public data may have occurred in model training. The 12 probes are a small separate project fixture, not a security certification. There was no independent user study.

## Product acceptance status

These are executed evaluation results. Development 2.5.0 adds authenticated runner ingestion, but live ingestion, replay/revocation and same-issue Rovo acceptance remain pending. Existing published videos show the earlier scenarios and do not demonstrate these 270-case results. The public production installation is not claimed to include the new development feature yet.
