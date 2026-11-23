# Model Evaluation Results

This directory contains the experimental evaluation results for the medical summarization project.

## Results File

`model_comparison.csv` contains the evaluation metrics for all six models.

## Models Compared

- BART
- BioBART
- DistilBART
- ViT + BART
- BiomedCLIP + BART
- PubMedCLIP + BART

## Metrics

| Metric | Description |
|---|---|
| ROUGE-1 | Unigram overlap |
| ROUGE-2 | Bigram overlap |
| ROUGE-L | Longest common subsequence |
| BLEU | N-gram precision with brevity penalty |
| BERTScore Precision | Semantic precision |
| BERTScore Recall | Semantic recall |
| BERTScore F1 | Combined semantic score |
| METEOR | Lexical similarity with stemming and synonym matching |

## Important

These results represent the currently recorded experimental results.

Before using them in a final research paper, ensure that:

- All models were evaluated on the same test set.
- Evaluation preprocessing was consistent.
- Metric implementations and parameters were consistent.
- The experimental settings are documented.
- Results are reproducible.

The CSV file is provided for transparent comparison and further analysis.