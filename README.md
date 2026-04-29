# Gatekeepn't

**Multi-Domain Medical Text Simplification via Domain-Conditioned Fine-Tuning**

We fine-tune Llama 3.1 8B Instruct with QLoRA across three medical sublanguages (biomedical literature, clinical notes, systematic reviews) using domain-prefix conditioning. A single model simplifies across domains without catastrophic cross-domain degradation.

Northeastern University · CS 6120 Natural Language Processing · Spring 2026

## Key Results

| Dataset | Zero-Shot SARI | SELLS-only FT | Mixed FT |
|---------|:-:|:-:|:-:|
| SELLS | 36.50 | 37.72 | **37.73** |
| MedLane | 16.60 ✗ | 14.64 ✗ | **55.53** |
| Cochrane | 40.12 | 34.16 | **42.31** |
| PLABA (OOD) | **32.25** | 30.17 | 30.25 |

✗ = below copy-source floor (model edits make text worse than returning source unchanged)

## Findings

1. **Single-domain fine-tuning backfires.** SELLS-only training drops MedLane SARI below the do-nothing floor and collapses Cochrane Entity F1 to 0.105.
2. **Multi-domain mixing recovers cross-domain performance** without degrading the dominant domain (SELLS SARI identical at 37.7).
3. **Reference quality varies dramatically.** MedLane references increase surface reading complexity (FK +2.2). We introduce a reference-quality audit (Exp 0) as a pre-evaluation step.
4. **OOD generalization is limited.** Mixed FT does not outperform zero-shot on PLABA. The model learns trained simplification styles, not a general ability.

## Repository Structure## Experiments

| Exp | Configuration | Purpose |
|-----|--------------|---------|
| 0 | Reference quality audit | Are the references good simplifications? |
| 1 | Zero-shot Llama 3.1 8B | Does fine-tuning help? |
| 2 | SELLS-only QLoRA FT | Does multi-domain mixing help? |
| 3a | Mixed FT, max_len=1024 | **Main experiment** |
| 3b | Mixed FT, max_len=1536 | Is 1024 sufficient? |
| 4a | BioBART-v2-large zero-shot | Encoder-decoder baseline (zero-shot) |
| 4b | BioBART-v2-large fine-tuned | Encoder-decoder baseline (fine-tuned) |
| 4c | FLAN-T5-large zero-shot | Instruction-tuned enc-dec baseline (zero-shot) |
| 4d | FLAN-T5-large fine-tuned | Instruction-tuned enc-dec baseline (fine-tuned) |

## Data Access

| Dataset | Access | Link |
|---------|--------|------|
| SELLS | Public | [GitHub](https://github.com/LinguisticAnomalies/pls_retrieval) |
| MedLane | Author request | [GitHub](https://github.com/machinelearning4health/MedLane) |
| Cochrane | Public | [HuggingFace](https://huggingface.co/datasets/GEM/cochrane-simplification) |
| PLABA | Public | [OSF](https://osf.io/rnpmf/) |
| MIMIC-IV | Credentialed | [PhysioNet](https://physionet.org/content/mimiciv/2.2/) |

MIMIC-IV requires CITI training and a signed data use agreement. No patient text is stored in this repository.

## Setup

```bash
git clone https://github.com/Kishan-prajapati-242/gatekeepnt.git
cd gatekeepnt
pip install -r requirements.txt
```

Experiments were run on Google Colab with NVIDIA A100 GPUs.

## Team

Ning-Hsuan Tseng · Kishan Prajapati · Theresa Coleman · Shashank Kadiyala · Siddarth Chalasani

## License

MIT
