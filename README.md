# Confidence-Gated Anthropometry

**TL;DR**  
A research-grade system for estimating human body measurements from a single RGB image using pose detection, monocular depth estimation, segmentation, and confidence-gated statistical priors.

---

## Overview

Confidence-Gated Anthropometry is an end-to-end system for estimating human body measurements from a **single RGB image** using modern computer vision and statistically grounded anthropometric priors.

The system combines pose detection, monocular depth estimation, semantic segmentation, and confidence-gated inference to produce **interpretable, uncertainty-aware body measurements** suitable for research and applied use.

---

## 🔍 What It Does

Given a single image of a person, the system estimates:

- Upper arm length  
- Forearm length  
- Thigh length  
- Calf length  
- Shoulder width  
- Hip width  

Each measurement includes:

- An uncertainty estimate  
- Confidence gating  
- Plausibility checks against population priors  

---

## 🧮 Why This Matters

This project emphasizes **transparency, uncertainty awareness, and failure visibility** over black-box prediction accuracy.

Rather than forcing a numeric output, the system explicitly detects when confidence is insufficient and avoids emitting misleading measurements.

---

## 🧠 Core Techniques

- **Pose Detection**
  - MediaPipe Pose

- **Monocular Depth Estimation**
  - Depth Anything v2 (small)
  - ONNX Runtime fallback

- **Person Segmentation**

- **Confidence-Gated Statistical Priors**
  - ANSUR II public anthropometric dataset

- **Scale Sanity & Pose Quality Checks**

If confidence is insufficient, the system gracefully falls back instead of emitting unreliable results.

---

## 🏗 Architecture

### Backend
- FastAPI (Python)
- Modular ML pipeline with **reduced** and **full ML** modes
- Health, readiness, and diagnostics endpoints

### Reverse Proxy
- Express-based proxy for production routing

### Client
- Cross-platform web/mobile-compatible frontend
- Debug artifact visualization:
  - Person mask
  - Depth map
  - Pose keypoints

---

## 🧪 Debug & Transparency Features

- Person mask visualization  
- Depth map visualization  
- Keypoint overlay  
- Scale factor diagnostics  
- Pose confidence scoring  
- Full inference metadata  

Designed to make **failures visible, not hidden**.

---

## 🚧 Project Status

Active development.

This repository represents a **functional research prototype** and a **production-capable architecture**, not a consumer-facing body measurement product.

---

## ⚠️ Disclaimer

This software is intended for:

- Research  
- Prototyping  
- Statistical and computer vision experimentation  

It is **not a medical device** and must not be used for clinical or biometric identification purposes.

---

## 🗺 System Overview

> Diagram coming soon — backend pipeline, confidence gating, and verification flow.

---

## 🔗 Related

- **Live prototype:**  
  https://replit.com/@drakonoslav/Visionary-Mobile-Dev
