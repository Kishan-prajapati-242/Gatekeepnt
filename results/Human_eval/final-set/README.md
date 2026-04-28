
# Final Set (Unique 40)
 
40 examples split 8 per annotator, no overlap. Each annotator rated Simplicity, Completeness, and Fluency on their assigned 8 examples across all 3 systems. Accuracy was rated separately by a single domain expert across all 40 examples.
 
## Files
 
- `eval-40.csv` — all 40 examples with S/C/F/Accuracy scores, grouped by annotator
- `calibration_raw.csv` — unblinded version
- `calibration_blind.csv` — blinded version
- `calibration_blind_key.json` — label-to-system mapping
- `exp[1|2|3]_preds.json` — model predictions on final-set examples
## Aggregation
 
Combined scores (anchor + final) are reported in the paper. Anchor examples use per-example means across 5 annotators; final-set examples use the single annotator's rating.
 
