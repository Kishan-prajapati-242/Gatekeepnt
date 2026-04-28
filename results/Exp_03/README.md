 
# Exp 3: Mixed Fine-Tune (Main Experiment)
 
Llama 3.1 8B fine-tuned with QLoRA on SELLS + MedLane + Cochrane with T=2 temperature mixing and domain-prefix conditioning.
 
- **Exp 3a** (max_length=1024) — main experiment, reported in paper
- **Exp 3b** (max_length=1536) — sequence-length ablation
All deltas between 3a and 3b are within CI overlap, justifying max_length=1024.
 
## Files
 
### Exp 3a (main)
- `exp3a_mixed_1024.json` — aggregate metrics
- `exp3a_per_example.json` — per-example scores
- `exp3a_preds_[sells|medlane|cochrane|plaba].json` — raw predictions
- `exp3a_train_history.json` — training log
### Exp 3b (ablation)
- `exp3b_mixed_1536.json` — aggregate metrics
- `exp3b_per_example.json` — per-example scores
- `exp3b_preds_[sells|medlane|cochrane|plaba].json` — raw predictions
- `exp3b_train_history.json` — training log
