# Experiments

All experiment notebooks. Each is self-contained and runs on Google Colab with an A100 GPU.

| Notebook | Experiment | Training Data | Notes |
|----------|-----------|---------------|-------|
| `exp0_reference_audit.ipynb` | Reference quality audit | — | No model; audits dataset references |
| `exp1_zero_shot.ipynb` | Zero-shot Llama 3.1 8B | None | Primary baseline |
| `exp2_sells_only.ipynb` | SELLS-only QLoRA FT | SELLS | Response-only masking (v2, canonical) |
| `exp3a_mixed_1024.ipynb` | Mixed FT, max_len=1024 | SELLS+MedLane+Cochrane | **Main experiment** |
| `exp3b_mixed_1536.ipynb` | Mixed FT, max_len=1536 | SELLS+MedLane+Cochrane | Ablation |
| `exp4a_biobart_zs.ipynb` | BioBART-v2-large | None | Zero-shot encoder-decoder |
| `exp4b_biobart_ft.ipynb` | BioBART-v2-large | SELLS+MedLane+Cochrane | Full fine-tune, encoder max_len=1024 |
| `exp4c_flant5_zs.ipynb` | FLAN-T5-large | None | Zero-shot encoder-decoder |
| `exp4d_flant5_ft.ipynb` | FLAN-T5-large | SELLS+MedLane+Cochrane | Full fine-tune, encoder max_len=512 |

Shared configuration across all experiments: seed=42, greedy decoding, repetition_penalty=1.1, max_new_tokens=1024, SciBERT for BERTScore, scispaCy en_core_sci_lg for Entity F1.

Note: Exp 4b/4d use full fine-tuning (no LoRA, no quantization) since encoder-decoder models are smaller (~400M params) and fit in memory without quantization. Exp 4b best checkpoint at step 1000 (~0.7 epochs). Exp 4d ran full training (11,223 steps).
