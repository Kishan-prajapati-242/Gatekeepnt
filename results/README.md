# Results

Evaluation outputs for all experiments.

## Automatic evaluation

Each JSON contains per-dataset SARI, BERTScore F1, Entity P/R/F1, readability deltas, and 95% bootstrap CIs.

## Human evaluation

`human_eval/` contains annotation scores from 50 MIMIC-IV discharge summaries. Source text is **not included** (credentialed data). Files contain numeric scores and example IDs only.

- `rubric.pdf` — Full annotation protocol
- `anchor_scores/` — 10-example anchor set, all 5 annotators (used for IAA)
- `unique_scores/` — 40 examples, 8 per annotator
- `iaa.json` — Krippendorff's alpha per dimension
