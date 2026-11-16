# Wafer-Detection-WM811K
Comparative study of CNN, Focal Loss, and confidence-based Semi-Supervised Learning for imbalanced semiconductor wafer defect classification using the WM-811K dataset with PyTorch.

# WM-811K Wafer Defect Classification

## Project Overview

This project presents a comparative study of three
deep learning approaches for semiconductor wafer
defect classification using the WM-811K dataset.

The project investigates the effect of class imbalance
and evaluates the following approaches:

1. Baseline CNN with Cross-Entropy Loss
2. CNN with Focal Loss
3. Semi-Supervised Learning using confidence-based
   pseudo-labeling

## Team Members

| Name | University ID |
|---|---|
| Tanisha Purohit | AU2644038 |
| Prachi Bhansali | AU2644040 |
| Dhairya Patel | AU2644042 |
| Jay Pancholi | AU2644043 |

**University:** Ahmedabad University  
**Programme:** M.Tech. VLSI  
**Faculty Guide:** Maitrik Shah

## Dataset

The project uses the WM-811K Wafer Map Dataset.

Dataset source:
https://www.kaggle.com/datasets/qingyi/wm811k-wafer-map/data

The dataset contains labeled and unlabeled wafer maps
belonging to nine wafer pattern categories.

The original dataset is not included in this repository.
Please download it from the Kaggle source.

## Methodology

### Experiment 1: Baseline CNN

A CNN model is trained using Cross-Entropy Loss
as the baseline classification approach.

### Experiment 2: Focal Loss

Focal Loss is used to investigate the effect of
giving greater emphasis to difficult classification
examples during model training.

### Experiment 3: Semi-Supervised Learning

Confidence-based pseudo-labeling is applied to
selected unlabeled wafer maps. High-confidence
predictions are selected and combined with the
original labeled training data.

## Experimental Configuration

- Input resolution: 64 x 64
- Number of classes: 9
- Batch size: 64
- Optimizer: Adam
- Learning rate: 0.001
- Training epochs: 10
- Dataset split: 70:15:15
- Focal Loss gamma: 2.0
- Unlabeled sample size: 50,000
- Pseudo-label confidence threshold: 0.95

## Final Test Results

| Model | Accuracy | Precision | Recall | Macro-F1 |
|---|---:|---:|---:|---:|
| Baseline CNN | 96.90% | 86.51% | 79.52% | 82.47% |
| Focal Loss | 96.68% | 81.69% | 84.02% | 82.50% |
| SSL | 96.91% | 86.04% | 79.95% | 82.51% |

The three approaches achieve similar overall
performance. SSL achieves the highest Macro-F1,
while Focal Loss achieves the highest macro recall.

## Repository Structure

- `notebooks/` - Complete Google Colab notebook
- `figures/` - Generated graphs and confusion matrices
- `reports/` - Final project report
- `requirements.txt` - Python dependencies

## How to Run

1. Download the WM-811K dataset from Kaggle.
2. Open the notebook in Google Colab.
3. Upload or mount the dataset in Google Drive.
4. Install the required dependencies.
5. Execute the notebook cells in sequence.

## Evaluation Metrics

- Accuracy
- Macro Precision
- Macro Recall
- Macro-F1 Score
- Confusion Matrix

## Limitations

- A relatively simple CNN architecture is used.
- Focal Loss is implemented without explicit
  class-specific alpha weighting.
- Pseudo-labeling is performed in one stage.
- The selected pseudo-labels are not guaranteed
  to be perfectly balanced across classes.

## Future Scope

- Deeper CNN architectures such as ResNet
- Iterative pseudo-labeling
- Improved confidence calibration
- Class-aware training strategies
- Wafer-specific data augmentation

## Acknowledgement

We acknowledge Ahmedabad University, our faculty
guide, the WM-811K dataset contributors, and the
authors of the research papers used in this study.

