🏀 Basketball AI Analytics Pipeline

An open-source, modular computer vision pipeline designed to track players, classify teams without supervision, read jersey numbers, and generate spatial 2D court analytics from broadcast basketball footage.

🚀 Architecture Overview

This pipeline is broken down into modular steps to allow for easy testing and future adaptation to other sports:

Object Detection: Locates players, ball, and rim using RF-DETR.

Player Tracking: Maintains pixel-level tracking across frames using SAM 2.

Team Clustering: Unsupervised team sorting using SigLIP, UMAP, and K-Means.

Court Mapping: Homography matrix projection onto a 2D map using YOLO 11 keypoint detection.

Event Analytics: Trajectory smoothing (MAD) and shot-event detection.

📁 Repository Structure

basketball_analytics/
├── configs/                 # Sport-specific rules and dimensions (court.yaml, etc.)
├── data/                    # Ignored: Local data storage (raw clips, processed frames)
├── models/                  # Ignored: Local storage for model weights (.pth, .pt)
├── notebooks/               # Jupyter notebooks for sandbox testing and experiments
├── src/                     # Core Python modules (detection, tracking, homography)
├── .gitignore               # Keeps heavy files out of the repository
├── README.md                # Project documentation and Dev Log
└── requirements.txt         # Python dependencies


🛠️ Installation

To run this project locally, clone the repository and install the dependencies listed in the requirements.txt file:

git clone https://github.com/SportsFirstAI/basketball_analytics.git
cd basketball_analytics
pip install -r requirements.txt


📅 Project Status & Dev Log

This section tracks the overall progress, milestones, and current development focus for the pipeline.

Phase 1: Project Setup & Baseline Detection (Completed)

Initialized the GitHub repository and established the modular folder architecture (src/, configs/, notebooks/).

Created .gitignore to protect the repo from heavy video/weight files and defined requirements.txt.

Acquired baseline test footage (stephcurryvideo.mp4).

Successfully fine-tuned the RFDETRSmall model in Roboflow for 20 epochs to detect players, ball, and rim.

Wrote the first inference script (PlayerDetection.ipynb) using supervision to draw bounding boxes and successfully exported an annotated MP4.

Phase 2: Tracking & Clustering Initialization (In Progress)

Team Clustering Development: Writing the 02_team_clustering.ipynb notebook. Implementing the math to extract player crops, pass them through SigLIP, reduce dimensionality with UMAP, and cluster them into two distinct teams using K-Means.

SAM 2 Integration: Working on the SAM 2 tracking logic to pass the RF-DETR bounding boxes from Phase 1 into SAM 2 as prompts to generate stable, pixel-level tracking masks.
