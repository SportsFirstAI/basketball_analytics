# Basketball Analytics Pipeline

## Stage 1

Object Detection

Model

RF-DETR

Output

Players

Ball

Referee

Rim

Basketball Events

---

## Stage 2

Player Tracking

Model

SAM2

Output

Persistent Player IDs

---

## Stage 3

Team Classification

Model

SigLIP

↓

UMAP

↓

KMeans

Output

Team A

Team B

---

## Stage 4

Jersey OCR

Model

Small Vision Language Model

Output

Player Number

---

## Stage 5

Homography

Model

YOLO11 Pose

Output

2D Court Coordinates

---

## Stage 6

Trajectory Smoothing

Algorithm

Median Absolute Deviation

Linear Interpolation

Sliding Window

---

## Stage 7

Shot Analytics

Output

Made

Missed

Heatmaps

Shot Charts

Pass Networks