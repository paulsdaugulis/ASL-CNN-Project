# ASL Dataset Preprocessing Log
**Generated on:** 2025-11-24 11:04:07

## 1. Data Source & EDA
* **Source:** kapillondhe/american-sign-language (KaggleHub)
* **Total Raw Images:** 165670
* **Class Distribution:** Generally balanced. Max: 5996, Min: 4542 (Class 'U' is lowest).

## 2. Preprocessing Pipeline
* **Target Image Size:** 64x64
* **Step 1: ToTensor:** Converts pixel integers (0-255) to floats (0-1).
* **Step 2: Normalization:** Mean=[0.5, 0.5, 0.5], Std=[0.5, 0.5, 0.5] (Resulting range: -1 to 1).
* **Augmentation (Train Only):** RandomRotation(+/- 10deg). NO Horizontal Flip (Letter loses its meaning).

## 3. Data Split Configuration
The dataset provided a separate Test folder. The main 'Train' folder was split 80/20 for training and validation.

| Set | Count |
| :--- | :--- |
| **Training** | 132536 |
| **Validation** | 33134 |
| **Test** | 112 |

## 4. DataLoader Setup
* **Batch Size:** 32
* **Shuffle:** ON for Training, OFF for Val/Test.

## 5. Evaluation Strategy
* **Primary Metric:** Accuracy (classes are balanced).
* **Training Diagnostics:** Loss Curves (Train vs. Validation Loss) to detect "progress".
* **Error Analysis:** Confusion Matrix (to spot specific letter confusions).
* **Detail:** Precision & Recall per class.
