# Early Detection of Alzheimer's Disease  
**AI-Based Retinal OCT Analysis for Non-Invasive Screening**

---

## Overview  
This project presents an **AI-driven, non-invasive solution** for the **early detection of Alzheimer’s Disease (AD)** using **Optical Coherence Tomography (OCT)** retinal images. By leveraging deep learning, the system segments key retinal layers—**Retinal Nerve Fiber Layer (RNFL)** and **Ganglion Cell Layer (GCL)**—and uses their thickness as biomarkers to predict AD risk.

The approach combines:  
- **U-Net** for precise retinal layer segmentation  
- **TransNet OCT** (a Transformer-based model) for Alzheimer’s risk prediction  

This pipeline offers a **scalable, cost-effective alternative** to traditional diagnostics like MRI and PET scans—especially valuable in low-resource settings.

---

## Key Features  

**Automated Retinal Layer Segmentation**  
- Uses U-Net to isolate RNFL and GCL from OCT scans with pixel-level accuracy  

**Clinically Interpretable Feature Extraction**  
- Applies the **ETDRS grid** to compute sector-wise thickness, asymmetry indices, and macular volume  

**AI-Powered Risk Prediction**  
- TransNet OCT analyzes structural biomarkers to output an **Alzheimer’s risk score (0–1)**  

**Non-Invasive & Accessible**  
- Relies on widely available retinal OCT imaging—no radiation, injections, or complex infrastructure  

**Modular & Extensible Architecture**  
- Designed for easy integration with real-world clinical workflows or multimodal data (e.g., cognitive tests, blood biomarkers)

---

## Methodology  

1. **Input**: Grayscale OCT B-scan (512×496 pixels)  
2. **Preprocessing**: Noise reduction, normalization, resizing  
3. **Segmentation**: U-Net model generates pixel-wise layer masks  
4. **Feature Extraction**:  
   - RNFL & GCL thickness mapped across 9 ETDRS sectors  
   - Statistical features (mean, std, asymmetry) computed  
5. **Classification**: TransNet OCT (Transformer) predicts AD risk from 18 input features  
6. **Output**: CSV report with thickness metrics + Alzheimer’s risk score  

> **Note**: Due to limited availability of labeled clinical AD-OCT datasets, the project uses **synthetic data** generated from peer-reviewed medical literature.

---

## Technology Stack  

- **Language**: Python  
- **Deep Learning Framework**: TensorFlow / Keras  
- **Libraries**:  
  - OpenCV (image preprocessing)  
  - NumPy, Pandas (data handling)  
  - scikit-image (segmentation utilities)  
  - Matplotlib (visualization)  
- **Hardware**: Trained on **Google Colab** (NVIDIA Tesla T4 GPU, 12GB RAM)  
- **Data Source**: University of Waterloo OCT Dataset (2018)

---

## Performance Metrics  

Evaluated on synthetic test data using:  
- Accuracy  
- Precision & Recall  
- F1-Score  
- ROC-AUC  

Results demonstrate accurate segmentation and promising classification performance, validating the potential of AI-based retinal analysis as a rapid and affordable screening tool for early Alzheimer’s detection.

--- 
**Institution**: Symbiosis Institute of Technology, Pune  
**Academic Year**: 2025–2026  

*This project aligns with UN Sustainable Development Goals (SDGs) 3 (Good Health), 9 (Innovation), and 10 (Reduced Inequalities) by promoting accessible, non-invasive, and intelligent healthcare solutions.*
