# Project Summary

This project develops and evaluates a lightweight and explainable deep learning framework for phonocardiogram (PCG) classification.

## Task

The task is five-class valvular heart disease classification using PCG heart-sound recordings:

- AS — Aortic Stenosis
- MR — Mitral Regurgitation
- MS — Mitral Stenosis
- MVP — Mitral Valve Prolapse
- N — Normal

## Main contribution

The project compares seven baseline neural-network architectures across three feature representations and proposes TinyPCGNet, an ultra-lightweight dual-branch model that combines MFCC and log-mel spectrogram features.

## Main finding

Recurrent models such as Conv-BiLSTM and Conv-LSTM achieve the highest accuracy, while TinyPCGNet provides a compact edge-deployment-oriented operating point with a much smaller parameter count.
