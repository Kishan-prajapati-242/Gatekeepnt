# Results
 
Evaluation outputs for all experiments. Each subfolder corresponds to one experimental condition.
 
| Folder | Experiment | Contents |
|--------|-----------|----------|
| `Exp_00/` | Reference quality audit | Copy-source SARI floors, reference entity F1, readability deltas |
| `Exp_01/` | Zero-shot Llama 3.1 8B | Baseline — no fine-tuning |
| `Exp_02/` | SELLS-only QLoRA FT | Single-domain ablation (response-only masking, v2 canonical) |
| `Exp_03/` | Mixed FT (3a at 1024, 3b at 1536) | Main experiment + sequence-length ablation |
| `Exp_04/` | Encoder-decoder baselines | BioBART (4a), FLAN-T5 zero-shot (4c), FLAN-T5 fine-tuned (4d), BioBART fine-tuned (4b) |
| `Human_eval/` | Human evaluation | Annotation scores on 50 MIMIC-IV discharge summaries |
 
## File conventions
 
- `*_results.json` or `*_zero_shot.json` / `*_mixed_*.json` / etc. — aggregate metrics with bootstrap CIs
- `*_per_example.json` — per-example scores for paired statistical comparison across experiments
- `*_preds_[dataset].json` — model predictions on each test set
- `*_train_history.json` — training loss and eval loss logged during fine-tuning
All automatic metrics: SARI, BERTScore F1 (SciBERT), Entity P/R/F1 (scispaCy en_core_sci_lg), FRE/FK deltas. Bootstrap 95% CIs (n=1000, seed=42).
 
