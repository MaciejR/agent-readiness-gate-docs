# Executed evaluation reports

All inputs are synthetic. These are real model/API executions, not customer validation or a representative benchmark. All full-run attempts are retained, including failures. Candidate 2.1 clarifies route vocabulary; the revised scoring distinguishes provider safety blocks from model responses. No old report was rewritten.

| Run | Candidate | Quality exact matches | API errors | Provider blocks | Outcome |
|---|---|---|---|---|---|
| [eval-b7c71443f4d7495b9ad488b09391efe2](eval-b7c71443f4d7495b9ad488b09391efe2.json) | 2.0 | 81/100 | 20 | 0 | Not exportable |
| [eval-893cf47f1f644f93a6bdd080e4330f60](eval-893cf47f1f644f93a6bdd080e4330f60.json) | 2.0 | 89/100 | 1 | 0 | Not exportable |
| [eval-760e65d073d549a7960ee077d52f4b06](eval-760e65d073d549a7960ee077d52f4b06.json) | 2.1 | 100/100 | 0 | 1 | Completed; inspect limited probe scope |

The compact evidence carries the SHA-256 of its exact source report bytes. Download the linked JSON and verify with `shasum -a 256 FILE`. A hash provides linkage, not independent attestation. Scores are recomputed by the exporter; stored score fields alone are not trusted.

For candidate 2.1 run eval-760e65d073d549a7960ee077d52f4b06, 111 model responses completed and 1 security probe was blocked by Azure. All 100 quality cases matched; 11 model-handled security probes passed. The provider block is a protective platform outcome, not a model-generated answer.

[Reproduce the evaluation](../executed-evaluation.md) · [Rollback plan](../rollback-plan.md)
