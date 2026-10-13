# ⚡ Temporal GNN: Anti-Money Laundering & Financial Forensics

[![Python 3.11](https://img.shields.io/badge/python-3.11-blue.svg)](https://www.python.org/downloads/)
[![PyTorch 2.1.0](https://img.shields.io/badge/PyTorch-2.1.0-EE4C2C.svg)](https://pytorch.org/)
[![Streamlit App](https://img.shields.io/badge/Streamlit-1.28+-FF4B4B.svg)](https://streamlit.io/)
[![Dataset](https://img.shields.io/badge/Dataset-Elliptic%20Bitcoin-F7931A.svg)](https://www.kaggle.com/datasets/ellipticco/elliptic-data-set)

An end-to-end Machine Learning and Forensic Intelligence platform detecting illicit Bitcoin transactions using **Temporal Graph Neural Networks (GCN + GRU)** on the **Elliptic Data Set**.

---

## 📌 Overview

This repository contains the model architecture, verification suite, and multi-page Streamlit intelligence console for temporal anti-money laundering (AML) detection. 
- **Graph Neural Network (GCN)**: Captures spatial network transaction topologies and graph neighborhood dynamics.
- **Gated Recurrent Unit (GRU)**: Tracks temporal evolution across 49 discrete time steps.
- **Forensic UI Dashboard**: Interactive local CPU inference, sub-graph neighborhood visualizer, risk scoring, early warnings, and model benchmark comparisons (Temporal GNN vs. Baseline GCN vs. XGBoost).

---

## 🚀 Quick Start

### 1. Prerequisites
- **Python 3.11** (64-bit recommended)
- Git

### 2. Environment Setup

```powershell
# Clone the repository
git clone https://github.com/Pratham171717/Temporal_GNN.git
cd Temporal_GNN

# Create and configure virtual environment
py -3.11 -m venv .venv
.\.venv\Scripts\python.exe -m pip install torch==2.1.0 --index-url https://download.pytorch.org/whl/cpu
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
.\.venv\Scripts\python.exe -m pip install -r requirements_ui.txt
```

### 3. Verify Artifacts & Model Inference

Run the integrity verification script before launching the UI:
```powershell
.\.venv\Scripts\python.exe verify_artifacts.py
```
*Ensures file hashes, snapshot indexing, and CPU forward passes match exported Kaggle checkpoints.*

### 4. Launch the Forensic Intelligence Console

```powershell
# Launch the main Streamlit application
.\.venv\Scripts\python.exe -m streamlit run app_intelligence.py --server.port 8502 --theme.base light

# Or launch standard analytics view
.\.venv\Scripts\python.exe -m streamlit run app.py
```

---

## 📂 Project Structure

```text
├── .github/workflows/          # CI linting and code quality workflows
├── .streamlit/                 # UI themes and Streamlit settings
├── artifacts/                  # Model weights (.pth), inference arrays (.npz), metrics
│   ├── artifact_manifest.json  # Checkpoint verification manifest
│   ├── temporal_gnn_weights.pth# Trained GCN + GRU model weights
│   ├── inference_data.npz      # Compressed test set graph tensors
│   └── ...
├── analytics.py                # Graph neighborhood extraction and risk metrics
├── app.py                      # Original 6-page Streamlit analytical dashboard
├── app_intelligence.py         # Advanced Forensic Intelligence UI
├── model.py                    # PyTorch Geometric GCN + GRU architecture definition
├── project_data.py             # Data loading, caching, and CPU inference engine
├── requirements.txt            # Core ML dependencies (torch, torch-geometric, scikit-learn)
├── requirements_ui.txt         # Streamlit and plotting dependencies
├── verify_artifacts.py         # Integrity verifier and inference benchmark test
├── CONTRIBUTING.md             # Contribution guidelines
└── DESIGN_AND_DEMO.md          # Architectural decisions & demo walk-through
```

---

## 📊 Application Pages

| View | Functionality |
| :--- | :--- |
| **Dashboard** | High-level overview of 203,769 transactions across 49 time-steps. |
| **Transaction Analyzer** | Real-time CPU inference on live transactions with instant risk scoring. |
| **Suspicious Network** | Interactive directed graph visualization showing suspect and neighboring wallets. |
| **Future Risk** | Population mean monitoring and temporal risk trajectory projection. |
| **Early Warnings** | Dual-condition threshold alarms for sudden systemic illicit volume spikes. |
| **Model Performance** | Head-to-head metrics: Precision, Recall, F1, Average Precision (AP) vs. Baselines. |

---

## 🧠 Dataset & Attribution

- **Dataset**: [Elliptic Data Set (Kaggle)](https://www.kaggle.com/datasets/ellipticco/elliptic-data-set)
- 203,769 Bitcoin node transactions, 234,355 directed edges, partitioned across 49 chronological time steps.

