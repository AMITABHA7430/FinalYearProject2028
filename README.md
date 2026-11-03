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
