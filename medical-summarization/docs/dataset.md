# Dataset Documentation

## Dataset

**MMCQSD (Medical Multimodal Question Answering and Summarization Dataset)**

Source: https://huggingface.co/datasets/ArkaAcharya/MMCQSD

## Description

This project uses a medical multimodal dataset containing code-mixed Hindi-English medical queries, corresponding English summaries, and associated medical images.

## Dataset Fields

| Field | Description |
|---|---|
| `Codemixed_Question` | Medical query written in code-mixed Hindi-English |
| `summary` | Corresponding English reference summary |
| `Image_path` | Path to the associated medical image |

## Dataset Statistics

- Total records: 3,015
- Unique image paths: 372
- Unique image contents: 365
- Training samples: 2,412
- Validation samples: 301
- Test samples: 302

## Data Split

| Split | Samples | Percentage |
|---|---:|---:|
| Train | 2,412 | 80% |
| Validation | 301 | ~10% |
| Test | 302 | ~10% |

## Data Privacy and Repository Policy

The dataset files, images, and processed data are not stored in this GitHub repository.

Researchers should obtain the dataset directly from its original source and follow its license and usage requirements.

Dataset files are intentionally excluded through `.gitignore`.