# Human Evaluation
 
Human evaluation of three systems on 50 MIMIC-IV discharge summaries.
 
## Systems evaluated
 
- **A**: SELLS-only fine-tune (Exp 2)
- **B**: Zero-shot Llama 3.1 8B (Exp 1)
- **C**: Mixed fine-tune (Exp 3a)
System identity was blinded and randomized per example during annotation.
 
## Design
 
- **Calibration set** (3 examples): Used for annotator alignment before real annotation. Not scored.
- **Anchor set** (10 examples): All 5 annotators rate all 3 systems. Used for inter-annotator agreement (Krippendorff's alpha).
- **Final set** (40 examples): Split 8 per annotator, no overlap. Each annotator rates Simplicity, Completeness, Fluency. Accuracy rated by a single domain expert across all examples.
Dimensions adapted from PLABA (Attal et al., 2023) and TESLEA (Phatak et al., 2022).
 
## Important
 
**No MIMIC-IV source text is stored here.** All CSVs contain numeric scores and example IDs only. Source text columns have been removed. Access to MIMIC-IV requires PhysioNet credentials.
 
## Subfolders
 
- `calibration-set/` — calibration materials
- `anchor-set/` — 10-example anchor set scores (5 annotators)
- `final-set/` — 40-example unique set scores + aggregate
