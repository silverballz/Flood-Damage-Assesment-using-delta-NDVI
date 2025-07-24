# 🌾 Flood Damage Assessment using Super-Resolved Satellite Imagery

This repository contains our end-to-end pipeline for assessing flood-induced agricultural damage using low-resolution Sentinel-2 imagery enhanced via Super-Resolution (EDSR) and classified using a UNet model. The approach improves classification fidelity by bridging the resolution gap between Sentinel-2 (10m) and PlanetScope (3m).

---

## 📌 Project Overview

- **Objective:** Assess pixel-wise flood damage (No Damage / Partial / Full) over agricultural land using enhanced satellite imagery.
- **Study Area:** Muzaffarpur, Bihar, India.
- **Time Period:** October 2022 flood event.
- **Data Sources:**
  - **Sentinel-2** (Pre/Post-flood RGB + NDVI)
  - **PlanetScope** (High-res reference)
  - **LULC Map** (LCFM v10)
  - **Cloud Masking** via Sentinel-2 QA bands

---

## 🔬 Methodology

1. **Cloud Removal** on Sentinel-2 images
2. **NDVI Computation** (pre and post-flood)
3. **Super-Resolution** with EDSR model (256×256 patches)
4. **ΔNDVI Generation** and labeling into damage categories
5. **Flood Damage Classification** using UNet
6. **Evaluation** via F1 scores, visual overlays, and side-by-side comparisons

---

## 📊 Results

| Image Type   | No Damage | Partial | Full |
|--------------|-----------|---------|------|
| Sentinel-2   | 1.00      | 0.98    | 0.83 |
| PlanetScope  | 0.98      | 0.90    | 0.89 |
| SR (EDSR)    | 0.99      | 0.96    | 0.89 |

- **Visual Outputs:**  
  - Delta NDVI heatmaps  
  - RGB overlays with classification masks  
  - 3-panel comparison (S2 / SR / PS predictions)

---

## 🧠 Key Insights

- Super-resolution (EDSR) substantially improves full damage classification compared to raw Sentinel-2.
- UNet benefits from enhanced spatial details, especially for fragmented or narrow crop parcels.

---

## 🗂️ Folder Structure

  ├── data/ # Processed GeoTIFFs and masks
  ├── notebooks/ # End-to-end pipeline in Jupyter
  ├── models/ # Trained EDSR & UNet weights
  ├── visualizations/ # PNG overlays, bar plots, flowcharts
  └── utils/ # Helper functions for patching, SR, metrics


---

## 📜 License

This project is open-sourced under the MIT License. Feel free to fork and build upon it!

---

## ✍️ Authors

- **Anurag Sharma** – B.Tech Mathematics & Computing, RGIPT
- **Sanidhya Ghosal** - B.Tech Information Technology, GGV Bilaspur
- **Yash Rawal**
- **Adil Ummer**
- **Under mentorship of Dr. Mukesh Saini during internship at Annam.AI, IIT Ropar**

---

## 📌 Citation

If you use this work, please consider citing or acknowledging the repository in your publications/presentations.

---
