# AI-Powered Sampling Engine for Real-Time Quality Analytics and Cost-Aware Manufacturing

This project proposes an AI-based Smart Sampling system designed to replace outdated AQL methods in Final Visual Inspection (FVI) of semiconductor manufacturing. The system integrates real-time defect detection, adaptive sampling logic, traceability, and economic optimization.

## 🔍 Key Features
- Real-time image-based defect detection using YOLOv8n
- Rule-based and feedback-driven sampling engine
- LightGBM for risk prediction and learning from batch history
- Cost-aware inspection logic: optimize effort vs defect risk
- Modular edge deployment (RPi / Jetson)

## 📊 Tech Stack
- Python, YOLOv8n, LightGBM
- CSV + image datasets
- Jupyter Notebooks for simulation
- Deployed on edge (RPi 4 / Jetson Nano)

## 📁 Folder Structure
- `notebooks/`: Model demos and sampling simulation
- `src/`: Python source code
- `data/`: Defect image dataset and mock sensor logs
- `assets/`: Poster, banner, system diagrams
- `docs/`: Project report and tiered system explanation

## 🖼️ Preview
1. PRODUCT FLOW (e.g. wafer/PCB)
        ↓
2. IMAGE CAPTURE MODULE
    [Camera Module: RPi Cam / USB Webcam]
        ↓
3. EDGE AI UNIT
    [Jetson Nano / Raspberry Pi 4]
    └─ YOLOv8n detects defect (class, location, confidence)
        ↓
4. SMART SAMPLING ENGINE
    ├─ Decision Logic: Accept / Resample / Reject
    ├─ Factors:
    │   ├─ Defect type & severity
    │   ├─ Confidence level
    │   ├─ Batch history
    │   └─ Stage/machine risk
    └─ Output: Decision per unit
        ↓
5. FEEDBACK LEARNING LOOP
    [LightGBM model]
    ├─ Inputs:
    │   ├─ Historical defect trends
    │   ├─ Sensor logs (temperature, machine ID, shift)
    │   └─ Past sampling results
    └─ Adjust sampling % for future batches
        ↓
6. COST-AWARE OPTIMIZER
    ├─ Calculates:
    │   ├─ (Defect Risk × Failure Cost)
    │   └─ Compare with Inspection Cost
    └─ Adjusts sampling rate accordingly
        ↓
7. TRACEABILITY MODULE
    └─ Maps defect to stage/machine via:
        ├─ Timestamp
        ├─ Sensor log
        └─ Batch metadata
        ↓
8. DASHBOARD / REPORT OUTPUT
    ├─ Real-time decision logs
    ├─ Defect distribution heatmap
    └─ Adaptive sampling trends



