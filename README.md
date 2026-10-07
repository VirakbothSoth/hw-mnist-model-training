# Train-HomeWork: LeakyReLU Bottleneck Dense Autoencoder on MNIST

This repository contains a bottleneck autoencoder implementation containing LeakyReLU activations trained on the MNIST dataset to reconstruct digits degraded by 15% Gaussian noise.

## Overview
- **Architecture**: 784 (Input) &rarr; 128 &rarr; 64 (Bottleneck) &rarr; 128 &rarr; 784 (Reconstruction)
- **Loss & Metrics**: Mean Squared Error (MSE), Mean Absolute Error (MAE), and Digit Classification Accuracy using normalized prototype cosine similarity.
- **Evaluation**:
  - Training, Validation, and Test MSE/MAE
  - Classification accuracy on reconstructed noisy test digits
  - Save outputs such as confusion matrices, training curve graphs, visual samples, and a global summary chart.

## Repository Structure
- `MNIST_Autoencoder_Project.ipynb`: Main notebook featuring dataset subsets, noisy test injection, model definitions, runs, and evaluations.
- `output/`:
  - `results.csv`: Table documenting metrics across all 4 experimental settings.
  - `metrics_batch_*.png`: Combined Train/Val Loss and MAE graphs over training epochs per batch.
  - `samples_batch_*.png`: Comparison grids containing Original, Noisy (15%), and Reconstructed test digits.
  - `confusion_matrix_batch_*.png`: Confusion matrices based on cosine similarity classifiers.
  - `result_10_digits_batch_*.png`: Digit-by-digit (0-9) visual reconstructions labeled with AI classification results.
  - `summary_plot.png`: Comparative bar charts analyzing Test MSE and Digit Accuracy across all configurations.

## Results Summary

These are the results of our model (rounded up):

| Size | Epochs | Train Loss | Val Loss | Train MSE | Val MSE | Test MSE | Train MAE | Val MAE | Digit Accuracy |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **2500** | 50 | 0.0085 | 0.0141 | 0.0059 | 0.0120 | 0.0243 | 0.0253 | 0.0355 | 74.4% |
| **2500** | 100 | 0.0077 | 0.0140 | 0.0050 | 0.0120 | 0.0255 | 0.0232 | 0.0347 | 79.4% |
| **5000** | 50 | 0.0088 | 0.0119 | 0.0064 | 0.0098 | 0.0211 | 0.0262 | 0.0317 | 78.6% |
| **5000** | 100 | 0.0081 | 0.0115 | 0.0059 | 0.0096 | 0.0197 | 0.0248 | 0.0308 | 78.8% |
```
