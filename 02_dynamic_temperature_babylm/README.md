# Dynamic Temperature Soft Targets on BabyLM

Soft-target objectives for training small language models on the BabyLM corpus

Instead of assigning all target probability to the observed next token, the soft-target objectives distribute some probability mass over semantically similar tokens. The project examines whether the softness of this distribution should remain fixed or change according to contextual uncertainty.

## Experimental setup

- **Dataset:** BabyLM Strict-Small English corpus
- **Tokenizer:** GPT-2 tokenizer
- **Model:** GPT-2-style causal language model trained from scratch
- **Reference model:** frozen hard cross-entropy baseline
- **Similarity signal:** cosine similarity between token embeddings
- **Uncertainty signal:** predictive entropy from the reference model

## Training conditions

The current experiments include:

- hard cross-entropy
- fixed-temperature soft targets
- mixed hard and soft objectives
- entropy-conditioned sigmoid mapping
- entropy-conditioned piecewise mapping
- shuffled-entropy control


## Code

The main experimental notebook is:

[`babylm_soft_target_training.ipynb`](./babylm_soft_target_training.ipynb)

It contains the data preparation, reference-model training, target construction, and training conditions.

## Status

Work in progress.
