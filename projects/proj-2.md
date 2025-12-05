---
layout: post
title: "Pose Estimation Experiments"
---

<style>
  #proj2 .section-title { letter-spacing: 0; line-height: 1.2; margin: 1.4rem 0 0.6rem; }
  #proj2 h2, #proj2 h3 { letter-spacing: 0; line-height: 1.2; margin: 1.4rem 0 0.6rem; }
  #proj2 p { margin: 0.5rem 0 0.9rem; }
  #proj2 ul, #proj2 ol { margin: 0.4rem 0 0.9rem 1.2rem; }
  #proj2 li { margin: 0.25rem 0; }
  #proj2 img { display:block; max-width:100%; height:auto; margin:0.4rem 0 0.8rem; }
</style>

<div id="proj2">

## Overview
This project documents my experiments with pose estimation models to analyze dance movements and explore real-time feedback possibilities for the AI Dance Feedback App.

The goal is to understand how accurately AI can detect body keypoints during fast choreography and to identify limitations that need to be solved in future iterations.

---

## Methods
<img src="{{ '/assets//img/projects/proj-2/skeleton_1.jpg' | relative_url }}" alt="stretch reference" loading="lazy">
### 1. Pose Estimation Models Tested
- **MoveNet (TensorFlow Hub, SinglePose Thunder) — primary**
- **MediaPipe Pose — explored (compatibility issues on Python 3.12)**
- **OpenPose (pretrained) — explored**

<img src="{{ '/assets//img/projects/proj-2/macbook.jpg' | relative_url }}" alt="stretch reference" loading="lazy">
### 2. Test Environment
- Apple MacBook Pro (M2 Pro, 16GB)
- Google Colab for inference tests
- Input data: dance performance videos recorded in low-light indoor environments

---

## Key Results
### ✓ Detection Accuracy
- MediaPipe performed best in fast arm movements.
- MoveNet had the most stable keypoint output with low latency.
- OpenPose struggled with silhouettes wearing dark clothing.

### ✓ Skeleton Visualization
Below are examples of skeleton estimation applied to sample dance frames:


### ✓ Limitations Observed
- Low lighting dramatically reduces joint confidence scores.
- Large clothing and hats obscure elbow and shoulder points.
- Fast turns cause temporary keypoint loss.

---

## Conclusion
Pose estimation is suitable for basic real-time feedback but requires:
- additional smoothing,
- error correction logic,
- better lighting conditions,
- and user calibration.

These findings directly contribute to improving the AI Dance Feedback App prototype.

