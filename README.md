# Posture-Monitoring
Analyze a set of images of a fitness coach performing different exercises (standing, squatting empty-handed, and holding weights). Estimate the load distribution across key body parts (arms, legs, hips, and chest) based on the given data and exercise posture.

# 🏋️‍♂️ Human Pose Estimation & Biomechanical Load Analysis – SEE Assessment

This project implements a full computer vision pipeline for **human pose estimation**, **joint angle computation**, and **biomechanical load distribution analysis** using YOLOv8. Developed as part of the SEE Startup technical assessment for the **Computer Vision Engineer** position.

---

## 📁 Dataset

- **Name**: Human Pose Estimation Dataset  
- **Source**: [Kaggle – Human Pose Estimation Dataset](https://www.kaggle.com/datasets/trainingdatapro/pose-estimation)
- **Type**: Static exercise images of a fitness coach
- **Format**: `.jpg` images

---

## 🚀 Pipeline Overview

1. **Upload Images or Dataset**
2. **Pose Estimation** using YOLOv8 (detect joints)
3. **2D Keypoint Extraction** (17 COCO keypoints)
4. **Joint Angle Calculation** (elbows, knees, hips)
5. **Biomechanical Load Estimation** (arms, legs, hips, chest)
6. **Visualization & Reporting** (color-coded overlays + summary)

---

## 📓 Notebooks Used

### 1️⃣ `Pose_Estimation_SEE_Assessment_Task.ipynb`

**Function**:  
- Run pose detection on uploaded images (manual or ZIP dataset)
- Extract 2D keypoints (XY coordinates for 17 joints)
- Save outputs:
  - `keypoints.csv` (for next stage)
  - Annotated images to:
    - `/content/outputs/` (temporary)
    - `/drive/MyDrive/SEE_Assessment/outputs/` (persistent)

---

### 2️⃣ `Biomechanical_Analysis_SEE_Assessment_Task.ipynb`

**Function**:  
- Load `keypoints.csv`
- Calculate:
  - Elbow, knee, and hip angles
- Estimate biomechanical loads on:
  - Arms (holding 5.5kg each)
  - Legs (posture-based)
  - Hips (body weight support)
  - Chest (supporting torso + weights)
- Save outputs:
  - `joint_angles.csv`
  - `load_estimations.csv`

---

### 3️⃣ `Visualization_and_Summary_Report.ipynb`

**Function**:  
- Load angle and load data from CSV
- Load annotated images from Google Drive
- Overlay:
  - Color-coded circles (stress levels)
  - Angle + load values on joints
- Generate:
  - Per-image overlays
  - Summary comparison by posture (stand, squat, lunge, etc.)
  - Bar chart of average joint loads

---

## 📊 Output Files

| File Name             | Description                                  |
|-----------------------|----------------------------------------------|
| `keypoints.csv`       | 2D (x, y) keypoints for each joint            |
| `joint_angles.csv`    | Elbow, knee, and hip angles per image         |
| `load_estimations.csv`| Biomechanical load (kg) for each body part    |
| `annotated_*.jpg`     | Color-coded joint overlay images              |

---

## 🧠 Assumptions

- Subject weight: **60 kg**, height: **170 cm**, age: **58 years**
- Dumbbells: **5.5 kg in each hand**
- Keypoints are based on YOLOv8 (COCO 17 keypoints)
- Only the **first person** detected is analyzed
- Static poses (no time-series)

---

## 📂 Directory Structure

📁 SEE_Assessment/
├── Pose_Estimation_SEE_Assessment_Task.ipynb
├── Biomechanical_Analysis_SEE_Assessment_Task.ipynb
├── Visualization_and_Summary_Report.ipynb
├── keypoints.csv
├── joint_angles.csv
├── load_estimations.csv
├── /outputs/ # Annotated images (in Google Drive)


---

## 📈 Load Visualization Example

- Green: Load < 6kg (low stress)
- Yellow: 6–10kg (moderate stress)
- Red: > 10kg (high stress)
- Overlay: `Angle° / Loadkg` per joint

Bar charts compare:
- Leg/arm/hip/chest load across:
  - Standing
  - Squatting
  - With weights
  - Lunges
  - Bent-forward

---

## ✅ How to Run This Project

1. **Pose Estimation Notebook**
   - Upload images or ZIP dataset
   - Annotated results saved to Google Drive

2. **Biomechanical Analysis Notebook**
   - Computes angles and loads
   - Saves results to CSV

3. **Visualization Notebook**
   - Loads annotated images and CSVs
   - Overlays load data
   - Generates summaries and graphs

---

## 👨‍💻 Author

- **Name**: Menna Mohamed Roushdy  
- **Position Applied For**: ML/Computer Vision Engineer  
- **Company**: SEE Startup  
- **Tools Used**: Python, OpenCV, YOLOv8, Ultralytics, Pandas, Google Colab

---

## 💬 Questions?

Open an issue or contact me via GitHub for collaboration or clarification.

