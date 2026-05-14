# Experiment Pipeline

## Step 1: Preprocessing and feature extraction

Notebook: `notebooks/notebook_A_features.ipynb`

Processing chain:

1. Resample PCG signals
2. Normalize signal length
3. Apply RMS normalization
4. Apply z-score normalization
5. Extract DWT, MFCC, and log-mel features
6. Save stratified 5-fold splits

## Step 2: Baseline experiments

Notebook: `notebooks/notebook_B_baselines.ipynb`

Models:

- CNN-1
- CNN-2
- SepCNN-1
- SepCNN-2
- Conv-LSTM
- Conv-BiLSTM
- Conv-GRU

Features:

- DWT
- MFCC
- Log-mel

Total baseline experiments: 21.

## Step 3: TinyPCGNet training

Notebook: `notebooks/notebook_C1_tinypcgnet_comparison.ipynb`

TinyPCGNet uses:

- MFCC branch
- Log-mel branch
- Depthwise-separable convolution
- Squeeze-and-Excite attention
- Global Average Pooling
- Small dense classification head

## Step 4: Explainability

Notebook: `notebooks/notebook_C2_gradcam_xai.ipynb`

XAI outputs:

- Per-class representative Grad-CAM
- Correct vs incorrect Grad-CAM comparison
- Aggregate class-conditional Grad-CAM heatmaps
