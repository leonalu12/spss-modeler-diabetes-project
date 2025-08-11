# IBM SPSS Modeler – Diabetes Risk Factors (BRFSS 2015)

> Reproducible project skeleton for **INFOSYS 722 – Iteration 2 (Steps 1–8)**  
> Owner: Leona Lu · Created: 2025-08-11

## Overview
This repository contains the artifacts to implement **Steps 1–8** of the CRISP‑DM-style assignment using **IBM SPSS Modeler** on the BRFSS 2015 Diabetes Health Indicators dataset.

- **Goal:** Predict `Diabetes_binary` and identify key risk factors
- **Tools:** IBM SPSS Modeler (streams), optional SPSS Statistics (syntax), optional Python for mirrored EDA
- **Data:** BRFSS 2015 diabetes indicators (public). _Large files are tracked via Git LFS._

## Repo Structure
```
.
├── data/
│   ├── raw/                # Original data (e.g., diabetes_binary_health_indicators_BRFSS2015.xlsx/.csv)
│   └── processed/          # Cleaned / transformed exports from Modeler
├── modeler/
│   ├── streams/            # *.str SPSS Modeler streams (export your flows here)
│   └── exports/            # Model nuggets, evaluation results, scored data
├── spss_syntax/            # Optional *.sps if using SPSS Statistics
├── notebooks/              # Optional Python notebooks (EDA parity with SPSS)
├── reports/                # Report (docx/pdf) and figures used in the paper
├── figures/                # Charts exported from Modeler (ROC, tree, etc.)
├── scripts/                # Utility scripts (e.g., data checks)
├── docs/                   # Extra documentation
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
   - **Filler/Type** nodes, **Partition** (e.g., 70/30), **Balance** (e.g., Over/Under/SMOTE).  
   - Apply **Field Reorder/Filter** for feature selection.
5. **Method & Algorithm (Steps 5–6)**  
   - Add **Logistic Regression**, **C5.0/CHAID**, and optionally **Random Forest** nodes.  
   - Keep **Auto Classifier** for quick comparison (optional).
6. **Modeling (Step 7)**  
   - Train models using the **Partition** node.  
   - Save **ROC**, **Gains**, **Confusion Matrix** outputs to `figures/` and `reports/`.
7. **Evaluation & Interpretation (Step 8)**  
   - Use **Analysis** and **Evaluation** nodes to compare models.  
   - Export variable importance, tree diagrams, and charts.  
   - Record multiple iterations (balancing on/off, feature subsets) in `docs/iterations.md`.

> 🔁 **Submission ZIP**: Include the entire project folder with data and streams. Also submit your Word/PDF report in `reports/`.

## Running a Python Mirror (Optional)
If collaborators lack SPSS licenses, mirror core EDA/classification in `notebooks/`. Keep outputs consistent with Modeler (ROC, confusion matrix).

## Academic Integrity Disclaimer
Append the required UoA disclaimer to the end of your report (see `docs/disclaimer.md`).

## License
This repo template is for coursework. Data usage must comply with BRFSS/Kaggle terms.
