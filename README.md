# Fine-tuning GIT Model: Normal vs. LoRa

This project demonstrates fine-tuning a **Generative Image-to-text Transformer (GIT)** model for vision and language tasks using the **Flickr 8k dataset**. It explores two fine-tuning methods:

- **Normal Fine-tuning**
- **LoRa (Low-Rank Adaptation)** 

## Model Overview

The GIT model is designed to generate captions for images, trained on various datasets. This experiment focuses on **fine-tuning** the GIT model on a small subset of 300 samples from the Flickr 8k dataset to compare performance between traditional fine-tuning and **LoRa**-based fine-tuning.

### Reference Paper:
- **[GIT: A Generative Image-to-text Transformer for Vision and Language](https://arxiv.org/abs/2205.14100)**

### Dataset:
- **Flickr 8k Dataset**: Available on [Kaggle](https://www.kaggle.com/datasets/adityajn105/flickr8k)

## Fine-tuning Methods

1. **Normal Fine-tuning**: The entire model is trained on the dataset.
2. **LoRa Fine-tuning**: Only selected parts of the model are adapted with **low-rank updates** for efficient fine-tuning.

## Evaluation Metrics

- **CIDEr**: Consensus-based Image Description Evaluation.
- **SPICE**: Semantic Propositional Image Caption Evaluation.
- **METEOR**: Metric for Evaluation of Translation with Explicit ORdering.

## Results

Below are the evaluation results for both fine-tuning methods:

| Fine-tuning Method     | CIDEr Score | SPICE Score | METEOR Score |
|------------------------|-------------|-------------|--------------|
| Normal Fine-tuning      | 0.5284      | 0.4143      | 0.5458       |
| LoRa (r=256, α=512)     | 0.1413      | 0.0348      | 0.1720       |

## Requirements

```bash
pip install torch transformers peft
