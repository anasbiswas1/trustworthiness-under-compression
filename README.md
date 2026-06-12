# Trustworthiness Under Compression

**Calibration and Explanation Faithfulness of Lightweight IoT Intrusion Detectors**

Target: IEEE BigData 2026 (Industry & Applications), extending to ESWA (Q1). Sole-authored.

## Thesis
Compression of edge-deployed IoT intrusion detectors preserves accuracy (F1) but
silently erodes two trust dimensions — probability calibration and explanation
faithfulness — unevenly across attack categories. Shown on CICIoT2023, validated on TON_IoT.

## Data / labels
CICIoT2023: 33 attacks -> 7 groups + Benign = 8 classes. Data and model binaries live
in Drive only (see .gitignore); GitHub holds code, notebooks, results, logs.

## Reproducibility
Locked split (seed 42); M0 at seeds 0-4; seed 0 pre-registered anchor
(logs/anchor_preregistration.json); tempered sqrt-inverse-frequency weighting.
Baseline: macro-F1 0.771, benign FPR 0.051.
