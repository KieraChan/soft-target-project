# Soft-target next-token prediction

This repository contains the code for the PLIN0072 project on soft-target next-token prediction.

## Main file

Run the notebook:

- `ST_project_full_wikitext2.py`

The notebook trains and evaluates four settings on WikiText-2:

- hard-target next-token prediction baseline
- label smoothing baseline
- similarity-based soft target with tau = 0.05
- similarity-based soft target with tau = 0.06

## Dataset

The project uses WikiText-2, loaded through the Hugging Face `datasets` library.

## Main experimental settings

- tokenizer: GPT-2 tokenizer
- block size: 128
- batch size: 4
- model: small GPT-2-style decoder-only Transformer
- layers: 4
- attention heads: 4
- embedding size: 256
- seeds: 42, 43, 44
- training budget: one full pass over grouped WikiText-2

## Evaluation

The notebook reports:

- perplexity (PPL)
- expected embedding distance
- accuracy
- top-5 accuracy
- expected calibration error (ECE)
- wall-clock runtime

It also produces the efficiency trade-off plots used in the report.

## Requirements

Install dependencies with:

```bash
pip install -r requirements.txt
```

This code is intended to run in Google Colab or a similar Python environment with GPU support.
