# 🌾 AgroSmart KZ - AI-Powered Agricultural Analytics

**Strategic Monitoring of Agricultural Subsidies in Kazakhstan**  
---

## 👥 Team: Van Gogh
| Name | Role | Socials |
| :--- | :--- | :--- |
| **Albina Gibadullina** | Project Manager & Team Lead | [● GitHub](https://github.com/albina0dali) |
| **Karlygash Aibolatkyzy** | ML Engineer & Backend Developer | [● GitHub](https://github.com/a1ksh) |
| **Asem Abdikarim** | Data Scientist | [● GitHub](https://github.com/assem-a7) |
| **Aruzhan Serikpaeva** | Frontend Developer | [● GitHub](https://github.com/Mevinss) |
---
## 📂 Documentation
📄 [Download Presentation PDF](https://github.com/a1ksh/AgroSmart-KZ/releases/download/v1.0.0/Van.Gogh.pdf)

## 📊 Platform Overview
AgroSmart KZ is a comprehensive analytical tool that leverages Machine Learning to ensure fair subsidy distribution, detect anomalies, and provide soil-based crop recommendations.

### Dashboard Preview
![Dashboard Preview](Overview%20Interface.png)

---
## 📥 Large Files (Datasets & Pre-trained Models)
Due to GitHub's file size limits, large binary files such as trained models (`.pth`, `.pkl`) and the full dataset are hosted on Google Drive.

[![Google Drive](https://img.shields.io/badge/Google%20Drive-Download%20Large%20Files-orange?logo=googledrive&logoColor=white)](https://drive.google.com/drive/folders/11yi8rJtEdJ74aQjcg6PpNFtLwBPbu8IR?usp=sharing)

**Instructions:**
1. Download the contents of the folder.
2. Place the model files into the `/models` directory.
3. Place the dataset files into the `/data` directory.

## 📦 Project Structure
```
AgroSmart_KZ/
├── app.py                ← Main Streamlit application
├── config.py             ← Constants, KZ regions, crop types
├── scoring_engine.py     ← Isolation Forest + XGBoost scoring
├── soil_analyzer.py      ← Soil analysis via photos
├── forecasting.py        ← Forecasting (Exponential Smoothing)
├── train_models.py       ← Training script (RUN ONCE)
├── requirements.txt      ← Dependencies
├── .env.example          ← Template for GEE credentials
├── data/                 ← Place your subsidy XLSX file here
├── models/               ← Saved ML models (auto-generated)
└── results/              ← Analysis results (auto-generated)
```

---

## 🚀 Quick Start Guide

### Step 1 — Setup Virtual Environment
**Windows:**
```bash
python -m venv .venv
.venv\Scripts\activate
```
**macOS / Linux:**
```bash
source .venv/bin/activate
```

### Step 2 — Install Dependencies
```bash
pip install --upgrade pip
pip install -r requirements.txt
```

### Step 3 — Configure Environment Variables
1. Copy `.env.example` to `.env`.
2. Add your **Google Earth Engine (GEE)** credentials:
   - `GEE_SERVICE_ACCOUNT`
   - `GEE_PRIVATE_KEY_PATH` (Path to your JSON key)
   - `GEE_PROJECT_ID`

### Step 4 — Prepare Data & Train (RUN ONCE)
Place your `subsidies_2025.xlsx` into the `data/` folder, then run:
```bash
python train_models.py
```
*Time: 1–3 minutes. This trains the ML models and caches results.*

### Step 5 — Launch Application
```bash
streamlit run app.py
```
Access the dashboard at: **http://localhost:8501**

---

## 🧠 Machine Learning Models

| Model | Purpose |
|-------|---------|
| **Isolation Forest** | Detects anomalous/fraudulent applications (~3% contamination). |
| **XGBoost** | Predicts the probability of application fulfillment. |
| **Merit Score** | Multi-factor ranking (Success history + Scale + Priority). |
| **Holt-Winters** | Time-series forecasting for subsidy volumes (1–6 months). |
| **Soil Classifier** | Computer Vision (PIL + NumPy) to identify soil types from photos. |

---

## 🛠 Features
*   **📊 Dashboard:** KPI metrics, application statuses, monthly dynamics.
*   **🗺️ Interactive Map:** Bubble-map of 17 regions and 3 major cities of Kazakhstan.
*   **🎯 Smart Scoring:** Fraud detection and merit-based shortlisting.
*   **📸 Soil Analysis:** Upload a soil photo → Get type & crop recommendations.

---

## ⚖️ License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

> **"ЗАҢ МЕН ТӘРТІП"**

**Made with 💚 for Kazakhstan's Digital Agriculture**
