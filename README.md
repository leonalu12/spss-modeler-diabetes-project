# IBM SPSS Modeler – Diabetes Risk Factors (BRFSS 2015)

> Reproducible project skeleton for **INFOSYS 722 – Iteration 2 (Steps 1–8)**  
> Owner: Leona Lu · Created: 2025-08-11

## Overview
This repository contains the artifacts to implement **Steps 1–8** of the CRISP‑DM-style assignment using **IBM SPSS Modeler** on the BRFSS 2015 Diabetes Health Indicators dataset.

- **Goal:** Predict `Diabetes_binary` and identify key risk factors
- **Tools:** IBM SPSS Modeler (streams)
- **Data:** BRFSS 2015 diabetes indicators (public). _Large files are tracked via Git LFS._

## Repo Structure
```
.
├── data/
│   ├── raw/                # Original data (e.g., diabetes_binary_health_indicators_BRFSS2015.xlsx/.csv)
├── modeler/
│   ├── streams/            # *.str SPSS Modeler streams (export your flows here)
├── reports/                # Report (pdf) and figures used in the paper
├── .gitattributes          # Git LFS rules for large/binary files
├── .gitignore
└── README.md
```

## How to Reproduce (SPSS Modeler)
1. **Open IBM SPSS Modeler** → create a new stream.
2. **Data Understanding (Step 2)**  
   - Add a **Var. File** node → load `data/raw/diabetes_binary_health_indicators_BRFSS2015.xlsx`  
   - Add **Data Audit** node → run and export audit table to `reports/`.
3. **Data Preparation (Step 3)**  
   - Use **Select, Filter, Derive** nodes (e.g., derive BMI categories).  
   - Document outlier handling (Capping/Discard) and type corrections.
4. **Transformation (Step 4)**  
   - **Filler/Type** nodes, **Partition** (70/30), **Balance** (e.g., Over/Under/SMOTE).  
   - Apply **Field Reorder/Filter** for feature selection.
5. **Method & Algorithm (Steps 5–6)**  
   - Add **Logistic Regression**, **C5.0/CHAID**, and optionally **Random Forest** nodes.  
   - Keep **Auto Classifier** for quick comparison (optional).
6. **Modeling (Step 7)**  
   - Train models
   - Use **Analysis** and **Evaluation** nodes to compare models.  
7. **Evaluation & Interpretation (Step 8)**  
   - Export variable importance, tree diagrams, and charts to the report  
   - Record multiple iterations (balancing on/off, feature subsets) in `docs/iterations.md`.

## License
This repo template is for coursework. Data usage must comply with BRFSS/Kaggle terms.
