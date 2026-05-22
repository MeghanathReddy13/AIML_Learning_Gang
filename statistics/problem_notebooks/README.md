# Problem-Based Learning Notebooks

Each notebook teaches statistics and ML concepts through a complete, real-world problem — from raw data to working predictions.

**Approach:** Problem first → explore the data → concepts emerge naturally → predictions follow.

---

## The Four Problems

| Notebook | Problem | Type | Dataset |
|---|---|---|---|
| `Problem01_Titanic_Survival.ipynb` | Who survived the Titanic? | Binary Classification | seaborn built-in |
| `Problem02_House_Price_Prediction.ipynb` | What drives California house prices? | Regression | sklearn built-in |
| `Problem03_Student_Performance.ipynb` | Which students will struggle? | Regression + Classification | Synthetic (realistic) |
| `Problem04_Heart_Disease_Prediction.ipynb` | Who is at risk of heart disease? | Binary Classification | Synthetic (clinical) |

---

## What Each Notebook Covers

Every notebook follows the same journey:

```
1. Meet the Problem       → understand the goal and the data
2. Data Health Check      → missing values, data types, describe()
3. Column-by-Column       → distribution of every feature (histogram, box plot, stats)
4. Target Variable        → understand what we're predicting
5. Feature vs Target      → what predicts the outcome? (box plots, scatter, rates)
6. Multi-Variable         → correlation heatmap, pair plots, interaction effects
7. Feature Engineering    → create better features from raw data
8. Prediction             → build and evaluate models
9. What We Learned        → connect concepts back to findings
```

---

## Statistical Concepts Taught

| Concept | Where It Appears |
|---|---|
| Mean, Median, Mode | Section 2–3 in every notebook |
| Std Dev, Variance, Spread | Section 3 per-column analysis |
| Skewness & transformations | Fare (Titanic), Income (Housing), Population (Housing) |
| Outliers (IQR method) | Rooms (Housing), Cholesterol (Heart Disease) |
| Distributions (normal, skewed, bimodal, Poisson) | Section 3 throughout |
| Correlation (Pearson r) | Section 5 & 6 in every notebook |
| Heatmaps | Section 6 in every notebook |
| Class imbalance | Titanic, Heart Disease |
| Feature engineering | Section 7 in every notebook |
| Train/test split | Section 8 in every notebook |
| Confusion matrix | Titanic, Student, Heart Disease |
| ROC / AUC | Heart Disease |
| Feature importance | Section 8 in every notebook |

---

## Prerequisites

```bash
pip install numpy pandas matplotlib seaborn scikit-learn jupyter
```

Start with **Problem01** (Titanic) — it's the most intuitive entry point.
