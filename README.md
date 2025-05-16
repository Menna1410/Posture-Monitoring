# Posture-Monitoring
Analyze a set of images of a fitness coach performing different exercises (standing, squatting empty-handed, and holding weights). Estimate the load distribution across key body parts (arms, legs, hips, and chest) based on the given data and exercise posture.

# 🏋️‍♂️ Human Pose Estimation & Biomechanical Analysis – SEE Assessment

This project implements a full **human pose estimation and biomechanical load analysis pipeline** to monitor and evaluate physical posture and joint stress using computer vision.

---

## 📁 Dataset

- **Dataset Used**: [Human Pose Estimation Dataset](https://www.kaggle.com/datasets/trainingdatapro/pose-estimation)
- Format: Collection of exercise images (standing, squatting, lifting weights, etc.)
- Input: Static 2D images of a fitness coach performing exercises
- Output: Keypoints, joint angles, biomechanical load, and annotated visual reports

---

## 🚀 Pipeline Overview

```mermaid
graph TD
A[Upload Images / Dataset] --> B[Pose Estimation (YOLOv8)]
B --> C[2D Keypoint Extraction]
C --> D[Joint Angle Calculation]
D --> E[Biomechanical Load Estimation]
E --> F[Visualization & Reporting]
