# 📊 Model Comparison and Selection for Fall Detection

## Project Context

This section presents a comparative analysis of multiple machine learning models developed for the **fall detection task** using the **SisFall dataset**.  
The objective is to select the most suitable model for deployment in a **smart health monitoring system**, where **reliability and safety are critical**.

The following models have been implemented and evaluated using the same dataset, feature extraction method, and train/test split:

- Random Forest (RF)
- Support Vector Machine (SVM – Linear kernel)
- XGBoost (Extreme Gradient Boosting)

---

## Evaluation Criteria

Due to the **safety-critical nature** of fall detection, model performance is evaluated using multiple metrics rather than accuracy alone.

### Key Metrics

- **Precision**  
  Measures how many detected falls are actually true falls.  
  High precision → fewer false alarms.

- **Recall (Sensitivity)**  
  Measures how many actual falls are correctly detected.  
  High recall → fewer missed fall events (very important for healthcare).

- **F1-score**  
  Harmonic mean of precision and recall, providing a balanced evaluation.

- **Confusion Matrix**  
  Provides insight into false positives (false alarms) and false negatives (missed falls).

In this project, **recall for the Fall class** is considered the most critical metric, since missing a fall event may cause serious health risks.

---

## Summary of Model Results

### 1. Random Forest (Baseline)

- Advantages:
  - Robust to noise
  - Easy to interpret
  - Good baseline performance
- Limitations:
  - Moderate recall for fall detection
  - Limited flexibility in decision boundary compared to boosting models

Random Forest serves as a **baseline ensemble model** for comparison.

---

### 2. Support Vector Machine (Linear Kernel)

- Advantages:
  - Simple and fast to train
  - Useful for evaluating linear separability of features
- Limitations:
  - Unable to model complex nonlinear patterns
  - Significant trade-off between precision and recall when adjusting decision thresholds

Threshold analysis shows that:
- Lower thresholds improve recall but introduce many false alarms
- Higher thresholds reduce false alarms but miss many fall events

As a result, **Linear SVM is not suitable as the final model**, but it provides a useful baseline and reference for feature quality.

---

### 3. XGBoost (Extreme Gradient Boosting)

XGBoost demonstrates the strongest performance among all evaluated models.

Key characteristics:
- Ability to model **nonlinear decision boundaries**
- Handles class imbalance effectively using `scale_pos_weight`
- Strong generalization performance

#### Selected Threshold: 0.45

At the selected decision threshold of **0.45**, the model achieves:

- High recall for fall detection (Fall class)
- Balanced precision–recall trade-off
- Stable overall accuracy

**Confusion Matrix (Threshold = 0.45):**


This configuration significantly reduces missed fall events while keeping false alarms at an acceptable level.

---

## Model Selection Decision

After comprehensive evaluation, **XGBoost with a decision threshold of 0.45** is selected as the **final model** for the fall detection system.

### Justification

- Achieves the best balance between:
  - Fall detection recall
  - Precision
  - Overall robustness
- Outperforms Random Forest and SVM in safety-critical metrics
- Suitable for future extension to real-time and embedded systems

---

## Deployment Considerations

The final XGBoost model is saved together with:
- Feature configuration (30 statistical features)
- Windowing parameters
- Decision threshold
- Optional scaler (for compatibility)

To avoid large file uploads, trained model artifacts are stored locally and excluded from the GitHub repository using `.gitignore`.

---

## Conclusion

This comparative study demonstrates that **model selection based solely on accuracy is insufficient** for fall detection systems.  
By considering recall, precision, and threshold behavior, **XGBoost emerges as the most reliable model** for real-world smart health applications.

The selected model will be used in subsequent stages of the project, including:
- System-level integration
- Real-time processing design
- Hardware and edge deployment exploration

---
