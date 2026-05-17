# Hands-On Practice Exercises
## Organized by Week with Solutions

---

## WEEK 1: STATISTICS FOUNDATION
### Topic: Mean, Standard Deviation, Z-Scores

---

## Exercise 1.1: Computing Mean

**Problem:**
A teacher records student test scores: [65, 78, 82, 71, 88]

**Task:** Calculate the mean score.

**Step-by-step:**
```
Step 1: Add all values
65 + 78 + 82 + 71 + 88 = 384

Step 2: Count values
5 scores

Step 3: Divide
mean = 384 / 5 = 76.8
```

**Answer:** Mean = 76.8

**Concept:** The mean is the center. Most scores are around 76.8.

---

## Exercise 1.2: Computing Standard Deviation

**Problem:**
Scores: [65, 78, 82, 71, 88]
Mean: 76.8 (from Exercise 1.1)

**Task:** Calculate standard deviation.

**Step-by-step:**
```
Step 1: Subtract mean from each
65 - 76.8 = -11.8
78 - 76.8 = 1.2
82 - 76.8 = 5.2
71 - 76.8 = -5.8
88 - 76.8 = 11.2

Step 2: Square each deviation
(-11.8)² = 139.24
(1.2)² = 1.44
(5.2)² = 27.04
(-5.8)² = 33.64
(11.2)² = 125.44

Step 3: Average the squares (variance)
(139.24 + 1.44 + 27.04 + 33.64 + 125.44) / 5
= 326.8 / 5
= 65.36

Step 4: Take square root
√65.36 ≈ 8.08
```

**Answer:** Standard Deviation ≈ 8.08

**Concept:** Typical distance from mean is 8.08. Scores are spread about ±8 points around 76.8.

---

## Exercise 1.3: Computing Z-Scores

**Problem:**
Scores: [65, 78, 82, 71, 88]
Mean: 76.8
Std Dev: 8.08

**Task:** Convert each score to z-score.

**Step-by-step:**
```
z = (x - mean) / std

For score 65:
z = (65 - 76.8) / 8.08 = -11.8 / 8.08 ≈ -1.46

For score 78:
z = (78 - 76.8) / 8.08 = 1.2 / 8.08 ≈ 0.15

For score 82:
z = (82 - 76.8) / 8.08 = 5.2 / 8.08 ≈ 0.64

For score 71:
z = (71 - 76.8) / 8.08 = -5.8 / 8.08 ≈ -0.72

For score 88:
z = (88 - 76.8) / 8.08 = 11.2 / 8.08 ≈ 1.39
```

**Answer:** Z-scores = [-1.46, 0.15, 0.64, -0.72, 1.39]

**Concept:** Now all on same scale [-3 to +3]. 65 is 1.46 std devs below mean. 88 is 1.39 std devs above.

---

## Exercise 1.4: Why Normalization Matters

**Problem:**
Two datasets:
- Dataset A: Ages [20, 30, 40, 50, 60] (mean=40, std≈15.81)
- Dataset B: Incomes [$30k, $50k, $70k, $90k, $110k] (mean=$70k, std≈31.62k)

**Task:** Show what happens without normalization.

**Solution:**
```
WITHOUT normalization:
Age range: 20 to 60 (40 units)
Income range: $30k to $110k ($80,000 units!)

Income numbers are 2000× LARGER!

Gradient for age: Could be 0.5
Gradient for income: Could be 1000

Income gradient dominates! Age is ignored!

WITH normalization (z-scores):
Both ages and incomes transform to [-2 to +2]

Same scale!
Both features matter equally
Learning is balanced!
```

**Concept:** Normalization prevents large-scale features from dominating.

---

## WEEK 2: UNDERSTANDING THE PROBLEM

---

## Exercise 2.1: Statistics vs Prediction

**Problem:**
Loan approval data:
- 80% of customers aged 40+ were approved
- 20% of customers aged under 40 were approved

New customer: Age 35

**Task:** Can you approve or reject based on statistics alone?

**Solution:**
```
NO!

Statistics tell us:
- Younger people are more likely to be rejected
- This customer is young

But:
- 20% of young people ARE approved
- Maybe this specific person should be approved
- Depends on OTHER factors (income, credit score)
- Statistics can't handle individual decisions

We need a MODEL that:
- Uses ALL features (age, income, credit score)
- Predicts probability for THIS person
- Gives specific yes/no decision
```

**Concept:** Statistics describe trends. Models make individual predictions.

---

## Exercise 2.2: Understanding Error

**Problem:**
Model predictions: [0.2, 0.8, 0.6, 0.4, 0.9]
Actual outcomes: [0, 1, 1, 0, 1]

**Task:** Calculate total error.

**Solution:**
```
Error for each: (prediction - actual)²

(0.2 - 0)² = 0.04
(0.8 - 1)² = 0.04
(0.6 - 1)² = 0.16
(0.4 - 0)² = 0.16
(0.9 - 1)² = 0.01

Total error: 0.04 + 0.04 + 0.16 + 0.16 + 0.01 = 0.41
Average error: 0.41 / 5 = 0.082
```

**Concept:** Smaller error = better predictions. Goal is to minimize this.

---

## WEEK 3: LINEAR MODEL

---

## Exercise 3.1: Making Predictions with Linear Model

**Problem:**
Model: ŷ = 0.3×z_age + 0.4×z_income + 0.2×z_credit + 0.1

New customer (standardized features):
- z_age = 0.5
- z_income = -0.3
- z_credit = 0.8

**Task:** Make prediction.

**Solution:**
```
ŷ = 0.3×(0.5) + 0.4×(-0.3) + 0.2×(0.8) + 0.1
  = 0.15 - 0.12 + 0.16 + 0.1
  = 0.29

Prediction: 0.29 (29% approval probability)
Decision: REJECT (below 50%)
```

**Concept:** Apply weights to features, sum, add bias. Get prediction.

---

## Exercise 3.2: Interpreting Weights

**Problem:**
Learned weights:
- w_age = 0.4
- w_income = 0.5
- w_credit = 0.6

**Task:** Interpret what these weights mean.

**Solution:**
```
w_age = 0.4:
  "Each unit increase in standardized age
   increases approval by 0.4"
  Positive: Older = more likely approved
  Medium magnitude: Age moderately important

w_income = 0.5:
  "Each unit increase in standardized income
   increases approval by 0.5"
  Positive: Richer = more likely approved
  Medium-high magnitude: Income very important

w_credit = 0.6:
  "Each unit increase in standardized credit score
   increases approval by 0.6"
  Positive: Better score = more likely approved
  Highest magnitude: Credit score MOST important
```

**Concept:** Weights show importance and direction of features.

---

## WEEK 4-5: GRADIENT DESCENT

---

## Exercise 4.1: Computing Gradient

**Problem:**
- Prediction: ŷ = 0.15
- Actual: y = 1
- Feature: z = 1.5

**Task:** Compute gradient ∂L/∂w = 2(ŷ - y) × z

**Solution:**
```
Step 1: Prediction error
ŷ - y = 0.15 - 1 = -0.85

Step 2: Apply formula
∂L/∂w = 2 × (-0.85) × 1.5
      = -1.7 × 1.5
      = -2.55

Step 3: Interpret
Negative gradient: Weight is too small
Magnitude 2.55: Large room for improvement
Action: INCREASE weight
```

**Answer:** Gradient = -2.55

---

## Exercise 4.2: Updating Weight

**Problem:**
- Current weight: w = 0.1
- Gradient: ∂L/∂w = -2.55
- Learning rate: lr = 0.1

**Task:** Compute new weight w_new = w - lr × gradient

**Solution:**
```
w_new = 0.1 - 0.1 × (-2.55)
      = 0.1 - (-0.255)
      = 0.1 + 0.255
      = 0.355

Weight increased from 0.1 to 0.355
```

**Answer:** w_new = 0.355

---

## Exercise 4.3: Verify Error Decreased

**Problem:**
- Old weight: w = 0.1
- New weight: w = 0.355
- Feature: z = 1.5
- Actual: y = 1

**Task:** Compare errors before and after.

**Solution:**
```
OLD ERROR:
ŷ_old = 0.1 × 1.5 = 0.15
error_old = (0.15 - 1)² = 0.7225

NEW ERROR:
ŷ_new = 0.355 × 1.5 = 0.5325
error_new = (0.5325 - 1)² = 0.2190

IMPROVEMENT:
Old: 0.7225
New: 0.2190
Reduction: 69.7% decrease! ✓

The update worked!
```

---

## Exercise 4.4: Multiple Iterations by Hand

**Problem:**
Starting with w = 0.1, iterate 3 times.
- Same data: z = 1.5, y = 1, lr = 0.1

**Task:** Show learning over iterations.

**Solution:**
```
ITERATION 1:
ŷ = 0.1 × 1.5 = 0.15
error = 0.7225
∂L/∂w = -2.55
w_new = 0.355

ITERATION 2:
ŷ = 0.355 × 1.5 = 0.5325
error = 0.2190
∂L/∂w = 2(-0.4675) × 1.5 = -1.4025
w_new = 0.355 - 0.1×(-1.4025) = 0.4953

ITERATION 3:
ŷ = 0.4953 × 1.5 = 0.7430
error = 0.0661
∂L/∂w = 2(-0.257) × 1.5 = -0.771
w_new = 0.4953 - 0.1×(-0.771) = 0.5724

PATTERN:
Iteration 1: w=0.355, error=0.7225
Iteration 2: w=0.495, error=0.2190
Iteration 3: w=0.572, error=0.0661

Error DECREASES each iteration ✓
Weight INCREASES (toward optimal) ✓
Gradient SHRINKS (getting closer) ✓
```

---

## WEEK 6-7: MULTIPLE WEIGHTS

---

## Exercise 5.1: Multiple Weights, One Data Point

**Problem:**
Model: ŷ = w₁×z₁ + w₂×z₂ + b

Data point:
- z₁ = 1.5, z₂ = 0.5
- y = 1
- w₁ = 0.1, w₂ = 0.1, b = 0
- lr = 0.1

**Task:** Compute gradients and update both weights.

**Solution:**
```
Step 1: Predict
ŷ = 0.1×1.5 + 0.1×0.5 + 0 = 0.2

Step 2: Error
ŷ - y = 0.2 - 1 = -0.8

Step 3: Gradients (independent)
∂L/∂w₁ = 2(-0.8) × 1.5 = -2.4
∂L/∂w₂ = 2(-0.8) × 0.5 = -0.8

Step 4: Updates (simultaneous)
w₁_new = 0.1 - 0.1×(-2.4) = 0.34
w₂_new = 0.1 - 0.1×(-0.8) = 0.18

KEY: Same error, but different gradients!
w₁ has larger feature → larger gradient → bigger update
w₂ has smaller feature → smaller gradient → smaller update
```

---

## Exercise 5.2: Learning Rate Effects

**Problem:**
Gradient: -2.55
Current weight: w = 0.1

**Task:** Show effect of different learning rates.

**Solution:**
```
Learning Rate = 0.01 (very small):
w_new = 0.1 - 0.01×(-2.55) = 0.1255
Change: +0.0255 (tiny step)
Convergence: Very slow (many iterations)

Learning Rate = 0.1 (medium):
w_new = 0.1 - 0.1×(-2.55) = 0.355
Change: +0.255 (good step)
Convergence: Balanced, reasonable

Learning Rate = 0.5 (large):
w_new = 0.1 - 0.5×(-2.55) = 1.375
Change: +1.275 (big step)
Convergence: Fast but risky, might overshoot

Learning Rate = 1.0 (very large):
w_new = 0.1 - 1.0×(-2.55) = 2.65
Change: +2.55 (huge step)
Convergence: Likely diverges, oscillates

CONCLUSION:
0.01 too small (slow)
0.1 just right (balanced)
0.5 risky (overshoot)
1.0 too large (diverges)
```

---

## WEEK 9-10: COMPLEX MODELS

---

## Exercise 6.1: Polynomial Features

**Problem:**
Feature: z = 1.0 (standardized)

Create polynomial features: z, z², z³

**Task:** Show how polynomial adds flexibility.

**Solution:**
```
Simple linear:
ŷ = w₁ × z = w₁ × 1.0

With polynomial:
ŷ = w₁×z + w₂×z² + w₃×z³
  = w₁×1.0 + w₂×1.0 + w₃×1.0

Example with weights:
Linear: ŷ = 0.5 × 1.0 = 0.5

Polynomial: ŷ = 0.5×1.0 + (-0.2)×(1.0)² + 0.1×(1.0)³
           = 0.5 - 0.2 + 0.1
           = 0.4

Different predictions!
Polynomial can fit curves.
```

---

## Exercise 6.2: Simple vs Complex Model

**Problem:**
Training data: 100 points
- Simple linear model: 2 parameters
- Complex tree model: 100 parameters

**Task:** Predict training vs test error pattern.

**Solution:**
```
TRAINING ERROR:
Simple (2 params): Medium error
  - Can't fit complex patterns
  - Some underfitting

Complex (100 params): Very low error
  - Can fit training data perfectly
  - Risk of overfitting

PREDICTION:
Linear will generalize better (low test error)
Tree will overfit (high test error)

But if we have tons of diverse data:
Complex model might generalize well too!
```

---

## WEEK 11-12: NEURAL NETWORKS

---

## Exercise 7.1: Hidden Layers

**Problem:**
Linear model: 3 features → 1 output

Add one hidden layer with 3 hidden units

**Task:** Describe learned features.

**Solution:**
```
INPUT: z_age, z_income, z_credit (3 features)

HIDDEN LAYER: 3 units
h₁ = ReLU(w₁×z_age + w₂×z_income + w₃×z_credit + b₁)
h₂ = ReLU(w₄×z_age + w₅×z_income + w₆×z_credit + b₂)
h₃ = ReLU(w₇×z_age + w₈×z_income + w₉×z_credit + b₃)

h₁, h₂, h₃ are LEARNED FEATURES
(Like z_age² that we manually created)
Network learns what features matter!

OUTPUT: Linear combination of h₁, h₂, h₃
ŷ = w₁₀×h₁ + w₁₁×h₂ + w₁₂×h₃ + b₄

Total parameters: 9 (hidden) + 3 (output) + 4 (biases) = 16
Compared to linear's 4!

More parameters = More flexibility = Can fit complex patterns
```

---

## Exercise 7.2: Activation Functions

**Problem:**
Value before activation: z = 0.5
Value before activation: z = -0.5

**Task:** Apply ReLU activation.

**Solution:**
```
ReLU(x) = max(0, x)

ReLU(0.5) = 0.5 (positive, passes through)
ReLU(-0.5) = 0 (negative, blocked)

Effect:
- Positive values pass through
- Negative values become 0
- Creates non-linearity
- Multiple layers can learn complex patterns

Without ReLU:
Stacking linear layers = still linear
No benefit to depth

With ReLU:
Each layer can learn non-linear transformation
Depth adds power!
```

---

## WEEK 13-14: PRACTICAL MASTERY

---

## Exercise 8.1: Train-Test Split

**Problem:**
Dataset: 100 customers with features and approval outcomes

**Task:** Proper train-test split and evaluation.

**Solution:**
```
WRONG approach:
1. Train model on all 100
2. Evaluate on same 100
3. Get 95% accuracy
4. Declare victory!
PROBLEM: Will fail on new data!

RIGHT approach:
1. Split: 80 train, 20 test
2. Train model on 80
3. Evaluate on 20 (never seen before)
4. Training accuracy: 92%
5. Test accuracy: 87%
6. If different, there's overfitting!

If test accuracy is good:
Model generalizes ✓
Safe to deploy!

If test accuracy is poor:
Model is overfitting
Need simpler model or more data
```

---

## Exercise 8.2: Detecting Overfitting

**Problem:**
Model results:
- Training error: 0.01 (very low)
- Test error: 0.35 (very high)

**Task:** Identify problem and solution.

**Solution:**
```
DIAGNOSIS: SEVERE OVERFITTING

The model learned training data too well,
but failed to learn the pattern.

EVIDENCE:
Training: 0.01 (nearly perfect)
Test: 0.35 (much worse)
Gap: 0.34 (huge difference!)

SOLUTIONS:
1. Use simpler model
   - Fewer parameters
   - Less flexibility

2. Add regularization
   - Penalize large weights
   - Force simpler solution

3. Get more training data
   - More diverse examples
   - Harder to memorize noise

4. Reduce feature count
   - Remove unimportant features
   - Fewer dimensions to overfit on
```

---

## Exercise 8.3: Model Comparison

**Problem:**
Three models on same data:

Model A (Linear):
- Training: 85%
- Testing: 83%

Model B (Tree):
- Training: 95%
- Testing: 78%

Model C (Neural Net):
- Training: 98%
- Testing: 82%

**Task:** Choose best model.

**Solution:**
```
ANALYSIS:

Model A (Linear):
✓ Good generalization (85% → 83%, small gap)
✓ Stable, interpretable
✗ Underfits (medium test accuracy)

Model B (Tree):
✗ Overfits (95% → 78%, large gap)
✗ High test error

Model C (Neural Net):
✗ Severe overfitting (98% → 82%, huge gap)
✗ Most overfitting of all

RECOMMENDATION: Model A

Reasons:
- Best test accuracy (83%)
- Most stable (smallest gap)
- Generalizes best
- Likely best on future data

Others fit training better
but fail on new data!

Conclusion:
Don't choose by training accuracy.
Choose by test accuracy and generalization!
```

---

## CAPSTONE PROJECT TEMPLATE

### Real-World Data

Use any dataset. Here's a framework:

```
1. DATA EXPLORATION
   - Load data
   - Calculate mean, std for all features
   - Visualize distributions
   
2. PREPROCESSING
   - Handle missing values
   - Normalize all features (z-scores!)
   - Split train/test (80/20)

3. LINEAR BASELINE
   - Train simple linear model
   - Evaluate on test
   - Interpret weights

4. IMPROVED MODELS
   - Try polynomial features
   - Try decision tree
   - Try neural network

5. COMPARISON
   - Compare training errors
   - Compare test errors
   - Identify overfitting
   
6. FINAL CHOICE
   - Choose best model by test error
   - Report performance
   - Explain choice

7. INSIGHTS
   - What did weights reveal?
   - What patterns were found?
   - How would you improve further?
```

---

## ANSWER KEY SUMMARY

| Exercise | Answer | Key Concept |
|----------|--------|-------------|
| 1.1 | Mean = 76.8 | Central tendency |
| 1.2 | Std = 8.08 | Spread measurement |
| 1.3 | Z = [-1.46, 0.15, ...] | Standardization |
| 2.1 | No, need model | Prediction needs model |
| 2.2 | Error = 0.082 | Smaller error better |
| 3.1 | ŷ = 0.29 | Applying weights |
| 3.2 | w_credit most important | Weight interpretation |
| 4.1 | ∂L/∂w = -2.55 | Gradient computation |
| 4.2 | w_new = 0.355 | Weight update |
| 4.3 | Error decreased 69.7% | Update works! |
| 4.4 | Errors: 0.72 → 0.22 → 0.07 | Convergence pattern |
| 5.1 | w₁_new = 0.34, w₂_new = 0.18 | Multiple weights |
| 5.2 | 0.1 best, 0.01 too slow, 1.0 too large | Learning rate matters |
| 6.1 | Polynomial gives flexibility | Model complexity |
| 6.2 | Linear better (generalizes) | Complexity tradeoff |
| 7.1 | Hidden layer = 16 params | Automatic features |
| 7.2 | ReLU(0.5)=0.5, ReLU(-0.5)=0 | Activation functions |
| 8.1 | Test error tells truth | Proper evaluation |
| 8.2 | Use simpler model | Overfitting solutions |
| 8.3 | Model A (generalization) | Choosing wisely |

---

**These exercises build understanding progressively.
Do them by hand first.
Then code them.
Then understand them deeply.**
