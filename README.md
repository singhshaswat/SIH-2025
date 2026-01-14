# 🐄 Cow & Buffalo Breed Classification System (SIH 2025)

A **two-stage deep learning–based computer vision system** developed for **Smart India Hackathon (SIH) 2025** to automatically identify **cow and buffalo breeds** from images using **YOLOv8, TensorFlow Lite, and Gradio**.

The system is designed for **high accuracy, modularity, and fast inference**, making it suitable for **real-world and edge deployment**.

---

## 🔁 System Flow (End-to-End Pipeline)

The system follows a **hierarchical inference flow** to improve classification accuracy:

1. **Input Image**
   - User uploads an image containing cattle

2. **Animal Detection**
   - YOLOv8 detects the animal region and removes background noise

3. **Stage 1: Species Classification**
   - A binary TFLite model classifies the detected animal as:
     - Cow
     - Buffalo

4. **Stage 2: Breed Classification**
   - If Cow → Cow breed classifier is triggered
   - If Buffalo → Buffalo breed classifier is triggered

5. **Final Output**
   - Predicted species and breed are displayed to the user

---

## 🏗️ Architecture Diagram

```

Input Image
│
▼
┌──────────────────────┐
│ YOLOv8 Detector      │
│ Animal Detection    │
└──────────────────────┘
│
▼
┌──────────────────────┐
│ Stage 1 Classifier   │
│ Cow vs Buffalo       │
│ (TFLite)             │
└──────────────────────┘
│
├───────────┐
▼           ▼
┌──────────────┐ ┌─────────────────┐
│ Cow Breed     │ │ Buffalo Breed   │
│ Classifier    │ │ Classifier      │
│ (TFLite)      │ │ (TFLite)        │
└──────────────┘ └─────────────────┘
│
▼
Final Breed Prediction

```

---

## 📊 Model Performance Metrics

| Model | Task | Accuracy |
|------|------|---------|
| YOLOv8n | Animal Detection | High (real-time) |
| classifier.tflite | Cow vs Buffalo | ~97% |
| indian_breed_model_cow.tflite | Cow Breed Classification | ~95% |
| indian_breed_model_bafflow.tflite | Buffalo Breed Classification | ~87% |

📌 *Metrics are based on validation/testing performed during SIH development.  
Performance may vary under real-world conditions.*

---

## 📁 GitHub Repository Overview

This repository contains **only inference-ready components** required to run the system.

```

gradio/
├── SIH_ROUND_1_Gradio.ipynb        # Gradio-based UI & inference logic
├── yolov8n.pt                     # YOLOv8 model for animal detection
├── classifier.tflite              # Stage 1: Cow vs Buffalo model
├── indian_breed_model_cow.tflite  # Stage 2: Cow breed classifier
├── indian_breed_model_bafflow.tflite # Stage 2: Buffalo breed classifier

````

### 📌 Why training code is not included?
- Training datasets are proprietary and SIH-restricted
- Models are shared for **demo, evaluation, and inference purposes**
- This keeps the repository lightweight and deployment-focused

---

## 🧪 How to Use This Repository (Inference Only)

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/harshitgupta04022004/SIH.git
cd SIH/gradio
````

### 2️⃣ Create Virtual Environment (Recommended)

```bash
python -m venv venv
source venv/bin/activate   # Linux / Mac
venv\Scripts\activate      # Windows
```

### 3️⃣ Install Required Libraries

```bash
pip install ultralytics tensorflow tflite-runtime gradio opencv-python numpy
```

### 4️⃣ Run the Gradio Application

Open the notebook and run all cells:

```bash
SIH_ROUND_1_Gradio.ipynb
```

### 5️⃣ Test the System

* Upload an image of a cow or buffalo
* The system will automatically:

  * Detect the animal
  * Classify species
  * Predict the breed

---

## 🎯 Key Highlights

* ✅ Two-stage deep learning architecture
* ✅ YOLOv8 for precise animal detection
* ✅ TensorFlow Lite models for fast inference
* ✅ Gradio-based interactive interface
* ✅ Edge-deployment friendly design

---

## 🏆 Smart India Hackathon 2025

This project was developed as part of **Smart India Hackathon (SIH) 2025**, focusing on **AI-driven solutions for agriculture and livestock management**.

---

## 👨‍💻 Author

**Shaswat Singh**
Deep Learning | Computer Vision | Machine Learning

---

## 📌 Disclaimer

* Training code and datasets are **not included**
* Models are shared for **academic, demonstration, and evaluation use only**

---

⭐ If you find this project useful, feel free to **star the repository**

```

