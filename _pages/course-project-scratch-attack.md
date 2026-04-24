---
permalink: /scratch-attack/
title: "Course Project: Optical Adversarial Attacks on Vision Systems"
excerpt: "A course project report on scratch-induced optical artifacts and their impact on depth-related vision tasks."
author_profile: true
---

# Course Project Report: Optical Adversarial Attacks on Vision Systems

**Authors:** Qinlin He, Zeming Zhuang  
**Term:** Spring 2026  
**Type:** Course Project

## Abstract

This course project studies a camera-side physical attack surface: fine scratches near a lens can scatter light and create structured flare artifacts under strong illumination. We analyze the optical mechanism, build both physical and digital evaluation pipelines, and quantify impacts on depth estimation and 3D detection models. Results show that this attack surface can cause clear depth distortions and measurable geometry errors without changing scene objects.

## Problem Setup

Real camera lenses may contain small scratches from long-term use. Under bright headlights or point light sources, these scratches can produce linear flares that partially occlude content or add misleading visual cues.

![Real-world lens scratches 1](/assets/projects/scratch-attack/real-world-scratches-1.png)
*Figure 1. Example of real-world lens scratch pattern.*

![Real-world lens scratches 2](/assets/projects/scratch-attack/real-world-scratches-2.png)
*Figure 2. Another lens scratch pattern observed in practice.*

![Physical adversarial attack categories](/assets/projects/scratch-attack/physical-adversarial-attacks.png)
*Figure 3. Representative physical attack directions for vision systems.*

## Optical Mechanism

A linear scratch perturbs the incoming light path and introduces a scattered component. When the scene contains intense light sources, the scattered component forms structured streak-like artifacts in the image plane. This project focuses on geometric optics intuition for attack construction.

![Lens scratches under microscope](/assets/projects/scratch-attack/lens-scratches-microscope.jpg)
*Figure 4. Microscopic view of surface scratches.*

![Focused path vs scratch-scattered path](/assets/projects/scratch-attack/light-path-focused-vs-scratch-scattered.png)
*Figure 5. Difference between focused and scratch-scattered light paths.*

![Attack surface overview](/assets/projects/scratch-attack/attack-surface-overview.png)
*Figure 6. Comparison between object-side and camera-side attack surfaces.*

## Experiment Setup

We evaluate the attack in two pipelines:

1. **Physical setup:** scratch patterns are engraved on an acrylic plate and placed in front of the lens under strong lights.
2. **Digital setup:** night-time driving scenes are edited with simulated scratch-induced flare artifacts for controlled evaluation.

Target tasks include depth estimation and monocular 3D detection.

![Physical attack setup](/assets/projects/scratch-attack/physical-attack-setup.png)
*Figure 7. Physical evaluation setup used in this course project.*

## Results

### Depth Estimation

Depth maps in attacked images show hallucinated near obstacles and stronger local distortion around light sources.

![MonoDepth2 benign vs attacked](/assets/projects/scratch-attack/monodepth2-benign-vs-attacked.png)
*Figure 8. Benign and attacked depth prediction comparison.*

![Depth estimation impact table](/assets/projects/scratch-attack/table-impact-depth-estimation.png)
*Figure 9. Summary of depth estimation impact under scratch-induced flare.*

### 3D Detection Geometry Error

Per-image and multi-frame optimizations both increase depth-related geometry error:

- **Pushing direction:** PGD `2.9% -> 14.9%`, FCOS3D `3.5% -> 18.4%`
- **Pulling direction:** PGD `2.8% -> 8.5%`, FCOS3D `3.5% -> 7.6%`
- **Multi-frame setting:** PGD `2.7% -> 5.8%`, FCOS3D `3.6% -> 7.2%`

![Impact on 3D detection (pushing)](/assets/projects/scratch-attack/impact-3d-detection-pushing.png)
*Figure 10. Error change in the pushing setting.*

![Impact on 3D detection (pulling)](/assets/projects/scratch-attack/impact-3d-detection-pulling.png)
*Figure 11. Error change in the pulling setting.*

![Impact on 3D detection (multi-frame)](/assets/projects/scratch-attack/impact-3d-detection-multi-frame.png)
*Figure 12. Error change in the multi-frame setting.*

![3D detection examples](/assets/projects/scratch-attack/examples-3d-detection.png)
*Figure 13. Qualitative examples in BEV and image views.*

![Optimizer ablation study](/assets/projects/scratch-attack/table-optimizer-ablation-study.png)
*Figure 14. Optimizer ablation results.*

## Limitations

- Current experiments emphasize night scenes with strong point light sources.
- Scratch geometry is parameterized in a simplified way and does not cover all lens defects.
- Transferability across camera hardware and sensor pipelines needs further study.

## Takeaways

- Camera-side optical artifacts are a practical and meaningful threat surface.
- Small physical lens defects can induce structured perturbations that alter depth cues.
- Depth-aware perception stacks should include optical artifact robustness checks during evaluation.
