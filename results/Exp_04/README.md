# Exp 4: Encoder-Decoder Baselines

Architecture baselines comparing encoder-decoder models against the decoder-only Llama fine-tune.

| Exp | Model | Setup | Training | Best Step |
|-----|-------|-------|----------|-----------|
| 4a | BioBART-v2-large | Zero-shot | — | — |
| 4b | BioBART-v2-large | Full fine-tune | Mixed, lr=3e-5, eff_batch=64 | 1000 (early stop) |
| 4c | FLAN-T5-large | Zero-shot | — | — |
| 4d | FLAN-T5-large | Full fine-tune | Mixed, lr=3e-5, eff_batch=64 | 11000 |

Note: FLAN-T5 encoder truncates at 512 tokens (T5 trained context length). BioBART uses encoder max_length=1024. Both fine-tuned models use full parameter updates (no LoRA) since encoder-decoder models at ~400M params fit in A100 memory without quantization.

## Files

Each experiment has aggregate results, per-example scores, and predictions per test set. 4b and 4d additionally include training logs.
