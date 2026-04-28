
# Exp 4: Encoder-Decoder Baselines
 
Architecture baselines comparing encoder-decoder models against the decoder-only Llama fine-tune.
 
| Exp | Model | Setup |
|-----|-------|-------|
| 4a | BioBART-v2-large | Zero-shot (encoder max_length=1024) |
| 4b | BioBART-v2-large | Fine-tuned on mixed data |
| 4c | FLAN-T5-large | Zero-shot (encoder max_length=512) |
| 4d | FLAN-T5-large | Fine-tuned on mixed data |
 
Note: FLAN-T5 encoder truncates at 512 tokens (T5 trained context length). Cochrane inputs (median ~788 tokens) are substantially truncated for 4c/4d but not for 4a/4b.
 
## Files
 
Each experiment has aggregate results, per-example scores, and predictions per test set. 4b and 4d additionally include training logs.
 
