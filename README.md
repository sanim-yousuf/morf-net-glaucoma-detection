# MORF-Net: Multi-Region Optic-Rim Fusion for Glaucoma Detection

<img width="2816" height="1432" alt="main_architecture_morfnet_ablation 2" src="https://github.com/user-attachments/assets/33cb23cb-b8b5-4530-b2a6-32070d8784f6" />

This repository contains the code, experiments, result summaries, and manuscript assets for **MORF-Net**, a deep learning framework for glaucoma detection from color fundus photographs.

MORF-Net is designed around a clinically motivated idea: glaucoma-related evidence is not always captured well by a single full-image classifier. The model therefore combines three complementary retinal views:

- the full fundus image for global retinal context,
- an optic-disc crop for localized disc morphology,
- a peri-disc crop for neuroretinal rim and surrounding structural cues.

These views are processed with a shared ConvNeXt-Tiny encoder and combined using a soft view-attention fusion module. When disc and cup segmentation masks are available, MORF-Net can also append structural biomarkers such as vertical cup-to-disc ratio and disc/cup area ratios before the final prediction head.

## Results Summary

Across three random seeds, MORF-Net showed strong internal and external performance.

On the balanced internal AIROGS+ORIGA test set, the image-only MORF variant achieved:

- **AUC:** 0.873 ± 0.004
- **F1:** 0.801 ± 0.008

The structural MORF variant achieved:

- **AUC:** 0.873 ± 0.006
- **Specificity:** 0.711 ± 0.072

On external REFUGE2 natural-distribution testing, MORF-full achieved the best AUC and F1 among the evaluated models:

- **AUC:** 0.874 ± 0.023
- **F1:** 0.615 ± 0.083

On external ACRIMA testing, the image-only MORF variant achieved the highest AUC:

- **AUC:** 0.821 ± 0.003

## Evaluation

The project compares MORF-Net against several baselines and ablations, including:

- global fundus-only model,
- optic-disc-only model,
- peri-disc-only model,
- MORF without structural biomarkers,
- MORF with structural biomarkers,
- EfficientNetV2-S comparator.

Experiments are performed across AIROGS, ORIGA, ACRIMA, and REFUGE2. The analysis includes ROC curves, calibration plots, decision-curve analysis, bootstrap confidence intervals, clinically motivated operating points, and qualitative gradient-based saliency maps.

## Purpose

The goal of this project is to study whether multi-region optic-disc fusion improves glaucoma detection robustness across datasets with different acquisition settings, class distributions, and image characteristics.
