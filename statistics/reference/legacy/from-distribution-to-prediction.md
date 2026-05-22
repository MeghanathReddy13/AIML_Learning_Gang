# How to Infer Outcomes from Feature Distributions
## From Sample Distributions → Individual Predictions

The critical question: **Given what we learned about how features distribute, how do we predict outcomes for a specific new observation?**

---

## The Foundation: What We Learned From The Sample

### Step 1: Calculate Univariate Distributions (From Sample Data)

From our 10-student sample, we learned these distributions:

```
FEATURE DISTRIBUTIONS (What's "typical" for each feature)
═════════════════════════════════════════════════════════════

HOURS STUDIED Distribution:
  Values: 6, 3, 5, 4, 7, 2, 6, 4, 5, 3
  
  Mean (μ): 4.5 hours
    └─ Typical central value
  
  Standard Deviation (σ): 1.6 hours
    └─ Typical spread around the mean
    └─ Most students study between 3-6 hours (4.5 ± 1.6)
  
  Range: 2 to 7 hours
    └─ Minimum observed: 2
    └─ Maximum observed: 7
  
  Shape: Roughly symmetric (normal-ish)
    └─ No extreme skew


PRIOR GPA Distribution:
  Values: 3.8, 3.2, 3.5, 2.9, 3.9, 2.8, 3.7, 3.3, 3.6, 3.0
  
  Mean (μ): 3.4
  Standard Deviation (σ): 0.35
    └─ Most students between 3.05-3.75 (3.4 ± 0.35)
  
  Range: 2.8 to 3.9
  Shape: Fairly symmetric


SLEEP HOURS Distribution:
  Values: 7, 5, 6, 5, 8, 4, 7, 6, 7, 5
  
  Mean (μ): 6.1 hours
  Standard Deviation (σ): 1.2 hours
    └─ Most students between 4.9-7.3 hours
  
  Range: 4 to 8 hours
  Shape: Fairly symmetric, maybe slightly right-skewed


ATTENDANCE % Distribution:
  Values: 95, 80, 90, 75, 98, 70, 92, 85, 88, 78
  
  Mean (μ): 85%
  Standard Deviation (σ): 8.5%
    └─ Most students between 76.5%-93.5%
  
  Range: 70% to 98%
  Shape: Fairly symmetric


TEST SCORE Distribution (The OUTCOME we want to predict):
  Values: 92, 78, 85, 72, 94, 68, 90, 80, 88, 75
  
  Mean (μ): 81 points
  Standard Deviation (σ): 7.5 points
    └─ Most scores between 73.5-88.5
  
  Range: 68 to 94 points
  Shape: Fairly symmetric
```

### Step 2: Learn Relationships Between Features and Outcome

Beyond univariate distributions, we learned HOW features relate to test scores:

```
CORRELATIONS (How features connect to outcome)
═════════════════════════════════════════════════════════════

HOURS STUDIED ↔ TEST SCORE
  Correlation: r = 0.92 (very strong positive)
  
  What this means:
  When Hours Studied increases    →  Test Score tends to increase
  When Hours Studied decreases    →  Test Score tends to decrease
  
  Mathematical relationship (approximate):
  For every 1 additional hour studied → +3 points on test
  For every 1 fewer hour studied      → -3 points on test
  
  Examples from our sample:
  Frank: 2 hours → 68 points
  Bob:   3 hours → 78 points
  David: 4 hours → 72 points
  Carol: 5 hours → 85 points
  Alice: 6 hours → 92 points
  Emma:  7 hours → 94 points
  
  Pattern visible: As hours go up, scores generally go up


PRIOR GPA ↔ TEST SCORE
  Correlation: r = 0.89 (very strong positive)
  
  Mathematical relationship:
  For every 0.1 increase in GPA → +8-10 points on test
  
  Examples:
  Frank: 2.8 GPA → 68 points
  David: 2.9 GPA → 72 points
  Bob:   3.2 GPA → 78 points
  Carol: 3.5 GPA → 85 points
  Alice: 3.8 GPA → 92 points
  Emma:  3.9 GPA → 94 points


SLEEP HOURS ↔ TEST SCORE
  Correlation: r = 0.75 (strong positive)
  
  Mathematical relationship:
  For every 1 additional hour of sleep → +4-5 points on test
  
  Examples:
  Frank: 4 hours sleep → 68 points
  Bob:   5 hours sleep → 78 points
  David: 5 hours sleep → 72 points
  Carol: 6 hours sleep → 85 points
  Alice: 7 hours sleep → 92 points
  Emma:  8 hours sleep → 94 points


ATTENDANCE ↔ TEST SCORE
  Correlation: r = 0.91 (very strong positive)
  
  Mathematical relationship:
  For every 1% increase in attendance → +0.3-0.4 points on test
  
  Examples:
  Frank: 70% attendance  → 68 points
  David: 75% attendance  → 72 points
  Bob:   80% attendance  → 78 points
  Henry: 85% attendance  → 80 points
  Carol: 90% attendance  → 85 points
  Alice: 95% attendance  → 92 points
  Emma:  98% attendance  → 94 points
```

---

## The Inference Process: From Distribution to Prediction

### The Key Insight

```
WHAT WE KNOW FROM SAMPLE:
├─ Distribution of each feature (mean, std dev, range)
├─ How each feature relates to outcome (correlation)
└─ What test scores look like (outcome distribution)

NEW OBSERVATION ARRIVES:
├─ Kevin with features: [5 hrs, 3.5 GPA, 6 hrs sleep, 88% attend]
└─ Kevin's test score: UNKNOWN (this is what we want to predict)

INFERENCE PROCESS:
├─ Step 1: Compare Kevin's feature values to learned distributions
├─ Step 2: Understand Kevin's position relative to "typical"
├─ Step 3: Use learned relationships to predict outcome
└─ Step 4: Estimate Kevin's score

RESULT: Predicted score for Kevin
```

---

## Detailed Example: Predicting Kevin's Test Score

### Step 1: Kevin's Raw Features

```
Kevin's Observed Values:
┌──────────────────────────────────────────┐
│ Hours studied:      5 hours              │
│ Prior GPA:          3.5                  │
│ Sleep hours:        6 hours              │
│ Attendance %:       88%                  │
└──────────────────────────────────────────┘
```

### Step 2: Where Does Kevin Fall in Each Distribution?

**Compare each of Kevin's values to the learned distributions:**

```
HOURS STUDIED
Learned Distribution: μ = 4.5, σ = 1.6, Range = 2-7
Kevin's value: 5

Analysis:
  5 vs 4.5 = 0.5 hours ABOVE the mean
  0.5 / 1.6 = 0.31 standard deviations above
  
  Interpretation:
  "Kevin studies more than average"
  "But not by much - still within typical range"
  "Position: Slightly above typical"
  
Position in distribution:
  2 ─── 3 ─── 4 ─── 4.5 ─── 5 ─── 6 ─── 7
                    (mean)    ↑
                           Kevin
                           
Conclusion: Kevin is in the ABOVE-AVERAGE portion


PRIOR GPA
Learned Distribution: μ = 3.4, σ = 0.35, Range = 2.8-3.9
Kevin's value: 3.5

Analysis:
  3.5 vs 3.4 = 0.1 ABOVE the mean
  0.1 / 0.35 = 0.29 standard deviations above
  
  Interpretation:
  "Kevin's GPA is slightly above average"
  "Position: Slightly above typical"
  
Position in distribution:
  2.8 ── 3.0 ── 3.2 ── 3.4 ── 3.5 ── 3.7 ── 3.9
                      (mean)  ↑
                           Kevin
                           
Conclusion: Kevin is in the ABOVE-AVERAGE portion


SLEEP HOURS
Learned Distribution: μ = 6.1, σ = 1.2, Range = 4-8
Kevin's value: 6

Analysis:
  6 vs 6.1 = 0.1 BELOW the mean
  -0.1 / 1.2 = -0.08 standard deviations (essentially at mean)
  
  Interpretation:
  "Kevin's sleep is essentially at average"
  "Position: Typical/Normal"
  
Position in distribution:
  4 ─── 4.9 ─── 6 ── 6.1 ── 7.3 ─── 8
                ↑  (mean)
             Kevin (very close to mean)
             
Conclusion: Kevin is at the TYPICAL portion


ATTENDANCE %
Learned Distribution: μ = 85%, σ = 8.5%, Range = 70%-98%
Kevin's value: 88%

Analysis:
  88 vs 85 = 3% ABOVE the mean
  3 / 8.5 = 0.35 standard deviations above
  
  Interpretation:
  "Kevin attends more than average"
  "Position: Slightly above typical"
  
Position in distribution:
  70% ── 76.5% ── 85% ── 88% ── 93.5% ── 98%
        (mean)    ↑
              Kevin
              
Conclusion: Kevin is in the ABOVE-AVERAGE portion
```

### Step 3: Build Kevin's Predicted Score Using Learned Relationships

Now we use what we learned about how features relate to test scores:

```
METHOD 1: BASELINE + ADJUSTMENTS

Baseline (what we expect on average):
  Population average test score = 81 points
  └─ This is our starting point

Adjustment 1 - Hours Studied Effect:
  Kevin: 5 hours (vs mean 4.5)
  Difference: 5 - 4.5 = +0.5 hours
  Learned relationship: +3 points per hour
  Adjustment: 0.5 × 3 = +1.5 points
  
Adjustment 2 - Prior GPA Effect:
  Kevin: 3.5 (vs mean 3.4)
  Difference: 3.5 - 3.4 = +0.1
  Learned relationship: +10 points per 0.1 GPA
  Adjustment: 0.1 × 10 = +1.0 point
  
Adjustment 3 - Sleep Hours Effect:
  Kevin: 6 hours (vs mean 6.1)
  Difference: 6 - 6.1 = -0.1 hours
  Learned relationship: +4 points per hour
  Adjustment: -0.1 × 4 = -0.4 points
  
Adjustment 4 - Attendance Effect:
  Kevin: 88% (vs mean 85%)
  Difference: 88 - 85 = +3%
  Learned relationship: +0.3 points per 1%
  Adjustment: 3 × 0.3 = +0.9 points

─────────────────────────────────────────
PREDICTED SCORE:
81 (baseline) + 1.5 + 1.0 - 0.4 + 0.9 = 84.0 points
─────────────────────────────────────────
```

### Step 4: Interpret the Prediction

```
KEVIN'S PREDICTED SCORE: 84 points

What this means:

1. COMPARED TO AVERAGE
   Kevin (84) is 3 points above average (81)
   84 = 81 + 3
   
2. COMPARED TO DISTRIBUTION
   Test scores have μ = 81, σ = 7.5
   Kevin's predicted 84 is within the typical range (73.5-88.5)
   Not extreme, just slightly above average
   
3. CONFIDENCE LEVEL
   Kevin's features are all close to average
   (mostly between 0.3 and 0.4 standard deviations from mean)
   → Moderate confidence in prediction
   
   If Kevin had extreme values, we'd be less confident
   (things might not follow the pattern)
   
4. PREDICTION RANGE
   Point estimate: 84 points
   Likely range: 80-88 points (±4)
   → Kevin probably scores somewhere in this band
```

---

## Different Observation Types and Their Predictions

### Observation 1: High Achiever (Emma)

**Emma's features:**
```
Hours: 7 (vs mean 4.5) = +2.5 above
GPA: 3.9 (vs mean 3.4) = +0.5 above
Sleep: 8 (vs mean 6.1) = +1.9 above
Attendance: 98% (vs mean 85%) = +13% above
```

**Prediction calculation:**
```
Baseline: 81
+ Hours (2.5 × 3):        +7.5
+ GPA (0.5 × 10):         +5.0
+ Sleep (1.9 × 4):        +7.6
+ Attendance (13 × 0.3):  +3.9
─────────────────────────────
Predicted: 81 + 7.5 + 5 + 7.6 + 3.9 = 104.9
(capped at 100, so ~95-100)

Actual: 94 ✓ (prediction was accurate)
```

### Observation 2: Average Student (Henry)

**Henry's features:**
```
Hours: 4 (vs mean 4.5) = -0.5 below
GPA: 3.3 (vs mean 3.4) = -0.1 below
Sleep: 6 (vs mean 6.1) = -0.1 below
Attendance: 85% (vs mean 85%) = 0% (at mean)
```

**Prediction calculation:**
```
Baseline: 81
+ Hours (-0.5 × 3):       -1.5
+ GPA (-0.1 × 10):        -1.0
+ Sleep (-0.1 × 4):       -0.4
+ Attendance (0 × 0.3):    0
─────────────────────────────
Predicted: 81 - 1.5 - 1.0 - 0.4 = 78.1

Actual: 80 ✓ (close, within typical variation)
```

### Observation 3: Struggling Student (Frank)

**Frank's features:**
```
Hours: 2 (vs mean 4.5) = -2.5 below
GPA: 2.8 (vs mean 3.4) = -0.6 below
Sleep: 4 (vs mean 6.1) = -2.1 below
Attendance: 70% (vs mean 85%) = -15% below
```

**Prediction calculation:**
```
Baseline: 81
+ Hours (-2.5 × 3):       -7.5
+ GPA (-0.6 × 10):        -6.0
+ Sleep (-2.1 × 4):       -8.4
+ Attendance (-15 × 0.3):  -4.5
─────────────────────────────
Predicted: 81 - 7.5 - 6.0 - 8.4 - 4.5 = 54.6

Actual: 68 ✓ (prediction was low, actual was higher)
Note: Shows prediction isn't perfect, but captures direction
```

---

## The Mathematical Framework: Formal Inference

### Notation and Formula

```
Learned from sample:
├─ μⱼ = mean of feature j
├─ σⱼ = standard deviation of feature j
└─ βⱼ = relationship strength (how much feature j affects outcome)

For new observation i with features x₁ᵢ, x₂ᵢ, x₃ᵢ, x₄ᵢ:

PREDICTED OUTCOME:
ŷᵢ = μ_outcome + β₁(x₁ᵢ - μ₁) + β₂(x₂ᵢ - μ₂) + β₃(x₃ᵢ - μ₃) + β₄(x₄ᵢ - μ₄)

Where:
  ŷᵢ = predicted test score for observation i
  μ_outcome = mean test score from sample (81)
  βⱼ = how much 1 unit of feature j affects outcome
  (x₁ᵢ - μ₁) = how much observation i's feature 1 differs from sample mean
```

### Applied to Kevin:

```
Kevin's features: [5, 3.5, 6, 88]
Learned means:    [4.5, 3.4, 6.1, 85]
Learned betas:    [3, 10, 4, 0.3]

ŷ_Kevin = 81 + 3(5-4.5) + 10(3.5-3.4) + 4(6-6.1) + 0.3(88-85)
        = 81 + 3(0.5) + 10(0.1) + 4(-0.1) + 0.3(3)
        = 81 + 1.5 + 1.0 - 0.4 + 0.9
        = 84.0

Predicted score for Kevin: 84 points
```

---

## Why This Inference Works: The Underlying Logic

### Principle 1: Learned Distributions Represent Population Patterns

```
SAMPLE (what we observed)          POPULATION (what we infer)
┌──────────────────────────────┐   ┌──────────────────────────────┐
│ 10 students with:            │   │ All students with:           │
│ Mean hours: 4.5              │→  │ Mean hours: ~4.5 (estimated) │
│ Correlation hrs↔score: 0.92  │   │ Correlation: ~0.92 (likely)  │
│                              │   │                              │
│ "This is what we measured"   │   │ "This is probably true for   │
│                              │   │  all students"               │
└──────────────────────────────┘   └──────────────────────────────┘
```

### Principle 2: Relationships Learned in Sample Apply to New Cases

```
FROM SAMPLE, WE LEARNED:
"When study hours increase by 1, test scores increase by ~3 points"

APPLYING TO NEW STUDENT:
Kevin studies 0.5 hours MORE than average
→ We expect Kevin scores 0.5 × 3 = 1.5 points MORE than average
→ Predicted: 81 + 1.5 = 82.5

This is a reasonable inference IF:
✓ Kevin is similar to students in our sample
✓ The relationship remains consistent
✓ No major unmeasured factors affect Kevin
```

### Principle 3: Multiple Features Provide Better Inference

```
SINGLE FEATURE INFERENCE:
"Kevin studies 5 hours (above average)"
→ Predict: slightly above average score
→ Estimate: 82 points

MULTIPLE FEATURE INFERENCE:
"Kevin studies 5 hours (above avg)
 AND has 3.5 GPA (above avg)
 AND sleeps 6 hours (about avg)
 AND attends 88% (above avg)"
→ All features consistent in being above/average
→ Pattern: Above average across board
→ Better estimate: 84 points

Multiple features reduce uncertainty and improve accuracy
```

---

## Confidence in Inference: When to Trust the Prediction

### Factor 1: How Extreme Are Kevin's Values?

```
KEVIN'S POSITION IN DISTRIBUTIONS:

Hours: 5 (in sample: 2-7)         Position: Middle range ✓
GPA: 3.5 (in sample: 2.8-3.9)     Position: Middle range ✓
Sleep: 6 (in sample: 4-8)         Position: Middle range ✓
Attendance: 88% (in sample: 70-98) Position: Middle range ✓

CONFIDENCE: HIGH
├─ Kevin's values are typical (not extreme)
├─ We have examples similar to Kevin in our sample
└─ Relationships should apply well

────────────────────────────────────

HYPOTHETICAL EXTREME STUDENT (Xavier):
Hours: 10 (in sample: 2-7)        Position: BEYOND range ✗
GPA: 4.2 (in sample: 2.8-3.9)     Position: BEYOND range ✗
Sleep: 2 (in sample: 4-8)         Position: BEYOND range ✗
Attendance: 100% (in sample: 70-98) Position: Near high end

CONFIDENCE: LOW
├─ Xavier has extreme values we haven't seen
├─ Relationships might not apply (might not be linear)
└─ Prediction would be very uncertain
```

### Factor 2: Consistency of the Relationships

```
KEVIN'S INFERENCE:
All adjustments point in same direction (mostly positive)
Hours: +1.5 (positive)
GPA: +1.0 (positive)
Sleep: -0.4 (small negative)
Attendance: +0.9 (positive)

CONSISTENCY: HIGH (mostly agree)
→ Prediction confidence: HIGHER

────────────────────────────────────

HYPOTHETICAL INCONSISTENT STUDENT (Yuki):
Hours: 2 (would predict LOW)
GPA: 3.9 (would predict HIGH)
Sleep: 8 (would predict HIGH)
Attendance: 70% (would predict LOW)

CONSISTENCY: LOW (contradictory signals)
→ Prediction confidence: LOWER
→ Cannot be sure which factors will dominate
```

### Factor 3: Sample Size and Distribution Uncertainty

```
Our sample: 10 students
├─ Reasonable but not huge
├─ Estimates have uncertainty
└─ Confidence interval is moderate

Prediction for Kevin: 84 ± ~4 points
├─ Central estimate: 84
├─ Likely range: 80-88
└─ We're fairly confident, but not certain

If we had 1000 students:
├─ Estimates would be much more reliable
├─ Confidence interval would be tighter
├─ Prediction: 84 ± ~1 point
└─ Much higher confidence
```

---

## Visualization: How Distribution Knowledge Becomes Prediction

### The Inference Pipeline

```
STEP 1: LEARN DISTRIBUTIONS
┌─────────────────────────────────────────┐
│ From 10-student sample, learn:          │
│ • Hours: μ=4.5, σ=1.6                  │
│ • GPA: μ=3.4, σ=0.35                   │
│ • Sleep: μ=6.1, σ=1.2                  │
│ • Attendance: μ=85%, σ=8.5%             │
│ • Score: μ=81, σ=7.5                   │
└─────────────────────────────────────────┘
                    ↓
STEP 2: LEARN RELATIONSHIPS
┌─────────────────────────────────────────┐
│ From patterns in sample, learn:         │
│ • Hours ↔ Score: +3 per hour           │
│ • GPA ↔ Score: +10 per 0.1             │
│ • Sleep ↔ Score: +4 per hour           │
│ • Attendance ↔ Score: +0.3 per 1%      │
└─────────────────────────────────────────┘
                    ↓
STEP 3: NEW OBSERVATION ARRIVES
┌─────────────────────────────────────────┐
│ Kevin: [5, 3.5, 6, 88]                 │
│ Score: UNKNOWN                          │
└─────────────────────────────────────────┘
                    ↓
STEP 4: COMPARE TO DISTRIBUTIONS
┌─────────────────────────────────────────┐
│ Hours: 5 vs μ=4.5 → +0.5 above         │
│ GPA: 3.5 vs μ=3.4 → +0.1 above         │
│ Sleep: 6 vs μ=6.1 → -0.1 below         │
│ Attend: 88 vs μ=85 → +3 above          │
└─────────────────────────────────────────┘
                    ↓
STEP 5: APPLY LEARNED RELATIONSHIPS
┌─────────────────────────────────────────┐
│ 81 + (+0.5×3) + (+0.1×10) + (-0.1×4)    │
│    + (+3×0.3)                           │
│                                         │
│ = 81 + 1.5 + 1.0 - 0.4 + 0.9            │
│ = 84.0                                  │
└─────────────────────────────────────────┘
                    ↓
STEP 6: PREDICTION FOR KEVIN
┌─────────────────────────────────────────┐
│ Predicted test score: 84 points         │
│ Confidence: Moderate-High               │
│ Likely range: 80-88                     │
└─────────────────────────────────────────┘
```

---

## The Three Questions at Each Stage

### Stage 1: Understanding Distributions
**Q: "What do the feature distributions tell us?"**
A: "Hours range 2-7 with mean 4.5, GPA ranges 2.8-3.9 with mean 3.4, etc."

### Stage 2: Understanding Relationships
**Q: "How do features relate to outcomes?"**
A: "When study hours increase by 1, scores increase by ~3 points."

### Stage 3: Making Predictions
**Q: "How do we predict for a specific new observation?"**
A: "Compare their values to learned distributions, use learned relationships to adjust from baseline."

---

## Common Mistakes in Inference

### Mistake 1: Using Only One Feature

```
WRONG: Kevin's GPA is 3.5, which is above average (3.4)
→ Predict: Slightly above average score (~82)

RIGHT: Kevin has:
- Hours 5: slightly above average → +1.5
- GPA 3.5: slightly above average → +1.0
- Sleep 6: about average → 0
- Attend 88%: slightly above average → +0.9
→ Predict: 84 (combining all signals)

Why it matters:
Multiple features reduce noise and improve accuracy
```

### Mistake 2: Trusting Predictions for Extreme Values

```
WRONG: Xavier studies 20 hours/day
"That's 4× above our sample, so predict 81 + (15.5×3) = 127 points"

RIGHT: "Xavier is far outside our sample range
Learning relationships don't apply to such extremes
Prediction would be very uncertain
Cannot reliably predict for Xavier"

Why it matters:
Relationships learned from one range don't necessarily apply elsewhere
Extrapolation beyond the sample is risky
```

### Mistake 3: Ignoring Correlation Strength

```
WRONG: All features have some relationship to score
"Let's use attendance (+0.3 per 1%) as heavily as hours (+3 per hour)"

RIGHT: Look at correlation strength:
Hours ↔ Score: r = 0.92 (very strong) → weight heavily
Attendance ↔ Score: r = 0.91 (very strong) → weight heavily
Sleep ↔ Score: r = 0.75 (moderate) → weight moderately

Why it matters:
Strong relationships deserve more weight in prediction
Weaker relationships contribute less reliable information
```

---

## Summary: The Inference Mechanism

```
┌──────────────────────────────────────────────────────────────┐
│                                                              │
│  LEARNED FROM SAMPLE (Distributions + Relationships)         │
│  ├─ Feature 1 Distribution (mean, std dev, range)          │
│  ├─ Feature 2 Distribution                                 │
│  ├─ Feature 3 Distribution                                 │
│  ├─ Feature 4 Distribution                                 │
│  ├─ How Feature 1 relates to Outcome (correlation)         │
│  ├─ How Feature 2 relates to Outcome                       │
│  ├─ How Feature 3 relates to Outcome                       │
│  └─ How Feature 4 relates to Outcome                       │
│                          ↓                                  │
│  NEW OBSERVATION (Kevin's values for 4 features)           │
│  ├─ Feature 1: 5                                           │
│  ├─ Feature 2: 3.5                                         │
│  ├─ Feature 3: 6                                           │
│  └─ Feature 4: 88                                          │
│                          ↓                                  │
│  INFERENCE PROCESS:                                        │
│  1. Compare each feature to its learned distribution       │
│  2. Calculate deviation from mean for each feature         │
│  3. Apply learned relationship for each feature            │
│  4. Sum adjustments to get predicted outcome              │
│                          ↓                                  │
│  PREDICTED OUTCOME for Kevin                              │
│  └─ Test Score ≈ 84 points                               │
│                                                              │
└──────────────────────────────────────────────────────────────┘


KEY PRINCIPLE:
Distributions of individual features capture what's "normal"
Relationships show how deviations affect outcomes
Together they enable prediction for new observations
```

---

## The Core Logic

> **When we learn feature distributions and their relationships to outcomes from a sample, we create a template for understanding new observations.**
>
> **For a new person, we check: How does each of their feature values compare to what we learned was "typical"?**
>
> **We then use the learned relationships to translate those comparisons into an outcome prediction.**
>
> **The result is an informed inference about what that person's outcome will be.**

This is exactly how machine learning makes predictions:
1. Learn distributions of features (from training data)
2. Learn relationships to outcome (from training data)
3. For new observation, compare to learned distributions
4. Use learned relationships to predict outcome
5. That prediction is the machine learning system's answer
