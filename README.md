# Trustworthiness Under Compression

**Calibration and Explanation Faithfulness of Lightweight IoT Intrusion Detectors**

Target venue: IEEE BigData 2026 (Industry & Applications track). Sole-authored.

## Thesis
Model compression for edge-deployed IoT intrusion detection preserves classification
accuracy (F1) but silently erodes two dimensions of trustworthiness — probability
**calibration** and **explanation faithfulness** — unevenly across attack categories.
Demonstrated on CICIoT2023 and validated on TON_IoT.

## Datasets
- **CICIoT2023** (primary) — 33 attacks across 105 IoT devices, mapped to 7 attack
  groups + Benign = 8 classes. Cite: UNB CIC, iotdataset-2023.
- **TON_IoT** network subset (cross-dataset validation).

## Repository structure
```
notebooks/   # PhaseA_v2 (baseline) ... PhaseE (writing)
splits/      # locked stratified split indices (in Drive)
models/      # M0 seed checkpoints, scaler (in Drive, gitignored)
results/     # metrics CSVs, figures
logs/        # anchor pre-registration, decision log
```
Data and model binaries live in Google Drive only (see `.gitignore`); GitHub holds
code, notebooks, results, and logs.

## Method axes
1. Deployability — size / latency / memory on real edge hardware (Raspberry Pi).
2. Detection — macro-F1, per-class recall, benign-defined FPR.
3. Calibration — adaptive-binned ECE + signed over-confidence gap; temperature scaling.
4. Explanation faithfulness — SHAP agreement + perturbation (AOPC) under a locked
   attribution protocol; three-floor noise hierarchy (explainer < seed < compression).

## Reproducibility
- Locked split (seed 42); M0 trained at seeds 0–4; **seed 0 pre-registered as anchor**
  (see `logs/anchor_preregistration.json`).
- Tempered (sqrt-inverse-frequency) class weighting.
