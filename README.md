# AdEcho — PE6201 End-of-Course Project
Author: ZHANG LIWEI

## Recorded results (3 October 2026)
The completed run is `3f2bbc45d57d3110`: 20 articles and 20 saved L2 reviews.

| Metric | Keyword baseline | AI |
|---|---:|---:|
| All-case accuracy / balanced accuracy | 50% | 45% |
| Binary-decision coverage | 100% | 55% |
| Accuracy among binary decisions | 50% | 81.8% (9/11) |
| Abstention rate | 0% | 10% |
| Response error rate | 0% | 35% |
| Mean latency | 0.00218 s | 2.36071 s |

AI L1 valid-response rate: 65%. AI-assisted student L2 pass rate: 40% (8/20).
Reported API cost: US$0.0060108 for the full run, with no missing cost records.
The proposed 88% balanced-accuracy target was not met. All 20 baseline decisions were editorial.
Seven AI responses failed exact-quote validation: six due to case/typographic differences,
one due to an added word. Two accepted AI decisions falsely labelled editorial articles as ads.
Original results are preserved; no post-hoc corrections were counted as successful predictions.

## Inspect without API calls
Read the saved Section 9–10 notebook outputs and JSON evidence in `results/`.
The notebook's live switches are disabled in this public copy. Private widget state was removed.
The saved output records the original run, before those switches were reset.

## Run
Open AdEcho_Final.ipynb in Google Colab. Enable the OPENROUTER_API_KEY secret.
Run all with live API switches disabled; collect and manually review 20 article bodies.
Set RUN_LIVE_EVAL=True in Section 9 to make up to 20 billable calls; rerun Sections 10–12.
Use Section 11 for human L2 review. Never commit API credentials.

## Data and methods
20 user-selected CNA-family article URLs, 10 advertorial and 10 editorial.
Reference labels and article extraction were reviewed by the student with AI assistance before the recorded evaluation.
Editorial labels indicate visible publication context, not proven absence of undisclosed payment.
Body-only first 20,000 characters; identical input for keyword baseline and GPT-4o-mini via OpenRouter.
Threshold 0.70 is a heuristic, not calibrated probability. Errors and abstentions count as not correct
in all-case accuracy and balanced accuracy. Also report coverage and conditional accuracy.
L1 checks output structure and exact evidence quotes. L2 is AI-assisted student review, not independent or blinded evaluation.

## Reproduction and permissions
Article copyright remains with the publisher. Full article bodies are NOT redistributed here.
Fetch original pages or manually supply lawfully accessible body text through the notebook review panel.
Network availability and webpage changes can affect reproduction. Hashes identify the text used.
The article parser does not bypass access controls and never uses the entire webpage as fallback.
The private checkpoint must not be published. Generated results may contain short evidence quotations.

## Limits and responsible use
Small convenience sample from one publisher family; two related RTS news stories are correlated.
Not an independent external holdout, not a representative estimate of real-world accuracy.
Removing disclosures can make sponsorship unknowable from text. Abstention is a meaningful outcome.
Intended for media literacy and human review, not accusations, legal findings or journalist scoring.
Public article text is sent to OpenRouter when live evaluation is enabled; do not enter private drafts.
No numerical evaluation result is claimed before a real run. Teacher-funded credits are not zero economic cost.

## Current human review status
{"run_id": "3f2bbc45d57d3110", "expected_cases": 20, "evaluated_cases": 20, "human_reviewed": 20, "human_passes": 8, "L2_pass_rate_all_20": 0.4, "complete": true}

## AI assistance
An AI assistant helped implement code, inspect source pages and draft documentation.
The student executed the evaluation and saved L2 ratings using AI-suggested verdicts and reasons. The same assistant helped build the system and draft the review, which limits review independence.
Historical notebook demonstrations are explicitly separate from final evaluation.

## Submission
The executed AdEcho_Final.ipynb is included alongside the code, source manifest and evaluation evidence.
Final business/technical analysis (at most 1,200 words) and recorded presentation/demo remain separate deliverables.
