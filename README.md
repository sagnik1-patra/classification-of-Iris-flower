# Iris Flower Classification using Artificial Neural Network (ANN) from Scratch

An implementation of a **Multi-Layer Perceptron (MLP)** built entirely from **NumPy** to classify the **Iris Flower Dataset**. This project demonstrates the complete implementation of an Artificial Neural Network, including forward propagation, backpropagation, mini-batch gradient descent, and performance evaluation without using any deep learning frameworks such as TensorFlow or PyTorch.


---

# Table of Contents

- Project Overview
- Features
- Dataset
- Neural Network Architecture
- Project Structure
- Requirements
- Installation
- How to Run
- Workflow
- Output Files
- Experimental Analysis
- Results
- Future Improvements
- Author

---

# Project Overview

Artificial Neural Networks are one of the fundamental algorithms of Deep Learning. Instead of using existing deep learning libraries, this project implements every major mathematical operation manually using **NumPy**, allowing a deeper understanding of how neural networks work internally.

The model classifies Iris flowers into one of the following categories:

- Setosa
- Versicolor
- Virginica

using four flower measurements:

- Sepal Length
- Sepal Width
- Petal Length
- Petal Width

---
## Visualization

<p align="center">
  <img src="outputs/pca_decision_boundary.png" width="700" alt="PCA Decision Boundary">
</p>

# Features

- Pure NumPy implementation
- Forward Propagation
- Backpropagation
- Cross Entropy Loss
- Mini Batch Gradient Descent
- Early Stopping
- Z-Score Normalization
- One-Hot Encoding
- Softmax Output Layer
- PCA Decision Boundary Visualization
- Confusion Matrix
- Classification Report
- Learning Curve Visualization
- Experimentation with

  - Different Learning Rates
  - Different Activation Functions
  - Different Network Architectures

- Comparison with Scikit-Learn MLPClassifier

---

# Dataset

Dataset Used:

**Iris Dataset**

Available from:

- Scikit-Learn
- UCI Machine Learning Repository

Dataset Statistics

| Property | Value |
|----------|------:|
| Samples | 150 |
| Features | 4 |
| Classes | 3 |

Target Classes

1. Setosa
2. Versicolor
3. Virginica

---

# Neural Network Architecture

The baseline neural network architecture is:

```
Input Layer
    │
    ▼
4 Neurons
    │
    ▼
Hidden Layer 1
8 Sigmoid Neurons
    │
    ▼
Hidden Layer 2
6 Sigmoid Neurons
    │
    ▼
Output Layer
3 Softmax Neurons
```

Training Parameters

| Parameter | Value |
|-----------|------:|
| Epochs | 1000 |
| Learning Rate | 0.01 |
| Batch Size | 16 |
| Loss Function | Cross Entropy |
| Optimizer | Mini Batch Gradient Descent |

---

# Project Structure

```
classification of Iris flower
│
├── iris_numpy_mlp_assignment.py
│
├── outputs
│   │
│   ├── dataset_summary.txt
│   ├── feature_histograms.png
│   ├── feature_pair_plot.png
│   ├── feature_correlation_heatmap.png
│   ├── training_loss_curve.png
│   ├── training_validation_accuracy_curves.png
│   ├── confusion_matrix_heatmap.png
│   ├── classification_report.csv
│   ├── classification_report.txt
│   ├── test_predictions.csv
│   ├── pca_decision_boundary.png
│   ├── experiment_comparison_table.csv
│   ├── experiment_comparison_graph.png
│   ├── numpy_vs_sklearn_comparison.csv
│   ├── numpy_vs_sklearn_comparison.png
│   ├── final_results.txt
│   └── written_report.md
│
└── README.md
```

---

# Requirements

Python 3.10+

Required Libraries

```
numpy
pandas
matplotlib
scikit-learn
```

Install dependencies

```bash
pip install numpy pandas matplotlib scikit-learn
```

---

# Installation

Clone or download the project.

Move into the project folder.

Install the required libraries.

Run

```bash
python iris_numpy_mlp_assignment.py
```

All outputs will automatically be generated inside

```
outputs/
```

---

# Workflow

```
Load Dataset
      │
      ▼
Exploratory Data Analysis
      │
      ▼
Train Validation Test Split
      │
      ▼
Feature Standardization
      │
      ▼
One-Hot Encoding
      │
      ▼
Initialize Neural Network
      │
      ▼
Forward Propagation
      │
      ▼
Cross Entropy Loss
      │
      ▼
Backpropagation
      │
      ▼
Gradient Descent Update
      │
      ▼
Repeat Until Convergence
      │
      ▼
Model Evaluation
      │
      ▼
Experiments
      │
      ▼
Comparison with sklearn
```

---

# Output Files

## Exploratory Data Analysis

- Dataset Summary
- Feature Histograms
- Pair Plot
- Correlation Heatmap

---

## Training Outputs

- Training Loss Curve
- Training Accuracy Curve
- Validation Accuracy Curve

---

## Evaluation

- Confusion Matrix
- Classification Report
- Test Predictions

---

## PCA Visualization

- PCA Decision Boundary

---

## Experimental Analysis

- Learning Rate Comparison
- Activation Function Comparison
- Network Architecture Comparison

---

## Comparison

- NumPy MLP vs Scikit-Learn MLPClassifier

---

## Report

- Final Results
- Written Report

---

# Experimental Analysis

The project evaluates multiple neural network configurations.

## Learning Rates

- 0.001
- 0.01
- 0.1

---

## Activation Functions

- Sigmoid
- Tanh
- ReLU

---

## Network Architectures

- 4-8-3
- 4-8-6-3
- 4-12-8-6-3

Each experiment records:

- Training Loss
- Validation Accuracy
- Test Accuracy
- Precision
- Recall
- F1 Score

Results are summarized in:

```
experiment_comparison_table.csv
```

---

# Results

The implementation successfully demonstrates:

- Neural Network construction from scratch
- Manual forward propagation
- Manual backpropagation
- Cross Entropy optimization
- Mini Batch Gradient Descent
- Multi-class classification using Softmax
- Effective classification of the Iris dataset
- Visualization of the learned decision boundaries using PCA
- Comparative analysis with Scikit-Learn's optimized MLPClassifier

---

# Future Improvements

Possible enhancements include:

- Adam Optimizer
- RMSProp Optimizer
- Dropout Regularization
- Batch Normalization
- L2 Regularization
- Learning Rate Scheduling
- Model Checkpointing
- TensorBoard Support
- Interactive Decision Boundary Visualization
- Additional Benchmark Datasets

---

# Author

**Sagnik Patra**

Assistant Professor (Computer Science & Engineering)

Developed as part of an Artificial Neural Network implementation project to understand the mathematical foundations of deep learning through a complete NumPy-based implementation.
