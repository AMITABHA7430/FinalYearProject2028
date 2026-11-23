# Multimodal Medical Query Summarization

A research project exploring multimodal summarization of code-mixed Hindi-English medical queries using text and medical images.

## Dataset

**MMCQSD:** [Hugging Face Dataset](https://huggingface.co/datasets/ArkaAcharya/MMCQSD)

Dataset fields:
- `Codemixed_Question` – Medical query in code-mixed Hindi-English.
- `summary` – English reference summary.
- `Image_path` – Corresponding medical image path.

## Tech Stack

- Python
- Pandas
- PyArrow
- Hugging Face
- Pillow
- Matplotlib
- Seaborn
- Jupyter Notebook
- VS Code

## Project Structure

```text
Medical-Summarization-Research/
│
├── data/
│   ├── raw/
│   │   ├── train.parquet
│   │   └── Multimodal_images.zip
│   ├── processed/
│   └── splits/
│
├── notebooks/
├── experiments/
├── reports/
├── src/
├── configs/
└── README.md
```

## Dataset Setup

1. Created the project directory and folder structure.
2. Created and activated a Python virtual environment.
3. Installed the required Python dependencies.
4. Downloaded the MMCQSD Parquet dataset.
5. Downloaded the medical image ZIP archive.
6. Inspected the image archive contents.

## Dataset Analysis

**Dataset:** [MMCQSD – Multimodal Code-Mixed Question Summarization](https://huggingface.co/datasets/ArkaAcharya/MMCQSD)

### Dataset Overview

| Property | Value |
|---|---:|
| Total records | 3,015 |
| Total columns | 3 |
| Unique image paths | 372 |
| Missing values | 0 |
| Empty values | 0 |
| Duplicate rows | 0 |
| Missing image references | 0 |

### Image Reuse Analysis

- 372 unique image paths are referenced by 3,015 records.
- 131 images have multiple extracted image descriptions.
- 241 images have only one extracted description.
- The most reused image appears in 673 records.
- Another image appears in 124 records with 37 different descriptions.

### Observation

The dataset has complete structural records and valid image references. However, repeated image usage and variations in image descriptions indicate a potential image–text alignment limitation that requires further investigation.

Original dataset files are preserved without modification.


## 🔒 Data Leakage Prevention via SHA-256 Hashing

To prevent **data leakage** and ensure realistic model evaluation, we group our data split using exact file contents rather than filenames or metadata.

### The Problem: Naive Splitting
If identical image files exist under different names (e.g., `Image_3.jpg` and `Image_70.jpg`), a standard random split might place one in the training set and its twin in the test set. The model would "cheat" by memorizing pixels, leading to artificially high test accuracy.

### The Solution: Hash Grouping
We use **SHA-256 hashing** to map file contents to a unique identifier:
* **Same SHA-256 Hash** = 100% identical file contents (even if filenames differ).
* **Different SHA-256 Hash** = Different file contents (though they may still look visually similar).


cat >> README.md << 'EOF'

---

# Medical Multimodal Query Summarization Using Vision-Language Models

## Overview

This research project investigates medical query summarization using both text-based and multimodal deep learning architectures. The objective is to compare conventional summarization models with vision-language approaches and evaluate whether incorporating medical images can improve the quality of generated summaries.

The project uses the MMCQSD dataset containing code-mixed medical queries, reference summaries, and associated images.

## Research Objectives

- Evaluate text-based summarization models on medical queries.
- Compare general-purpose pretrained models with biomedical pretrained models.
- Investigate multimodal summarization approaches combining textual and visual information.
- Compare model performance using multiple evaluation metrics.
- Study the impact of medical image information on summarization quality.

## Dataset

**MMCQSD — Medical Multimodal Query Summarization Dataset**

Dataset source: [Hugging Face – MMCQSD](https://huggingface.co/datasets/ArkaAcharya/MMCQSD)

| Dataset Information | Value |
|---|---:|
| Total samples | 3,015 |
| Unique image paths | 372 |
| Unique image contents | 365 |
| Training samples | 2,412 |
| Validation samples | 301 |
| Test samples | 302 |

The dataset contains:

- `Codemixed_Question` — medical query in code-mixed Hindi-English
- `summary` — reference English summary
- `Image_path` — associated image path

**Dataset files and images are not included in this repository.** Please obtain the dataset from its original source and follow the dataset's licensing and usage conditions.

## Models Evaluated

### Text-based Models

- BART
- BioBART
- DistilBART

### Multimodal Models

- ViT + BART
- BiomedCLIP + BART
- PubMedCLIP + BART

## Evaluation Metrics

| Metric | Purpose |
|---|---|
| ROUGE-1 | Unigram overlap |
| ROUGE-2 | Bigram overlap |
| ROUGE-L | Longest common subsequence |
| BLEU | N-gram precision with brevity penalty |
| BERTScore | Contextual semantic similarity |
| METEOR | Lexical similarity considering stemming and synonyms |

## Recorded Experimental Results

| Model | ROUGE-1 | ROUGE-2 | ROUGE-L | BLEU |
|---|---:|---:|---:|---:|
| BART | 55.89 | 33.50 | 47.60 | 33.36 |
| BioBART | 51.06 | 27.75 | 41.83 | 26.28 |
| DistilBART | 51.87 | 30.27 | 43.08 | 28.68 |
| ViT + BART | **58.68** | **38.06** | **51.08** | **38.17** |
| BiomedCLIP + BART | 51.85 | 32.05 | 45.05 | 24.83 |
| PubMedCLIP + BART | 38.64 | 19.43 | 31.37 | 12.52 |

*These are currently recorded experimental results. Experimental consistency and reproducibility should be verified before treating them as final research conclusions.*

Full metrics, including BERTScore and METEOR, are available in [`medical-summarization/results/model_comparison.csv`](medical-summarization/results/model_comparison.csv).

## Repository Structure

```text
FinalYearProject2028/
├── README.md
└── medical-summarization/
    ├── configs/
    ├── docs/
    │   ├── dataset.md
    │   └── experiments.md
    ├── experiments/
    ├── results/
    │   ├── README.md
    │   └── model_comparison.csv
    └── src/