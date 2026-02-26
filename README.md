# MedVAR: Next-scale Autoregressive Medical Image Generation 🩻📈

<div align="center">

[![arXiv](https://img.shields.io/badge/arXiv%20paper-2602.14512-b31b1b.svg)](https://arxiv.org/abs/2602.14512)&nbsp;
[![Paper PDF](https://img.shields.io/badge/Paper-PDF-red)](https://arxiv.org/pdf/2602.14512.pdf)&nbsp;

</div>

<p align="center" style="font-size: larger;">
  <a href="https://arxiv.org/abs/2602.14512">
    MedVAR: Towards Scalable and Efficient Medical Image Generation via Next-scale Autoregressive Prediction
  </a>
</p>

<div>
  <p align="center" style="font-size: larger;">
    <strong>Next-scale autoregressive foundation model for multi-organ CT/MRI generation</strong>
  </p>
</div>

<p align="center">
  <img src="./assets/cover.png" width="95%">
</p>

<br>

## News
* **2026-02:** MedVAR arXiv preprint released.

---

## What's New?

### 🔥 MedVAR brings next-scale prediction to medical image synthesis 🧠🩺
MedVAR adapts **Visual Autoregressive Modeling** to medical imaging and reformulates generation as **coarse-to-fine next-scale prediction** rather than raster-scan next-token prediction. This makes sampling **fast, scalable, and stable** for 256×256 medical slices while preserving anatomical structure.

<p align="center">
  <img src="./assets/framework.jpg" width="93%">
</p>

### ⚡ Fast sampling without step-heavy diffusion
Diffusion models improve fidelity by increasing denoising steps but pay a linear runtime cost. MedVAR generates an image in **10 scales** (instead of ~100 steps) and achieves strong quality–efficiency trade-offs.

### 📈 Scalable transformers for medical generation
We observe consistent improvements as model size scales from **310M → 2B**, improving anatomical sharpness and fine texture fidelity while keeping sub-second latency.

### 🧩 Multi-organ & multi-modality coverage
MedVAR is trained on a harmonized corpus spanning multiple anatomies and both CT/MRI. Below shows representative multi-domain generations.

<p align="center">
  <!-- Multi-domain samples: use Fig.6-style grid -->
  <img src="./assets/diversity.png" width="85%">
</p>

---

## Dataset
MedVAR is trained on a **harmonized multi-organ CT/MRI dataset** (~438,905 curated 2D slices) covering abdomen/brain/chest/heart/prostate/spine with modality-specific normalization and geometric standardization. Details and dataset list are provided in the paper.

<p align="center">
  <img src="./assets/datasets.png" width="85%">
</p>

---

## Evaluation
We report fidelity, diversity, and scalability using:

- **FID**, **RadFID**, **KID**, **CMMD**
- **Efficiency metric** balancing quality and runtime:
  - Efficiency = Q · (log(1 + P))^γ
  - Where:
    - Q = FID  
    - P = inference time  
    - γ = balancing coefficient  
  - Lower values indicate better quality-efficiency trade-off.

## Citation
If our work assists your research, feel free to give us a star ⭐ or cite us using:

```bibtex
@misc{he2026medvarscalableefficientmedical,
      title={MedVAR: Towards Scalable and Efficient Medical Image Generation via Next-scale Autoregressive Prediction}, 
      author={Zhicheng He and Yunpeng Zhao and Junde Wu and Ziwei Niu and Zijun Li and Bohan Li and Lanfen Lin and Yueming Jin},
      year={2026},
      eprint={2602.14512},
      archivePrefix={arXiv},
      primaryClass={cs.CV},
      url={https://arxiv.org/abs/2602.14512}, 
}
