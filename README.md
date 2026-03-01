# 🔐 SecureBoost – Privacy-Preserving Credit Risk Analysis

## Breaking Data Silos: Privacy-Preserving Credit Risk Analysis  
### using Federated SecureBoost & CKKS Homomorphic Encryption

**Author:** Samyak Shriram Gedam  
**Institution:** National Institute of Technology Karnataka (NITK)  
**Course:** CS809 – Seminar  

---

## 📌 Overview

SecureBoost is a research-oriented implementation of **Privacy-Preserving Machine Learning (PPML)** for Credit Risk Analysis.

This project simulates a **Vertical Federated Learning (VFL)** setup where:

- 🏦 A **Bank (Host)** holds customer credit labels  
- 💳 A **Fintech Company (Guest)** holds complementary customer features  

Both parties collaboratively train an **XGBoost-based SecureBoost model** without sharing raw data.

To ensure privacy, we use the **CKKS Homomorphic Encryption scheme** (via TenSEAL & PyFhel) to perform encrypted gradient aggregation.

✔ No raw feature exchange  
✔ No label leakage  
✔ Fully encrypted gradient computation  
✔ Secure collaborative training  

---

## 🧠 Core Concepts Implemented

- Vertical Federated Learning (VFL)
- SecureBoost Architecture
- Homomorphic Encryption (CKKS)
- Encrypted Gradient Aggregation
- Privacy-Preserving Credit Risk Classification
- Performance vs Privacy Trade-off Analysis

---

## 🏗 Repository Structure

```
SecureBoost/
│
├── src/                    # Core implementation
├── data/                   # Dataset
├── experiments/            # Model outputs & logs
├── research/               # Paper summaries & notes
├── documentation/          # Report (LaTeX) & Presentation
└── README.md
```

---

## 📊 Dataset

**Dataset Used:** Statlog (German Credit Data)

UCI Repository:  
https://archive.ics.uci.edu/dataset/144/statlog+german+credit+data

### Dataset Setup

1. Download the dataset.
2. Convert to CSV format (if required).
3. Rename the file as:

```
german_credit_data.csv
```

4. Place it inside the project directory (same folder as notebooks).

---

## 💻 System Requirements

### Operating System
- Linux (Ubuntu 20.04+ Recommended)
- macOS
- Windows 10/11 (Requires Visual Studio C++ Build Tools)

### Python
- Python 3.9 or 3.10 (Recommended)
- Avoid Python 3.12 due to compatibility issues

### Hardware
- Minimum 8GB RAM recommended
- Encryption experiments are CPU-intensive

---

## ⚙️ Installation Instructions

⚠️ Use a Virtual Environment to prevent dependency conflicts.

### Step 1 — Create Virtual Environment

```bash
python -m venv venv
```

### Step 2 — Activate Environment

**Windows**
```bash
venv\Scripts\activate
```

**Linux / macOS**
```bash
source venv/bin/activate
```

### Step 3 — Install System Dependencies (Linux Only)

```bash
sudo apt-get update
sudo apt-get install cmake build-essential libgmp-dev
```

### Step 4 — Install Python Dependencies

```bash
pip install numpy pandas scikit-learn xgboost imbalanced-learn jupyter
pip install tenseal==0.3.16
pip install syft==0.8.5
pip install pyfhel
```

Versions are pinned to ensure compatibility.

---

## 🚀 How to Run the Project

Launch Jupyter Notebook:

```bash
jupyter notebook
```

Run notebooks in the following order:

### 1️⃣ 1.VFL + HE 2 Party.ipynb (Primary Demo)

- Simulates 2-party VFL
- SecureBoost training with CKKS encryption
- Outputs ROC-AUC score
- Full encrypted gradient workflow

### 2️⃣ 2.Parties Comparison.ipynb (Scalability Test)

- Splits dataset across 4 parties
- Tests performance stability

### 3️⃣ 3.Hyperparameters.ipynb

- Learning rate tuning
- Max depth tuning
- Tree count experiments

### 4️⃣ 4.Performance_Overhead_Analysis.ipynb

- Measures computational latency
- Benchmarks encryption overhead

### 5️⃣ 5.Encryption_Time.ipynb

- Detailed encryption timing metrics

⚠️ Encryption benchmarks may take several minutes to execute.

---

## 📈 Experimental Focus

| Component | Objective |
|-----------|-----------|
| Accuracy | Validate model performance under encryption |
| Scalability | Evaluate multi-party splitting |
| Latency | Measure encryption/decryption time |
| Resource Usage | Monitor CPU and RAM overhead |

---

## 🔐 Privacy Architecture Summary

1. Data is vertically split between parties.
2. Gradients are encrypted using CKKS.
3. Aggregation is performed in encrypted space.
4. Only the authorized host decrypts results.
5. Raw features and labels are never exchanged.

This ensures:
- Zero raw data exposure
- Secure collaborative model training
- Practical PPML deployment feasibility

---

## 🛠 Troubleshooting

### ❌ ModuleNotFoundError: tenseal
Ensure the virtual environment is activated before launching Jupyter.

### ❌ Could not build wheels for tenseal (Windows)
Install:
- Visual Studio Build Tools
- Select “Desktop development with C++”

### ❌ Kernel Crashes / High RAM Usage
- Reduce `n_estimators`
- Use smaller CKKS parameters
- Close other memory-intensive programs

---

## 🎓 Academic Context

- Course: CS809 – Seminar
- Program: M.Tech – Computer Science
- Institution: National Institute of Technology Karnataka

This project demonstrates a practical implementation of SecureBoost with CKKS encryption for real-world credit risk analysis.

---

## 🚀 Future Work

- Multi-party production-scale deployment
- GPU-accelerated homomorphic encryption
- Integration with banking APIs
- Differential Privacy augmentation
- Optimized secure aggregation protocols

---

## 👨‍💻 Author

Samyak Shriram Gedam  
M.Tech – Computer Science  
National Institute of Technology Karnataka  

---

⭐ If you found this work useful, consider starring the repository.
