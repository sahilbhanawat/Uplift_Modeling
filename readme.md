<div align="center">
  <h1>🎯 Uplift Modeling: Optimizing Marketing ROI</h1>
  <h3>Causal Inference to Identify "Persuadable" Customers</h3>

  <p>
    <img src="https://img.shields.io/badge/Python-3.9-blue" alt="Python Version">
    <img src="https://img.shields.io/badge/Library-Scikit--Learn-orange" alt="Scikit-Learn">
    <img src="https://img.shields.io/badge/Technique-Causal%20Inference-green" alt="Technique">
    <img src="https://img.shields.io/badge/Status-Completed-success" alt="Status">
  </p>

  <p>
    <a href="#-business-impact">Business Impact</a> •
    <a href="#-the-solution">The Solution</a> •
    <a href="#-how-to-run">How To Run</a>
  </p>
</div>

---

## 🧐 The Business Problem
**Context:** A retail company sends promotional emails to all customers. However, mass marketing is inefficient:
* It wastes money on **"Sure Things"** (customers who would buy anyway).
* It annoys **"Sleeping Dogs"** (customers who react negatively to ads).
* It ignores the **"Persuadables"** (the only group that truly adds incremental value).

**Goal:** Build an Uplift Model to target *only* the Persuadables, thereby maximizing **Incremental ROI**.

---

## 🏆 Business Impact (The "Money Slide")
Using a **T-Learner Causal Model** on a blind test set of 8,500 customers, I simulated two strategies. The Uplift strategy significantly outperformed the baseline.

| Strategy | Target Audience | Revenue | Cost | **Profit (ROI)** |
| :--- | :--- | :--- | :--- | :--- |
| **Mass Marketing** | 100% (Everyone) | $10,995 | $8,520 | $2,475 |
| **Uplift Model** | Top 20% (Persuadables) | $9,868 | $1,704 | **$8,164** |
| **Impact** | | | | **+230% Increase** 🚀 |

> **Key Insight:** By emailing 80% *fewer* people, we nearly *tripled* the profit.

---

## 🔬 Methodology & Tech Stack

### The Approach: The "Four Quadrants"
I used Causal Inference to categorize customers based on their **Conditional Average Treatment Effect (CATE)**:

* 🟩 **Persuadables:** Buy only if treated. *(High Uplift)* -> **Target**
* ⬜ **Sure Things:** Buy regardless. *(Zero Uplift)* -> **Ignore**
* ⬜ **Lost Causes:** Never buy. *(Zero Uplift)* -> **Ignore**
* 🟥 **Sleeping Dogs:** Churn if treated. *(Negative Uplift)* -> **Avoid**

### Tech Stack
* **Python:** Pandas, NumPy
* **Machine Learning:** Scikit-Learn (Random Forest Classifiers)
* **Causal Method:** T-Learner (Meta-Learner)
* **Evaluation:** Qini Curve, Decile Analysis

---

## 📊 Visualizing Success
*The chart below demonstrates the model's ability to segregate high-lift customers (Decile 9) from negative-lift customers (Decile 0).*

![Uplift Decile Chart](images/uplift_by_decile.png)
*(Note: Ensure you save your bar chart as `uplift_by_decile.png` in an `images` folder)*

---

## 📂 Repository Structure

```bash
├── data/
│   ├── Kevin_Hillstrom_MineThatData_E-MailAnalytics.csv  # Dataset
├── notebooks/
│   ├── uplift_modeling_end_to_end.ipynb   # Complete analysis & modeling
├── images/
│   ├── uplift_by_decile.png               # Visualizations for README
├── README.md                              # Project Documentation
└── requirements.txt                       # Python dependencies