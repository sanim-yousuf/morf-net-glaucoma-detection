# MORF-Net: Multi-Region Optic-Rim Fusion for Glaucoma Detection

<img width="2816" height="1432" alt="main_architecture_morfnet_ablation 2" src="https://github.com/user-attachments/assets/33cb23cb-b8b5-4530-b2a6-32070d8784f6" />

This repository contains the code, experiments, and manuscript assets for MORF-Net, a deep learning framework for glaucoma detection from fundus photographs. MORF-Net combines global fundus context, optic-disc crops, and peri-disc regions using a shared ConvNeXt-Tiny encoder with view-attention fusion. When segmentation masks are available, the model can also incorporate structural biomarkers such as vertical cup-to-disc ratio and disc/cup area ratios.

Across three random seeds, MORF-Net achieved strong performance on both internal and external evaluations. On the balanced internal AIROGS+ORIGA test set, the image-only MORF variant reached an AUC of 0.873 ± 0.004 and F1 of 0.801 ± 0.008, while the structural MORF variant reached an AUC of 0.873 ± 0.006 and specificity of 0.711 ± 0.072. On external REFUGE2 natural-distribution testing, MORF-full achieved the highest AUC and F1 among evaluated models, with AUC 0.874 ± 0.023 and F1 0.615 ± 0.083. On ACRIMA, the image-only MORF variant achieved the highest AUC, 0.821 ± 0.003.

The project evaluates single-view baselines, multi-region fusion variants, and an EfficientNetV2-S comparator across AIROGS, ORIGA, ACRIMA, and REFUGE2. Reported analyses include ROC curves, calibration, decision-curve analysis, bootstrap confidence intervals, operating-point evaluation, and qualitative saliency visualizations.
