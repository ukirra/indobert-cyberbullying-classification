# IndoBERT-Based Cyberbullying Classification

## Overview

This project investigates the performance of IndoBERT in classifying cyberbullying content in Indonesian social media comments. The study evaluates the model across four datasets with different characteristics, covering both binary and multiclass classification tasks.

By comparing datasets from different sources and with varying class structures, this research aims to analyze IndoBERT's classification performance and generalization across different data characteristics.

## Research Objectives

- Evaluate IndoBERT performance on Indonesian cyberbullying classification.
- Compare binary and multiclass classification performance across different datasets.
- Analyze the impact of dataset characteristics, including data sources, class distributions, and label structures, on model performance.
- Assess model performance using stratified 5-fold cross-validation.

## Datasets

This research uses four Indonesian cyberbullying datasets from different sources, consisting of two binary classification datasets and two multiclass classification datasets.

| Dataset | Source | Samples | Classes | Classification |
|---|---|---:|---:|---|
| Binary 1 | GitHub | 650 | 2 | Binary |
| Binary 2 | Kaggle | 400 | 2 | Binary |
| Multiclass 1 | Kaggle | 2,400 | 6 | Multiclass |
| Multiclass 2 | Mendeley Data | 7,530 | 5 | Multiclass |

### Dataset Description

- **Binary 1:** Indonesian Instagram comments labeled as positive (non-cyberbullying) and negative (cyberbullying), adapted from sentiment labels.
  - [Dataset Source](https://github.com/rizalespe/Dataset-Sentimen-Analisis-Bahasa-Indonesia)

- **Binary 2:** Indonesian Instagram comments categorized into cyberbullying and non-cyberbullying.
  - [Dataset Source](https://www.kaggle.com/datasets/cttrhnn/cyberbullying-bahasa-indonesia)

- **Multiclass 1:** An Indonesian-translated dataset originally written in English. The data was translated using Helsinki-NLP, with 400 samples selected for each of the six categories: age, ethnicity, gender, religion, not cyberbullying, and other cyberbullying.
  - [Dataset Source](https://www.kaggle.com/datasets/leonss0711/multiclass-indonesian-cyberbullying-dataset)

- **Multiclass 2:** An Indonesian cyberbullying dataset containing five categories: body shaming, denigration, flaming, harassment, and neutral. The original multilabel data was converted into single-label multiclass classification using the first assigned label as the target.
  - [Dataset Source](https://data.mendeley.com/datasets/xthb26ntc5/1)

## Methodology

The research follows these main stages:

1. **Data Preparation:** Selected relevant text and label columns from each dataset and performed text preprocessing.
2. **Model Development:** Used `indobenchmark/indobert-base-p2` as the base model for binary and multiclass classification.
3. **Model Training:** Fine-tuned IndoBERT using a consistent experimental setup across datasets.
4. **Cross-Validation:** Applied Stratified 5-Fold Cross-Validation with a fixed random state to evaluate model performance across different data splits.
5. **Evaluation:** Assessed model performance using accuracy, precision, recall, F1-score, and confusion matrices.

## Experimental Setup

| Parameter | Configuration |
|---|---|
| Base Model | IndoBERT Base P2 |
| Maximum Sequence Length | 128 |
| Dropout | 0.3 |
| Batch Size | 16 |
| Epochs | 5 |
| Learning Rate | 2e-5 and 3e-5 |
| Optimizer | AdamW |
| Weight Decay | 0.01 |
| Cross-Validation | Stratified 5-Fold |
| Random State | 42 |
| Early Stopping Patience | 2 |

## Results and Evaluation

The experimental results show that IndoBERT achieved higher accuracy on binary classification tasks compared to multiclass classification tasks.

| Dataset | Classification | Accuracy |
|---|---|---:|
| Binary 1 | Binary | 94.25% |
| Binary 2 | Binary | 91.85% |
| Multiclass 1 | Multiclass | 75.62% |
| Multiclass 2 | Multiclass | 72.32% |

### Key Findings

- **Binary Classification:** IndoBERT achieved accuracy scores ranging from 91.85% to 94.25%, demonstrating strong performance in distinguishing cyberbullying and non-cyberbullying comments.
- **Multiclass Classification:** Accuracy ranged from 72.32% to 75.62%, indicating greater challenges in distinguishing between multiple cyberbullying categories.
- **Dataset Characteristics:** Differences in data sources, class structures, and label definitions provide important context for interpreting the variations in model performance.

## Technologies and Tools

- Python
- PyTorch
- Hugging Face Transformers
- IndoBERT
- Scikit-learn
- Pandas
- NumPy
- Matplotlib
- Seaborn

## Project Context

This project was conducted as an undergraduate thesis 
