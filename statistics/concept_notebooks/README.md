# Concept Notebooks

These notebooks isolate core ideas that students usually need before or alongside full problem notebooks.

## Included

- `Feature_Transformation_and_Weight_Learning.ipynb`
  - Starts from a small synthetic dataset
  - Examines feature distributions
  - Applies statistical transformations
  - Standardizes features
  - Trains linear models before and after transformation
  - Interprets learned weights

- `Observation_Level_Feature_Contribution.ipynb`
  - Trains a linear model and a decision tree on the same dataset
  - Breaks one prediction into per-feature `weight × value` terms
  - Shows the exact tree path for one observation
  - Compares how the two model families explain a prediction differently

Use this folder when the goal is to teach *why* preprocessing is necessary before a machine can learn useful rules from data.
