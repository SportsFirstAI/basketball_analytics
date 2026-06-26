# 🏀 Basketball AI Analytics Pipeline

An **open-source, modular computer vision pipeline** designed to track players, classify teams without supervision, recognize jersey numbers, and generate **2D spatial basketball analytics** from broadcast footage.

The project is built with a modular architecture so that individual components can be improved independently and easily adapted to other sports.

---

# 🚀 Features

- 🎯 Player, ball, and rim detection using **RF-DETR**
- 🏃 Multi-object tracking using **SAM 2**
- 👕 Unsupervised team classification using **SigLIP + UMAP + K-Means**
- 🗺️ Court homography projection for 2D analytics
- 📊 Trajectory smoothing and basketball event analytics
- 🔧 Modular architecture for research and future expansion

---

# 🏗️ Pipeline Architecture

```
Broadcast Video
       │
       ▼
RF-DETR Object Detection
       │
       ▼
SAM 2 Player Tracking
       │
       ▼
Player Crop Extraction
       │
       ▼
SigLIP Feature Embeddings
       │
       ▼
UMAP Dimensionality Reduction
       │
       ▼
K-Means Team Clustering
       │
       ▼
YOLO11 Court Keypoint Detection
       │
       ▼
Homography Transformation
       │
       ▼
2D Court Mapping
       │
       ▼
Trajectory Smoothing + Event Analytics
```

---

# 📁 Repository Structure

```text
basketball_analytics/
│
├── configs/                 # Sport-specific configurations (court dimensions, rules)
├── data/                    # Local datasets (ignored by Git)
├── models/                  # Model weights (.pt, .pth) (ignored by Git)
├── notebooks/               # Jupyter notebooks for experimentation
├── src/                     # Core Python modules
│   ├── detection/
│   ├── tracking/
│   ├── clustering/
│   ├── homography/
│   └── analytics/
│
├── .gitignore
├── README.md
└── requirements.txt
```

---

# 🛠️ Installation

Clone the repository:

```bash
git clone https://github.com/SportsFirstAI/basketball_analytics.git
```

Move into the project directory:

```bash
cd basketball_analytics
```

Install the dependencies:

```bash
pip install -r requirements.txt
```

---

# 🧠 Tech Stack

| Component | Model / Library |
|------------|-----------------|
| Object Detection | RF-DETR |
| Tracking | SAM 2 |
| Image Embeddings | SigLIP |
| Dimensionality Reduction | UMAP |
| Team Classification | K-Means |
| Court Keypoints | YOLO11 Pose |
| Visualization | OpenCV, Supervision |
| Analytics | NumPy, Pandas |

---

# 📅 Development Roadmap

## ✅ Phase 1 — Project Setup & Baseline Detection *(Completed)*

- Repository initialized with modular architecture
- Created project folders (`src`, `configs`, `notebooks`, etc.)
- Added `.gitignore` and `requirements.txt`
- Collected baseline test footage (`stephcurryvideo.mp4`)
- Fine-tuned **RF-DETR Small** for **20 epochs** on Roboflow
- Successfully detected:
  - Players
  - Basketball
  - Rim
- Developed the initial inference notebook:
  - `01_player_detection.ipynb`
- Generated annotated MP4 output using **Supervision**

---

## 🚧 Phase 2 — Tracking & Team Classification *(In Progress)*

### 👕 Team Clustering

Current work includes:

- Extracting player image crops
- Computing SigLIP feature embeddings
- Applying UMAP for dimensionality reduction
- Clustering players into two teams using K-Means

Notebook:

```
02_team_clustering.ipynb
```

---

### 🏃 SAM 2 Tracking

Current work includes:

- Feeding RF-DETR bounding boxes into SAM 2
- Creating stable segmentation masks
- Maintaining player identities across frames
- Improving temporal consistency

---

## 🔜 Upcoming Phases

### Phase 3

- Jersey Number Recognition (OCR)

### Phase 4

- Court Homography Mapping
- 2D Court Visualization

### Phase 5

- Ball Trajectory Estimation
- Shot Detection
- Possession Analytics
- Heatmaps
- Pass Networks

---

# 🎯 Current Status

| Module | Status |
|---------|--------|
| Repository Setup | ✅ Completed |
| RF-DETR Detection | ✅ Completed |
| Video Inference | ✅ Completed |
| SAM 2 Tracking | 🚧 In Progress |
| Team Clustering | 🚧 In Progress |
| Court Homography | ⏳ Planned |
| Jersey OCR | ⏳ Planned |
| Event Analytics | ⏳ Planned |

---

# 🤝 Contributing

Contributions, ideas, and improvements are welcome!

If you'd like to contribute:

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Open a Pull Request

---

# 📄 License

This project is released under the **MIT License**.

---

# ⭐ Support

If you find this project useful, consider giving it a ⭐ on GitHub to support future development.