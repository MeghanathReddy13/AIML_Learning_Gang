# AIML Learning Gang

A collaborative learning repository for AI and Machine Learning fundamentals.

---

## Repository Structure

```
AIML_Learning_Gang/
├── AIML_Learning_Roadmap/   ← Course roadmap documents (.docx)
├── ML-foundations/          ← ML foundations resources
└── statistics/              ← 14-week statistics → ML course
    ├── notebooks/           ← Weekly Jupyter notebooks (main content)
    └── reference/           ← Curriculum guides and exercises
```

---

## Getting Started

The primary learning content lives in **`statistics/`**.

1. Read `statistics/README.md` for an overview of the course
2. Open `statistics/notebooks/Week01_Statistics_Foundation.ipynb` to begin
3. Work through notebooks in week order
4. Use `statistics/reference/` docs alongside for deeper context

### Prerequisites

```bash
pip install numpy matplotlib scikit-learn jupyter
```

Then launch:

```bash
jupyter notebook statistics/notebooks/
```

---

## Course Overview

| Phase | Weeks | Topic |
|---|---|---|
| Foundation | 1–2 | Statistics: mean, std dev, z-score, normalization |
| First Model | 3 | Linear model: ŷ = w×z + b |
| Learning | 4–8 | Gradient descent, weight updates, training loop |
| Understanding | 9 | Why normalization enables learning |
| Complexity | 10–12 | Polynomial, decision trees, neural networks |
| Mastery | 13–14 | Overfitting, regularization, model selection |
