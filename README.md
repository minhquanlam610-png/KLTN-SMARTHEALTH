\# KLTN-SMARTHEALTH



Graduation Thesis Project – Smart Health Monitoring System  

\*\*Fall Detection \& Physiological Signal Analysis using Machine Learning\*\*



\---



\## 📌 Project Overview



This repository contains the experimental implementation and results of my \*\*graduation thesis\*\* on smart healthcare monitoring.  

The current phase focuses on \*\*fall detection using wearable IMU signals\*\* and machine learning models.



Key objectives:

\- Build a complete ML pipeline for fall detection

\- Evaluate baseline machine learning models

\- Analyze decision threshold effects

\- Provide reproducible experiments for academic reporting



\---



\## 📊 Dataset



\### SisFall Dataset

\- Type: Wearable IMU data (accelerometer \& gyroscope)

\- Signals: 6 channels (ax, ay, az, gx, gy, gz)

\- Activities:

&#x20; - \*\*ADL\*\* (Activities of Daily Living)

&#x20; - \*\*FALL\*\* events

\- Windowing:

&#x20; - Fixed-length sliding windows

&#x20; - Used for supervised classification



📚 Reference:  

SisFall: A Dataset for Fall Detection (UPM, Spain)



\---



\## ⚙️ Methodology



\### 1. Data Preprocessing

\- File parsing and validation

\- Signal cleaning

\- Sliding window segmentation

\- Feature extraction (statistical \& temporal features)



\### 2. Model

\- \*\*Random Forest (Baseline Model)\*\*

\- Binary classification:

&#x20; - `0`: ADL

&#x20; - `1`: FALL



\### 3. Evaluation Metrics

\- Accuracy

\- Precision / Recall / F1-score

\- Confusion Matrix

\- Threshold analysis



\---



\## 🧪 Experimental Results



All experimental results are stored in:





Including:

\- Classification report (baseline)

\- Confusion matrix

\- Threshold comparison results (0.35 → 0.50)

\- Dataset statistics

\- Windowing statistics



📈 These results are directly used for the \*\*Experimental Evaluation\*\* chapter of the thesis.



\---



\## 📁 Repository Structure





\---



\## 🚫 Trained Models



Due to GitHub file size limitations, trained model files (`.joblib`) are \*\*not included\*\* in this repository.



All results can be reproduced by running the provided Jupyter notebooks.



\---



\## ▶️ How to Run



1\. Clone this repository

2\. Open the notebook:

3\. Run all cells to reproduce preprocessing, training, and evaluation



\---



\## 🔜 Future Work



\- Deep learning models (1D-CNN / LSTM) for fall detection

\- Physiological signal analysis (PPG, HRV)

\- IoT-based real-time system integration (ESP32 + Cloud)



\---



\## 👤 Author



\*\*Lam Minh Quan\*\*  

Final-year student – Electronics \& Telecommunications Engineering  

Graduation Thesis Project



\---



