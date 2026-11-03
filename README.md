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

