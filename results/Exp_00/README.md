
# Exp 0: Reference Quality Audit
 
Evaluates the quality of human-written reference simplifications before any model is trained. No model is involved.
 
## What this computes
 
- **Entity P/R/F1** between source and reference (do references preserve medical terms?)
- **Readability delta** FRE and FK from source to reference (do references actually simplify?)
- **Copy-source SARI** (what score does "change nothing" get? — the floor every model must beat)
- **Source-reference BERTScore** (how semantically close are source and reference?)
## Files
 
- `exp0_baselines.json` — all metrics for SELLS, MedLane, Cochrane, PLABA test sets
