# Predicting Brain Responses From Movies

Predict fMRI activity from a movie's video, audio and text, and test whether a **Hybrid** model (each brain parcel learns its own modality weights and time lag) beats simpler models.

Everything is in one notebook: `brain\_movie\_encoding.ipynb`.

## Data

The official Algonauts 2025 dataset needs a registration form and DataLad (not supported on Windows), so the notebook generates a **synthetic** dataset with the same structure (4 subjects, TR = 1.49 s, train / val / test / OOD splits). 

## What the notebook does

1. Generate data and extract video / audio / text features
2. Clean (drop warm-up TRs, clip outliers, z-score on train only)
3. EDA: 3 plots
4. Train 6 models: Ridge, Deep CCA, Perceiver, Mamba, Cross-Modal Transformer, Hybrid
5. Results: 5 plots (accuracy bar chart, training curves, ablations, OOD generalization, per-parcel accuracy map)

## Run

```
pip install -r requirements.txt
jupyter notebook brain\_movie\_encoding.ipynb
```

CPU only; a full run takes roughly 30 minutes.

