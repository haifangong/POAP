# POAP: Decoupling Antimicrobial Potency of Peptides from Off-target Toxicity via Deep Learning

## Overview
Here, we present the Painless Optimization of Antimicrobial Peptides (POAP) pipeline, a deep learning framework that reframes AMP engineering as a therapeutic window maximization problem. POAP introduces three innovations: (1) A metric learning20-guided assessment module for inter-peptide AA divergence, designed to identify the most potent optimized peptides from template-derived search spaces. By reformulating the training objective from learning features determining individual AMP activity to those governing pairwise antimicrobial efficacy differences, this strategy shifts training emphasis from high-activity AMPs to AMP pairs with maximal activity divergence. This approach expands the pool of high-value training samples by over 60-fold, addressing potent AMP scarcity. Baseline experiments demonstrate a 20.1% reduction in mean absolute error for AA prediction. (2) An incremental learning-refined toxicity filtration module to identify non-toxic candidates within template-derived search spaces. This module is supplemented by 170 in-house experimentally validated hemolytic toxicity measurements for post-initial-training fine-tuning. This dual-phase training achieves a 98.5% AUPRC in the hemolytic toxicity classification task, effectively constraining candidate selection to therapeutically viable regions. (3) An efficiency improvement module based on the empirical selection and activity classifier to exclude candidates unlikely to exhibit antibacterial activity from template-derived search spaces. Its implementation reduces computational workload and processing time by 90.9% for downstream modules, enabling systematic exploration of expansive combinatorial spaces within tractable computational frameworks.

## Features
- Implementation of Siamese neural network for metric learning on AMPs.
- Evaluation scripts for model performance and feature visualization.
- Cascading pipeline for automated deep mutational scanning.
- Scripts for training and inference on both individual AMPs and their graph representations.

## Usage

### Data Preparation
Prepare your dataset using the provided scripts:
- `dataset.py`: General dataset preparation.
- `dataset_single.py`: Prepare dataset for single AMP predictions.
- `dataset_graph.py`: Prepare graph-based dataset representations.

### Training Models
Train the models using the following scripts:
- `train.py`: Train models on individual AMP data.
- `train_graph.py`: Train models on graph-based data representations.

Shell scripts are provided for convenience:
- `train.sh`: Bash script for training models on individual data.
- `train_graph.sh`: Bash script for training on graph data.

### Evaluation
Evaluate the models and visualize their performance:
- `eval.py`: Evaluate the models and print metrics.
- `eval_gradcam.py`: Visualize model decisions using Grad-CAM.
- `eval_graphgrad.py`: Grad-CAM for graph-based models.

### Inference
Run inference on new data:
- `infer_graph.py`: Perform inference on graph-based models.

## Project Structure
```plaintext
.
├── dataset.py
├── dataset_graph.py
├── dataset_graph2.py
├── dataset_single.py
├── eval.py
├── eval_gradcam.py
├── eval_graphgrad.py
├── get_experiments.py
├── infer_graph.py
├── loss.py
├── main.py
├── model.py
├── model_single.py
├── network.py
├── train.py
├── train.sh
├── train_graph.py
├── train_graph.sh
├── train_graph_single.py
├── train_single.py
└── utils.py
