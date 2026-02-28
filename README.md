# 🔐 SecureBoost – Privacy Preserving Machine Learning

### PROJECT TITLE: Breaking Data Silos: Privacy-Preserving Credit Risk Analysis using Federated SecureBoost & Homomorphic Encryption (CKKS)
### AUTHORS:       Samyak Shriram Gedam
### INSTITUTION:   National Institute of Technology Karnataka (NITK)

---

## 📌 Overview

This project implements a privacy-preserving machine learning framework for
Credit Risk Analysis. It simulates a "Vertical Federated Learning" (VFL)
scenario where a Bank (holding labels) and a Fintech company (holding features)
collaborate to train an XGBoost model without sharing raw customer data.

We utilize the CKKS Homomorphic Encryption scheme (via TenSEAL/PyFhel) to
perform secure gradient aggregation, ensuring zero data leakage.

---

## 🏗 Repository Structure

- `src/` → Core implementation code
- `data/` → Dataset
- `experiments/` → Model outputs and evaluation logs
- `research/` → Paper summaries and theory references
- `documentation/` → LaTeX source, report, presentation
- `README.md`

---

## 🎯 Objectives

- Understand privacy-preserving ML architecture
- Study secure computation techniques
- Experiment with secure model training approaches

---

## 🔐 Focus Areas

- SecureBoost Architecture
- Encrypted Model Training
- Homomorphic Encryption Concepts
- Secure Data Handling

---

## 📊 Reproducibility

1. Clone repository
2. Install dependencies
3. Run experiments from `src/`

---

### PREREQUISITES
To run this project on a standalone machine, you need:

1. Operating System: 
   - Linux (Ubuntu 20.04+ recommended) OR
   - macOS OR
   - Windows 10/11 (Requires "C++ Build Tools" installed for encryption libs)

2. Python Version: 
   - Python 3.9 or 3.10 is recommended. 
   - (Newer versions like 3.12 might have conflicts with PySyft/TenSEAL).

---

### INSTALLATION INSTRUCTIONS
It is highly recommended to use a Virtual Environment to avoid library conflicts.

- STEP 1: Create a Virtual Environment
   Open your terminal/command prompt and run:
   $ python -m venv venv

- STEP 2: Activate the Environment
   - Windows:
     $ venv\Scripts\activate
   - Linux/Mac:
     $ source venv/bin/activate

- STEP 3: Install System Dependencies (Linux Only)
   If you are on Linux, you need C++ compilers for the encryption libraries:
   $ sudo apt-get install cmake build-essential libgmp-dev

- STEP 4: Install Python Libraries
   Run the following command to install all required packages:
   
   $ pip install numpy pandas scikit-learn xgboost imbalanced-learn jupyter
   $ pip install tenseal==0.3.16 
   $ pip install syft==0.8.5
   $ pip install pyfhel

   (Note: TenSEAL and PySyft versions are pinned to ensure compatibility).

---

### DATASET SETUP
The project uses the "Statlog (German Credit Data)" dataset.

1. Download the dataset from the UCI Machine Learning Repository or Kaggle.
   [Link](https://archive.ics.uci.edu/dataset/144/statlog+german+credit+data)
   
2. Ensure you have the CSV file named "german_credit_data.csv" (or as referenced
   in the notebooks).

3. Place the CSV file in the SAME directory as the Jupyter Notebooks.

---

### HOW TO RUN THE PROJECT
Launch Jupyter Notebook by running:
   $ jupyter notebook

You will see 5 notebooks. Run them in the following order to replicate our
experiments:

1.  "1.VFL + HE 2 Party.ipynb" (PRIMARY DEMO)
    - This is the main implementation.
    - It simulates 1 Host (Bank) and 1 Guest (Fintech).
    - It trains the SecureBoost model and outputs the ROC/AUC score.
    - Run all cells to see the privacy-preserving training in action.

2.  "2. Parties Comparison.ipynb" (SCALABILITY TEST)
    - Run this to see what happens when data is split among 4 parties.
    - Demonstrates that accuracy remains stable even with more fragmentation.

3.  "3. Hyperparameters.ipynb"
    - Run this if you want to see how we tuned the XGBoost parameters
      (learning rate, max depth, etc.) for this dataset.

4.  "4.Performance_Overhead_Analysis.ipynb" & "5.Encryption Time.ipynb"
    - Run these to view the benchmarks for computational latency.
    - CAUTION: Encryption benchmarks can take time (minutes) to run on CPUs.

---

### TROUBLESHOOTING
Issue 1: "ModuleNotFoundError: No module named 'tenseal'"
   - Solution: Ensure you activated your virtual environment before launching
     Jupyter Notebook.

Issue 2: "ERROR: Could not build wheels for tenseal" (On Windows)
   - Solution: You need to install "Visual Studio Build Tools" with the
     "Desktop development with C++" workload checked.

Issue 3: Kernel crashes during training
   - Solution: Homomorphic Encryption uses a lot of RAM. If your machine has
     less than 8GB RAM, try reducing the 'n_estimators' (number of trees)
     in the XGBoost configuration inside the notebook.

---

## 🎓 Academic Context

- Course: CS809 – Seminar 
- Type: Research-Oriented Project  

---

## 👨‍💻 Author

Samyak Gedam  
M.Tech – Computer Science
National Institute of Technology Surathkal, Karnataka.
