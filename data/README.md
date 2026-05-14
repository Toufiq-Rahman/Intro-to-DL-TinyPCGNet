# Data

The OAHS dataset is not included in this repository because datasets are usually kept outside GitHub repositories due to size and distribution restrictions.

Before running `notebook_A_features.ipynb`, place the raw OAHS PCG recordings in:

```text
/content/drive/MyDrive/Msc_ML_project/dataset
```

Notebook A will generate cached feature files in:

```text
/content/drive/MyDrive/Msc_ML_project/features_v1
```

Expected classes:

- AS — Aortic Stenosis
- MR — Mitral Regurgitation
- MS — Mitral Stenosis
- MVP — Mitral Valve Prolapse
- N — Normal
