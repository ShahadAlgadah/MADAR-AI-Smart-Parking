<div align="center">

# MADAR | مدار
### AI-Powered Drone-Based Smart Parking Management

**A smart parking monitoring and vehicle management prototype designed for large-scale events, including Expo 2030.**

</div>

## Overview
MADAR combines drone imagery, computer vision, vehicle tracking, and an operator dashboard to help event teams monitor parking areas and improve the visitor experience. It explores how aerial data can support vehicle location, parking-rule monitoring, and congestion management.

[🚀 Live Dashboard Demo](https://shahadalgadah.github.io/MADAR-AI-Smart-Parking/dashboard/MADAR_Dashboard.html)

## Key Features
- **Find My Car:** Locate a vehicle using its license plate and provide navigation assistance.
- **Smart Navigation:** Guide visitors toward their vehicle.
- **Wrong Parking Detection:** Identify potentially incorrectly parked vehicles.
- **Overstay Detection:** Track vehicles over time to flag prolonged parking.
- **Exit Optimization:** Support operators in monitoring traffic flow and planning departures.
- **Operator Dashboard:** Central view of vehicle locations, alerts, parking areas, and analytics.

> **Project status:** Prototype / demonstration. The features above reflect the proposed system; they are not all validated as production-ready end-to-end functions.

## Technology Stack
| Component | Technology |
| --- | --- |
| Vehicle detection | YOLO |
| License-plate detection | YOLO |
| License-plate recognition | PaddleOCR PP-OCRv5 |
| Vehicle tracking | ByteTrack |
| AI training and evaluation | Python, Google Colab |
| User experience | Operator dashboard and Find My Car mobile UI prototype |

## Computer Vision Pipeline
```text
Drone video / aerial imagery
         ↓
Vehicle detection (YOLO)
         ↓
Vehicle tracking (ByteTrack)
         ↓
License-plate detection (YOLO)
         ↓
License-plate recognition (PaddleOCR)
         ↓
Vehicle ID, location and timestamps
         ↓
Parking analytics / alerts / Find My Car
```

## Model Evaluation
Results reported in the project presentation:

| Model / task | Precision | Recall | mAP@50 | mAP@50:95 |
| --- | ---: | ---: | ---: | ---: |
| Vehicle detection | 97.6% | 93.4% | 97.4% | 66.7% |
| License-plate detection | 95.0% | 93.6% | 98.5% | 84.3% |

**OCR (English PP-OCRv5 mobile recognition):** 97.26% exact-plate accuracy (labeled *Precision* in the slides), 99.54% character accuracy, and 0.46% character error rate. These are evaluation results for the reported test setting and do not establish real-world performance across all Saudi plate formats and drone conditions.

## Repository Structure
```text
MADAR-AI-Smart-Parking/
├── README.md
├── dashboard/
│   ├── MADAR_Dashboard.html
│   └── README.md
└── notebooks/
    ├── MADAR_All_Models_Evaluation .ipynb
    └── README.md
```

## Datasets and Pretrained Weights
Datasets for the prototype include **VisDrone** aerial vehicle images and license-plate image datasets.

- ### Datasets Used

The following datasets were used to support vehicle and license plate detection in MADAR:

- **[VisDrone Dataset](https://github.com/VisDrone/VisDrone-Dataset)** — Aerial imagery for vehicle detection using YOLO.
- **[License Plate Project – Roboflow](https://universe.roboflow.com/test-vaxvp/license-plate-project-adaad)** — License plate image dataset for training the license plate detection model.
- **CARPK Dataset** — Parking lot imagery used for vehicle detector fine-tuning.
- **Trained models:** [MADAR Models – Google Drive](https://drive.google.com/drive/folders/1ofM27k1upHCMFaNxc2yG5xq_cnwK4eX2?usp=sharing)
- **Evaluation notebook:** [MADAR All Models Evaluation](notebooks/MADAR_All_Models_Evaluation%20.ipynb)

Check the terms of use and redistribution rights of each third-party dataset and pretrained model before republishing its files.


## Team

**Autonomous Drone Systems Bootcamp**  
Tuwaiq Academy × Misk Skills

**MADAR Team Members:**
- Shahad Algadah
- Nuha Alrubayyi
- Mariam Alessi
- Faisal Alkhater
- Mariyah AlMoaili

MADAR was developed as part of the Autonomous Drone Systems Bootcamp, focusing on AI-powered drone solutions for smart parking management at large-scale events, including Expo 2030.

## Project Presentation

[📊 View MADAR Expo Presentation](https://docs.google.com/presentation/d/1Xo5K68q6CPtzN0iNNDevceMTPHsXKNwW/edit?usp=sharing&ouid=100071248718851677963&rtpof=true&sd=true)
