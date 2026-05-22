# Statistics for Machine Learning

A structured 14-week course taking learners from zero statistics knowledge to full ML understanding — from mean and std dev all the way to neural networks and model selection.

---

## Structure

```
statistics/
├── problem_notebooks/  ← Problem-driven EDA→prediction notebooks (recommended start)
├── notebooks/          ← Weekly concept reference notebooks
└── reference/          ← Curriculum guides, exercises, and legacy docs
    └── legacy/         ← Original teaching materials (attempt1)
```

---

## problem_notebooks/ — Problem-Driven Notebooks (Recommended Start)

Each notebook takes a real problem and walks through it completely: tabular data → column distributions → feature-target relationships → correlation heatmaps → feature engineering → prediction.

| Notebook | Problem | Type |
|---|---|---|
| `Problem01_Titanic_Survival.ipynb` | Who survived the Titanic? | Classification |
| `Problem02_House_Price_Prediction.ipynb` | What drives California house prices? | Regression |
| `Problem03_Student_Performance.ipynb` | Which students will struggle? | Both |
| `Problem04_Heart_Disease_Prediction.ipynb` | Who is at risk of heart disease? | Classification |

---

## notebooks/ — Weekly Concept Reference Notebooks

Concept-focused notebooks organized by week. Use as a reference alongside the problem notebooks.

| Notebook | Topics |
|---|---|
| `Week01_Statistics_Foundation.ipynb` | Mean, std dev, z-score, normalization |
| `Week02_Understanding_The_Problem.ipynb` | Statistics vs prediction, error, supervised learning |
| `Week03_Linear_Model.ipynb` | ŷ = w×z + b, predictions, weight interpretation |
| `Week04_05_Gradient_Descent.ipynb` | Gradient formula, error landscape, weight updates |
| `Week06_07_Multiple_Weights_Learning_Rate.ipynb` | Multiple weights, simultaneous updates, learning rate |
| `Week08_Complete_Training_Loop.ipynb` | Full predict→error→gradient→update loop |
| `Week09_Why_Normalization_Matters.ipynb` | How scale mismatch breaks learning |
| `Week10_11_Complex_Models.ipynb` | Polynomial features, decision trees, bias-variance |
| `Week12_Neural_Networks.ipynb` | Activations, hidden layers, backpropagation |
| `Week13_14_Practical_Mastery.ipynb` | Overfitting, regularization, model selection, capstone |
| `ML_Learning_Journey.ipynb` | Full course overview in one notebook |

---

## reference/ — Curriculum Guides

| File | Purpose |
|---|---|
| `LEARNING_ROADMAP_QUICK_REFERENCE.md` | Week-by-week roadmap with checkpoints |
| `ORGANIZED_TEACHING_CURRICULUM.md` | Full teaching curriculum |
| `HANDS_ON_PRACTICE_EXERCISES.md` | Exercises with solutions (organized by week) |
| `MASTER_INDEX_GUIDE.md` | Index of all concepts and where to find them |
| `WHY_STATISTICS_IS_NECESSARY.md` | Motivation for the statistics-first approach |
| `COMPLETE_COURSE_SUMMARY.txt` | Full course summary |
| `READING_ORDER.md` | Recommended reading order |

---

## External Resources

- https://github.com/thomasnield/oreilly_vibing_with_statistics
- https://distribution-explorer.github.io/index.html
- https://github.com/gedeck/practical-statistics-for-data-scientists/tree/master
- https://www.jmp.com/en/statistics-knowledge-portal
