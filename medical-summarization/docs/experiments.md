# Experimental Setup

## Research Objective

The objective of this research is to investigate medical query summarization using different NLP and multimodal architectures.

We compare text-based summarization models with vision-language approaches to investigate whether incorporating medical images improves summarization performance.

## Models Evaluated

### Text-based Models

- BART
- BioBART
- DistilBART

### Multimodal Models

- ViT + BART
- BiomedCLIP + BART
- PubMedCLIP + BART

## Experimental Comparison

The models are evaluated using the same summarization task:

**Input:** Medical query, with image information where applicable.

**Output:** Generated medical summary.

The goal is to compare generated summaries against reference summaries.

## Evaluation Metrics

### ROUGE

Measures overlap between generated summaries and reference summaries.

- ROUGE-1: Unigram overlap
- ROUGE-2: Bigram overlap
- ROUGE-L: Longest common subsequence

### BLEU

Measures n-gram precision with a brevity penalty.

### BERTScore

Uses contextual embeddings to assess semantic similarity between generated and reference summaries.

Metrics reported:

- Precision
- Recall
- F1

### METEOR

Evaluates similarity using unigram matching, including stemming and synonym matching.

## Research Questions

1. How do traditional text summarization models perform on medical query summarization?
2. Do biomedical pretrained models provide an advantage over general pretrained models?
3. Does incorporating medical image information improve summarization performance?
4. How do different multimodal architectures compare with text-only models?
5. Which model provides the best balance between lexical overlap and semantic similarity?

## Reproducibility

All experiments should use documented configurations, dataset splits, model parameters, and evaluation procedures.

Dataset files and model weights are not committed to this repository.
