# Exp 2: SELLS-Only Fine-Tune
 
Single-domain ablation. Llama 3.1 8B fine-tuned with QLoRA on SELLS only (168K biomedical sentence pairs). Tests whether multi-domain mixing helps by comparison with Exp 3a.
 
This is v2 (canonical), which uses response-only masking for consistency with Exp 3a/3b.
 
## Files
 
- `exp2v2_sells_only.json` — aggregate metrics with bootstrap CIs
- `exp2v2_per_example.json` — per-example scores
- `exp2v2_preds_[sells|medlane|cochrane|plaba].json` — raw predictions
- `exp2v2_train_history.json` — training and eval loss per step
