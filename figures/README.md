# Figures

All visualizations used in the paper and exploratory data analysis.

## `paper/`

Figures used in the final report. Files named `table-N` are plots that replace the corresponding tables.

| File | Replaces | Content |
|------|----------|---------|
| `table-4.png` | Table 4 | SARI across datasets with copy-source floors |
| `table-5.png` | Table 5 | BERTScore F1 and Entity F1 across datasets |
| `table-6.png` | Table 6 | Readability delta (FRE) across datasets |
| `human_eval.png` | — | Human evaluation scores (Simplicity, Completeness, Fluency, Accuracy) |
| `human_eval_example_output_length.png` | — | Output length comparison across models on MIMIC-IV |

## `eda/`

Exploratory data analysis plots produced by `data/eda.ipynb`.

| File | Content |
|------|---------|
| `fig_dataset_composition.png` | Training data composition by domain |
| `fig_token_length_dist.png` | Token length distribution across datasets |
| `fig_token_length_by_domain.png` | Token length distribution grouped by domain |
| `fig_src_vs_tgt_wordcount.png` | Source vs target word count |
| `fig_compression_scatter.png` | Compression ratio scatter plot |
| `fig_readability_fre.png` | Flesch Reading Ease distribution |
| `fig_readability_fkg.png` | Flesch-Kincaid grade distribution |
| `fig_readability_bars.png` | Readability comparison bars |
| `fig_sentence_count.png` | Sentence count distribution |
| `fig_avg_word_length.png` | Average word length distribution |
