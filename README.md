# Intro-to-DL-TinyPCGNet

**TinyPCGNet: A Lightweight and Explainable Deep Learning Framework for Phonocardiogram Classification**

This repository contains the implementation of a course project for **2026SP - Introduction to Deep Learning (16:332:530:01)** under **Prof. Bo Yuan**. The project studies automated classification of phonocardiogram (PCG) heart-sound recordings for five-class valvular heart disease (VHD) screening and proposes **TinyPCGNet**, an ultra-lightweight dual-branch model designed for edge-device deployment.

## Project overview

Cardiovascular diseases remain a major global health challenge, and PCG-based heart-sound analysis provides a non-invasive approach for early screening. This project compares multiple deep learning architectures and feature representations under a controlled experimental setup.

The study evaluates:

- **Features:** DWT scalogram, MFCC, and log-mel spectrogram
- **Baseline models:** CNN-1, CNN-2, SepCNN-1, SepCNN-2, Conv-LSTM, Conv-BiLSTM, and Conv-GRU
- **Proposed model:** TinyPCGNet, a compact MFCC + log-mel dual-branch model
- **Explainability:** Grad-CAM analysis for TinyPCGNet predictions

## Key results

| Model | Feature | Parameters | FLOPs | Accuracy | Macro F1 |
|---|---:|---:|---:|---:|---:|
| Conv-BiLSTM | MFCC | 100.3K | 24.1M | 99.5% | 99.5% |
| Conv-LSTM | MFCC | 55.0K | 22.0M | 99.4% | 99.4% |
| TinyPCGNet | MFCC + Log-Mel | 5.1K | 4.3M | 92.8% | 92.8% |

The best overall model is **Conv-BiLSTM × MFCC**, while **TinyPCGNet** reaches a strong lightweight operating point with only about **5.1K trainable parameters**, making it more suitable for resource-constrained edge devices.

## Repository structure

```text
Intro-to-DL-TinyPCGNet/
├── notebooks/
│   ├── notebook_A_features.ipynb
│   ├── notebook_B_baselines.ipynb
│   ├── notebook_C1_tinypcgnet_comparison.ipynb
│   └── notebook_C2_gradcam_xai.ipynb
├── report/
│   └── Intro_to_deep_learning.pdf
├── data/
│   └── README.md
├── models/
│   └── README.md
├── results/
│   ├── README.md
│   ├── figures/
│   ├── tables/
│   └── xai/
├── docs/
│   ├── project_summary.md
│   └── experiment_pipeline.md
├── requirements.txt
├── .gitignore
├── LICENSE
└── README.md
```

## Notebook execution order

Run the notebooks in this order:

1. **`notebooks/notebook_A_features.ipynb`**  
   Extracts DWT, MFCC, and log-mel features from the OAHS dataset and saves the 5-fold split files.

2. **`notebooks/notebook_B_baselines.ipynb`**  
   Runs 21 baseline experiments: 7 architectures × 3 features.

3. **`notebooks/notebook_C1_tinypcgnet_comparison.ipynb`**  
   Trains TinyPCGNet and merges its result with the baseline experiments to generate the final 22-row comparison.

4. **`notebooks/notebook_C2_gradcam_xai.ipynb`**  
   Runs Grad-CAM explainability analysis on the saved TinyPCGNet model.

## Dataset

This project uses the **Open-Access Heart Sound (OAHS)** dataset for five-class VHD classification:

- AS: Aortic Stenosis
- MR: Mitral Regurgitation
- MS: Mitral Stenosis
- MVP: Mitral Valve Prolapse
- N: Normal

The dataset is not included in this repository. Place the OAHS dataset in the expected Google Drive location before running Notebook A.

Default Colab path used in the notebooks:

```text
/content/drive/MyDrive/Msc_ML_project/dataset
```

Generated features are saved to:

```text
/content/drive/MyDrive/Msc_ML_project/features_v1
```

## Requirements

The notebooks were developed and tested in **Google Colab** with a T4 GPU. Install the required packages with:

```bash
pip install -r requirements.txt
```

## Main outputs

The notebooks generate:

- Cached feature arrays
- Stratified 5-fold split files
- Baseline result tables
- TinyPCGNet trained model file
- Final 22-experiment ranking table
- Accuracy-vs-parameters and accuracy-vs-FLOPs plots
- Confusion matrices
- Grad-CAM visualizations

## Course information

- **Course:** Introduction to Deep Learning
- **Course code:** 16:332:530:01
- **Semester:** Spring 2026
- **Instructor:** Prof. Bo Yuan
- **Author:** Md Toufiqur Rahman
- **Platform:** Google Colab

## Citation

If you use or refer to this project, please cite the project report included in the `report/` folder.

## License

This repository is released under the MIT License.
