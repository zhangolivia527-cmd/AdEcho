# Evaluation evidence and interpretation

## Files
All four JSON files refer to run 3f2bbc45d57d3110 on 3 October 2026.

| File | Contents |
|---|---|
| eval_3f2bbc45d57d3110.json | Frozen protocol, source/input hashes and all 20 baseline/AI responses, including errors, raw model output, usage and timing |
| summary_3f2bbc45d57d3110.json | Computed classification, coverage, abstention, response-validity, latency and cost metrics |
| human_review_3f2bbc45d57d3110.json | 20 student-saved L2 verdicts, reasons and timestamps |
| l2_summary_3f2bbc45d57d3110.json | Completion count and 8/20 L2 passes |

## Protocol and metrics
The keyword baseline and GPT-4o-mini via OpenRouter received identical reviewed article bodies, limited to 20,000 characters. Model temperature was 0, maximum output tokens 500, and the uncalibrated confidence threshold 0.70. The original prompt and configuration are preserved in the run file. No post-hoc corrected predictions replace the recorded outcomes.

All-case accuracy is correct binary predictions divided by 20. Balanced accuracy is the mean recall for the two reference classes. Errors and abstentions are not correct predictions. Because the classes each contain 10 cases, all-case accuracy and balanced accuracy coincide here.

Coverage is accepted binary decisions divided by 20. Conditional accuracy is correct binary decisions divided by accepted binary decisions. Abstention rate counts accepted abstain outputs; error rate counts unusable/null decisions. A response error is distinct from a valid but incorrect classification.

## L1 and L2
L1 checks response structure, allowed labels, finite confidence, evidence quote types/counts, exact quote presence in the input and a nonempty reason. It does not establish semantic correctness. L1 accepted 13/20 outputs, including two abstentions. Seven responses failed exact-quote validation.

L2 assesses whether the response gives a grounded and useful explanation and decision. A justified abstention can pass. The student saved all 20 ratings using AI-suggested verdicts and English reasons; the assistant also helped implement the system. This is AI-assisted student review, not independent, blinded or multi-rater validation. Eight cases passed. AD06 matched its reference label but failed L2 because its explanation did not adequately establish sponsorship. ED02 and ED07 failed for insufficient justification of abstention.

## Recorded results
Baseline: 10/20 correct (50%), 100% coverage; all predictions were editorial.
AI: 9/20 correct (45%), 11/20 binary coverage (55%), 9/11 conditional accuracy (81.8%), two abstentions (10%) and seven errors (35%). The 88% balanced-accuracy target was not met.

AI mean call latency was 2.36071 seconds versus approximately 0.00218 seconds for the local baseline. These measurements include different execution components: the AI measurement includes network/service time. Total recorded API cost was US$0.0060108, or US$0.00030054 per case; no cost record was missing. These are observed run costs, not a current pricing guarantee or total project cost. L2 pass rate was 40% (8/20).

## Failure analysis
- AD01, ED05, ED08 and ED10: a cue changed initial-letter case.
- AD02: cues changed apostrophe typography.
- ED01: a cue changed quotation marks and punctuation.
- AD04: a quoted fragment added HSBC, which was absent from that fragment in the input.
- ED03 and ED06: accepted outputs incorrectly inferred advertising from clinical-trial recruitment or business-profile content.

The first six cases show a fidelity-versus-availability trade-off in exact matching. They were not retroactively counted as successes. The false positives show that promotional appearance does not prove paid sponsorship. Further tuning and evaluation on fresh cases remain future work.

## Inspect or rerun
Read the JSON evidence and saved notebook Sections 9–10 without making API calls. To rerun live evaluation, follow the root README and notebook review steps. Changing prompts, validators or thresholds creates a new method: preserve this original run and label subsequent use of these same cases as development, not unseen testing. API errors remain in the evidence rather than being silently retried away.
