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
├── .gitignore
├── datasets/            # Dataset sources / links (not huge archives)
├── models/              # Small configs, scripts, links to model weights
├── notebooks/           # Training and evaluation notebooks
├── dashboard/           # Dashboard source code, if shared
├── docs/                # Presentation and project documentation
└── assets/              # Screenshots and short demo media
```

## Datasets and Pretrained Weights
Datasets for the prototype include **VisDrone** aerial vehicle images and license-plate image datasets. For large files, publish accessible cloud links here rather than committing gigabytes to Git:

- **Datasets:** [Google Drive folder — add sharing link](ADD_DATASETS_LINK_HERE)
- **Trained models:** [Google Drive folder — add sharing link](ADD_MODELS_LINK_HERE)
- **Evaluation notebooks:** [Google Drive folder — add sharing link](ADD_NOTEBOOKS_LINK_HERE)

Check the terms of use and redistribution rights of each third-party dataset and pretrained model before republishing its files.

## Project Demo
Add a screenshot of the dashboard in `assets/dashboard.png`, then uncomment this line:

<!-- ![MADAR operator dashboard](assets/dashboard.png) -->

A demo video or walkthrough can also be linked here.

## Running the Project
The repository currently documents multiple prototype components. Once source code and dependencies are uploaded, add component-specific installation and run instructions under `dashboard/` and `models/`. The presentation and evaluation notebook alone are **not** a fully runnable end-to-end application.

## Future Work
- Integrate drone flight simulation and the computer vision pipeline.
- Evaluate the end-to-end workflow at a larger scale.
- Improve robustness under different lighting, viewpoints, and operational conditions.
- Explore additional deployment scenarios beyond Expo 2030.

## Team
Developed as part of the Autonomous Drone Systems Bootcamp project by the MADAR team.

## Presentation
[MADAR Expo presentation (Google Drive — add sharing link)](ADD_PRESENTATION_LINK_HERE). The original PowerPoint is large, so linking it avoids the GitHub browser upload limit.
