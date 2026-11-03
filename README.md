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


