# 📸 Image Retrieval System using LBP, LTP, and KNN

## 🔍 Overview

This project is an **Image Retrieval System** that leverages texture-based feature extraction and a simple, effective classification algorithm to retrieve visually similar images from a dataset. It uses:

- **Local Binary Pattern (LBP)**
- **Local Ternary Pattern (LTP)**
- **K-Nearest Neighbors (KNN)**

for robust and efficient retrieval.

---

## 🧠 How It Works

### 🔹 Feature Extraction

1. **Local Binary Pattern (LBP)**:
   - LBP is a texture descriptor that encodes the local spatial structure of an image.
   - It compares each pixel with its 8 neighbors:
     - If a neighbor's value ≥ center pixel → assign `1`; else assign `0`.
   - These binary values are combined into an LBP code.
   - A histogram of these codes over the image serves as a texture feature descriptor.
   - ✅ *Advantages*: Fast, simple, rotation-invariant, and effective for texture-based classification.

2. **Local Ternary Pattern (LTP)**:
   - LTP extends LBP by introducing a threshold to form three-value codes:
     - +1 if neighbor ≥ center + threshold
     - 0 if center - threshold < neighbor < center + threshold
     - -1 if neighbor ≤ center - threshold
   - This makes the descriptor more robust to noise and illumination variations.

### 🔹 Image Representation

- Each image is represented by concatenating the LBP and LTP histograms to form a feature vector.

### 🔹 Classification using KNN

- The **K-Nearest Neighbors (KNN)** algorithm is used to find the **top 5 most similar images** to a given **query image**.
- Distance metric: typically Euclidean or Chi-square distance between feature vectors.
- The top 5 closest images (in feature space) are returned as the best matches.

---

**📌 Applications**
Facial Recognition

Texture Classification

Content-Based Image Retrieval (CBIR)

Medical Image Analysis
