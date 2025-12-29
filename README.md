# 🍠 Sweetpotato Grading Dataset (SP-Grade)

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
[![Dataset: Zenodo](https://img.shields.io/badge/Dataset-Zenodo-blue.svg)](https://zenodo.org/) [![Institution](https://img.shields.io/badge/Institution-Michigan%20State%20University-green)](https://msu.edu/)

**A vision dataset for full-surface quality inspection of sweetpotatoes.**

This repository contains the official documentation, metadata, and usage guidelines for the dataset described in the *Data in Brief* article: **"Dataset for Automated Full-Surface Quality Grading and Inspection of Sweetpotatoes"**.

---

## ✨ Key Features

* **Multi-View Capture**: Samples are rotated on a roller conveyor, providing 360° coverage to reveal hidden defects.
* **Two Imaging Domains**:
    * **Subset A (ASABE)**: 1,168 images from a research station, captured in an enclosed LED chamber ($1280 \times 720$).
    * **Subset B (COMPAG)**: 232 images from commercial grocery stores, captured under ambient lighting ($1920 \times 1080$).
* **Rich Annotations**: 3,700+ instance-level polygon masks with standardized quality grades (Grade 1/2/3).
* **Physical Ground Truth**: Includes manually measured weight, length, and width for samples.

---

## 📂 Download

The full dataset (Images, Annotations, Videos, and CSV Metadata) is hosted on Zenodo:

> **[Download from Zenodo (DOI: xxx)](https://zenodo.org/)**

---

## 🚀 Usage Guidelines (Critical!)

⚠️ **Strict No-Shuffle Policy for Data Splitting** ⚠️

Because this dataset contains sequential frames of rotating objects, **random splitting (shuffling) is strictly prohibited**. Random splitting will cause data leakage (different views of the same potato appearing in both Train and Test sets).

**Recommended Split:**
* **Subset A**: Use folders `v1`–`v16` for Training, and `Test1`–`Test4` for Testing.
* **Subset B**: Split by **Batch ID** (e.g., Batches 0–14 for Train, 15–18 for Test).

### Directory Structure
```text
Dataset Root
├── Subset A (ASABE)
│   ├── Dataset (train/test splits)
│   └── Videos
└── Subset B (COMPAG)
    ├── imgs (Commercial batches)
    ├── measurement size data
    └── labels
```

## 🛠️ Data Format

* **Images**: `.png` (Subset A) / `.jpg` (Subset B)
* **Labels**: `.json` (Compatible with LabelMe / AnyLabeling)
* **Physical Data**: `.csv` (Weight, Length, Width)

### Class Definitions
* **Grade 1 (Normal)**: Defect-free or negligible defects.
* **Grade 2 (Moderate)**: Visible defects exceeding premium tolerance but usable.
* **Grade 3 (Severe)**: Unmarketable due to severe damage or rot.
* *Note: Grades refer to **surface defect severity only**. Size constraints are not incorporated in the image labels but are available in the CSV file.*

<img width="1916" height="873" alt="image" src="https://github.com/user-attachments/assets/eaa225cc-382e-4009-848e-258c315fb0ef" />

---

## 📝 Citation

If you use this dataset in your research, please cite the following papers:

**1. The Data Article (Data in Brief):**
```bibtex
@article{Zhang2025Dataset,
  title = {Dataset for Automated Full-Surface Quality Grading and Inspection of Sweetpotatoes},
  author = {Zhang, Jiaming and Xu, Jiajun and Lu, Yuzhen},
  journal = {Data in Brief},
  year = {2025},
  note = {In Draft}
}
```

```bibtex
@article{Xu2024ASABE,
  title = {Design, Prototyping, and Evaluation of A New Machine Vision-Based Automated Sweetpotato Grading and Sorting System},
  author = {Xu, Jiajun and Lu, Yuzhen and Deng, B.},
  journal = {Journal of the ASABE},
  volume = {67},
  number = {5},
  pages = {1369--1380},
  year = {2024},
  doi = {10.13031/ja.16051}
}
```

```bibtex
@article{Xu2024ComputAg,
  title = {Prototyping and evaluation of a novel machine vision system for real-time, automated quality grading of sweetpotatoes},
  author = {Xu, Jiajun and Lu, Yuzhen},
  journal = {Computers and Electronics in Agriculture},
  volume = {219},
  pages = {108826},
  year = {2024},
  doi = {10.1016/j.compag.2024.108826}
}
```

## 📧 Contact
For questions regarding the dataset, please contact:

Yuzhen Lu: luyuzhen@msu.edu

Jiaming Zhang: zhan2374@msu.edu

Department of Biosystems and Agricultural Engineering, Michigan State University.
