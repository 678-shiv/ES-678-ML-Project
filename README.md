# ML-Based Prediction of Flexural Load Capacity of CFRP-Strengthened RC Beams

**ES 678 Course Project — IIT Gandhinagar**
**Author:** Shivam Gautam (Roll No: 25350005)

---

## 📌 Project Overview

This project applies machine learning to predict the **ultimate load capacity (Pᵤ)** of reinforced concrete (RC) beams strengthened with externally bonded Carbon Fibre-Reinforced Polymer (CFRP) laminates.

Existing code-based models (ACI 440.2R) rely on simplified assumptions that deviate from experimental results for unusual geometries. This work trains and compares:
- **Random Forest (RF) Regression**
- **Support Vector Regression (SVR) with RBF kernel**
- **Multiple Linear Regression (Baseline)**

**Best result:** SVR achieves R² = 0.9822, RMSE = 8.39 kN, MAPE = 6.91% on the held-out test set.

---


---

## 📊 Dataset

- **Source:** Mendeley Data — https://data.mendeley.com/datasets/c5tb3whh2j/2
- **Size:** 1,695 experimental specimens
- **Split:** 1,356 train / 339 test (pre-defined by dataset provider)
- **Target:** Pᵤ (kN) — ultimate load capacity
- **Features:** 19 input variables (beam geometry, concrete, steel, CFRP properties)

---

## ⚙️ Setup and Installation


**Requirements:**
- Python 3.11+
- scikit-learn 1.5
- pandas 2.1
- scipy 1.11

---

## 🚀 How to Run

Place the dataset in the `data/` folder, then run scripts in order:




## 📈 Results Summary

| Model | R² | RMSE (kN) | MAE (kN) | MAPE (%) |
|---|---|---|---|---|
| Linear Regression (Baseline) | 0.7804 | 29.50 | 21.69 | 43.32 |
| Random Forest | 0.9726 | 10.42 | 5.71 | 8.70 |
| **SVR (RBF kernel)** | **0.9822** | **8.39** | **4.11** | **6.91** |

**Key finding:** SVR with RBF kernel achieves the best performance. Permutation importance identifies effective depth (d), tension steel area (As1), and beam height (h) as the most influential features — consistent with ACI 440 capacity scaling.

---

## 🔑 Key Features Used

| Group | Features |
|---|---|
| Beam Geometry | b, h, Lo, B, d |
| Concrete | fc |
| Steel | As1, As2, fy1, fy2, Es1, Es2 |
| CFRP | tf, bf, Af, Ef, ff |
| Configuration | Anchor, Loading |

---

## 📄 Paper

The full paper is in the `paper/` folder. 

---

## 🤖 AI Use Disclosure

AI tools (Claude, ChatGPT) were used to assist with dataset identification, code scaffolding, and paper-structure feedback. All results were independently executed, verified, and interpreted by the author.

---

## 📚 References

- Breiman, L. (2001). Random Forests. *Machine Learning*, 45(1), 5–32.
- Smola & Schölkopf (2004). A Tutorial on SVR. *Statistics and Computing*.
- Teng et al. (2003). *FRP-Strengthened RC Structures*. Wiley.
- ACI 440.2R-17. American Concrete Institute.
- Tiljani et al. (2026). Mendeley Data V2. DOI: 10.17632/c5tb3whh2j.2
