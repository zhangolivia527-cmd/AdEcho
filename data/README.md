# Data: provenance and access

## What was used
The recorded evaluation used 20 real article bodies selected by the student: AD01–AD10 have advertorial reference labels; ED01–ED10 have editorial reference labels. All are from the CNA publisher family. Synthetic smoke-test examples in the notebook are separate and are not included in these 20 results.

source_manifest.json lists article URLs, label bases, collection/review metadata and text hashes. Positive labels rely on publisher disclosure. Editorial labels reflect visible publication context, not proof that no undisclosed commercial relationship exists. The student reviewed extraction and labels with AI assistance before evaluation.

## Preparation
The collector extracts an article body from structured data or supported article containers. It does not use the entire page as fallback. Failed collection requires manual text entry. Standalone disclosure headings and page furniture are excluded; promotional wording within sentences is retained. The same body-only input is used by the keyword baseline and AI, capped at 20,000 characters. ED07 was truncated.

text_sha256 identifies the stored body; reviewed_input_sha256 identifies the reviewed model input. The evaluation protocol also stores each input hash. All 20 uploaded article inputs were checked against the recorded run hashes and matched.

## Actual text snapshot
The exact body snapshot is articles_private.json, downloaded from the student's Colab session and retained separately. It contains source metadata and the reviewed article text. It is excluded from the public repository because it reproduces publisher article bodies. This public manifest is not a substitute for that snapshot.

For the course data hand-in, provide the snapshot through the permitted private assessment channel and identify it in the submission note, subject to applicable course and publisher permissions. This document does not claim that the private hand-in has already occurred. AdEcho_PRIVATE_Checkpoint.json is a separate recovery backup containing article text and results; do not publish it.

## Reproduction
Use notebook Sections 7–8 to collect the linked pages and review their bodies and labels. Alternatively, the student can restore the private checkpoint through Section 7. Compare input hashes with the recorded protocol before claiming exact reproduction. Live webpages can change or become unavailable, so a new fetch may not reproduce the original text. Reproduction calls can also produce different model outputs.

## Sampling limitations
This is a convenience sample, not an independently authored external holdout. ED08 and ED10 cover the same RTS event. Balanced labels do not represent real-world prevalence. Removing explicit disclosures may make sponsorship impossible to establish from body text. The originally proposed larger dataset and colleague holdout were not used in this recorded evaluation.
