# From Data Distributions to Machine Learning
## Step-by-Step Teaching Guide with Student Sample Walkthrough

A complete guide for teaching how machines learn from data by examining distributions, relationships, and patterns in sample data.

**Duration:** 45-60 minutes  
**Target Audience:** Data Literacy Bootcamp students  
**Prerequisites:** Understanding of data types, descriptive statistics, distributions, correlation

---

## Table of Contents

1. [Overview & Learning Objectives](#overview--learning-objectives)
2. [Teaching Timeline](#teaching-timeline)
3. [The 10-Student Sample Dataset](#the-10-student-sample-dataset)
4. [Step 1: Understanding the Data](#step-1-understanding-the-data)
5. [Step 2: Univariate Distributions](#step-2-univariate-distributions)
6. [Step 3: Relationships & Correlations](#step-3-relationships--correlations)
7. [Step 4: Making Predictions](#step-4-making-predictions)
8. [Step 5: The Learning Loop](#step-5-the-learning-loop)
9. [Key Concepts Checklist](#key-concepts-checklist)
10. [Assessment Questions](#assessment-questions)
11. [Connection to Data Literacy Bootcamp](#connection-to-data-literacy-bootcamp)

---

## Overview & Learning Objectives

### Purpose

This guided walkthrough teaches how machines learn from data using a concrete example: predicting student test scores from a sample of 10 students. Students will trace through each step of the machine learning process and see how bootcamp concepts (distributions, relationships, inference) flow directly into real-world prediction systems.

### Learning Objectives

After completing this lesson, students will be able to:

- **Understand univariate distributions:** Recognize how machines examine mean, standard deviation, and range of individual features
- **Discover bivariate relationships:** See how machines find correlations between features and outputs
- **Combine features for prediction:** Understand multivariate prediction and why multiple features are better than one
- **Connect bootcamp concepts:** Apply distributions, correlation, sampling, and inference to machine learning
- **Practice statistical thinking:** Identify patterns, spot outliers, and interpret results

---

## Teaching Timeline

### Total Time: 45-60 minutes

| Segment | Time | Content |
|---------|------|---------|
| **1. Introduction** | 3-5 min | Show dataset, identify features vs. output |
| **2. Univariate Distributions** | 12-15 min | Examine each feature individually (mean, std dev, range) |
| **3. Relationships** | 10-12 min | Find correlations between features and test scores |
| **4. Making a Prediction** | 12-15 min | Walk through predicting for a new student (Kevin) |
| **5. Wrap-up & Discussion** | 8-10 min | Review learning loop, ask key questions, connect to bootcamp |

### Segment 1: Introduction (3-5 minutes)

**What you do:**
1. Display the 10-student dataset on screen
2. Ask: "What are features vs. the output we want to predict?"
3. Get volunteers to identify them
4. Say: "Today we're going to see exactly how machines learn to predict from this kind of data"

**Key points:**
- Features = Hours studied, Prior GPA, Sleep hours, Attendance %
- Output = Test score (what we're predicting)
- This is a SAMPLE that represents a larger population

### Segment 2: Univariate Distributions (12-15 minutes)

**What you do:**
1. Walk through Step 2 showing each feature's distribution
2. For each feature, calculate or discuss: mean, standard deviation, range
3. Ask: "What does standard deviation tell us?"
4. Have students predict: "Is 10 hours of study normal or unusual?"

**Key points:**
- Machines don't memorize; they calculate statistics
- Std dev tells us what "typical variation" looks like
- When machines see new data, they compare to learned distributions
- Small std dev = tight clustering; Large std dev = more spread

### Segment 3: Relationships (10-12 minutes)

**What you do:**
1. Show how each feature relates to test scores
2. List students by one feature (e.g., hours studied) and show scores increase
3. Ask: "Does more sleep CAUSE higher scores, or is it just correlation?"
4. Discuss: "Can machines use correlations without claiming causation?"

**Key points:**
- All relationships here are positive (higher feature → higher scores)
- Correlation ≠ Causation (from your bootcamp!)
- Machines use patterns for prediction anyway
- Some features are stronger predictors than others

### Segment 4: Making a Prediction (12-15 minutes)

**What you do:**
1. Introduce Kevin (new student) with his feature values
2. Ask students FIRST: "What do you predict Kevin will score?"
3. Walk through step-by-step comparison to learned patterns
4. Build up prediction from baseline + bonuses
5. Reveal predicted score and explain why

**Key points:**
- Compare new observation to learned distributions
- Combine all features (multivariate prediction)
- Explain deviations from baseline
- Emphasize: predictions are estimates, not guarantees

### Segment 5: Wrap-up & Discussion (8-10 minutes)

**What you do:**
1. Review Step 5: the learning loop (more data → better patterns)
2. Ask key assessment questions
3. Connect back to bootcamp concepts
4. Summarize the full ML process

**Key points:**
- Sample size matters (larger samples = more reliable patterns)
- Machine learning is iterative
- All bootcamp concepts are the foundation for ML

---

## The 10-Student Sample Dataset

### Raw Data Table

| Student | Hours Studied | Prior GPA | Sleep Hours | Attendance % | Test Score |
|---------|---|---|---|---|---|
| Alice | 6 | 3.8 | 7 | 95 | **92** |
| Bob | 3 | 3.2 | 5 | 80 | **78** |
| Carol | 5 | 3.5 | 6 | 90 | **85** |
| David | 4 | 2.9 | 5 | 75 | **72** |
| Emma | 7 | 3.9 | 8 | 98 | **94** |
| Frank | 2 | 2.8 | 4 | 70 | **68** |
| Grace | 6 | 3.7 | 7 | 92 | **90** |
| Henry | 4 | 3.3 | 6 | 85 | **80** |
| Iris | 5 | 3.6 | 7 | 88 | **88** |
| Jack | 3 | 3.0 | 5 | 78 | **75** |

### Key Dataset Information

- **Shape:** 10 rows (observations/students) × 6 columns (student name + 4 features + 1 output)
- **Features (inputs):** Hours studied, Prior GPA, Sleep hours, Attendance %
- **Output (target):** Test score
- **Data type:** This is a SAMPLE representing the population of all possible students

### Teaching Points for Step 1

1. **Identify components:**
   - Ask: "Which column is output?" → Test score
   - Ask: "How many features?" → Four
   - Ask: "How many observations?" → Ten students

2. **Explain dataset shape:**
   - "10 rows × 6 columns" or shape (10, 6)
   - Rows = observations; Columns = variables

3. **Discuss population vs. sample:**
   - "These 10 are a SAMPLE"
   - "They represent a larger POPULATION of possible students"
   - "The machine learns from this sample to predict for new students it hasn't seen"

---

## Step 1: Understanding the Data

### What You're Teaching

Students need to understand what a "sample" is in machine learning and identify features vs. the output. This is a fundamental review of data literacy bootcamp content.

### Checkpoint Questions for Step 1

1. **Which column is the output (what we want to predict)?**
   - Answer: Test score

2. **How many features (input columns) does this dataset have?**
   - Answer: Four (Hours studied, Prior GPA, Sleep hours, Attendance %)

3. **Why do you think we need MULTIPLE features to predict test scores, not just Prior GPA?**
   - Answer: Each feature contains different information. A student with a 3.5 GPA who studies 3 hours might score differently than one with the same GPA who studies 7 hours. All features together give a fuller picture than any single feature alone.

---

## Step 2: Univariate Distributions

### What You're Teaching

Machines don't just memorize data; they calculate summary statistics to understand what "typical" or "normal" looks like for each feature. This directly applies bootcamp content on measures of central tendency and dispersion.

### Feature Distribution Summary

| Feature | Mean | Std Dev | Range | Typical (±1 SD) |
|---------|------|---------|-------|-----------------|
| **Hours Studied** | 4.5 | 1.6 | 2-7 | 3-6 hours |
| **Prior GPA** | 3.4 | 0.35 | 2.8-3.9 | 3.05-3.75 |
| **Sleep Hours** | 6.1 | 1.2 | 4-8 | 4.9-7.3 hours |
| **Attendance %** | 85% | 8.5 | 70-98 | 76-94% |
| **Test Score** | 81 | 7.5 | 68-94 | 73.5-88.5 |

### Teaching Steps for Step 2

#### 1. Introduce the Concept
"Now we're going to see what machines notice first: the distribution of each feature. Just like you learned in the bootcamp, machines calculate the mean, standard deviation, and range to understand what 'typical' looks like."

#### 2. Walk Through One Feature in Detail (Hours Studied)

**Raw values:** 6, 3, 5, 4, 7, 2, 6, 4, 5, 3

**Calculate mean:**
```
(6 + 3 + 5 + 4 + 7 + 2 + 6 + 4 + 5 + 3) ÷ 10 = 45 ÷ 10 = 4.5 hours
```

**Interpret:**
- "On average, students study 4.5 hours"
- "But they don't all study exactly 4.5 hours"
- "Some study 2 hours, others study 7 hours"
- "That spread is what standard deviation measures"

**Explain standard deviation (1.6):**
- "Std dev is 1.6 hours"
- "That means most students study between 3 and 6 hours (mean ± 1 std dev)"
- "If someone studied 10 hours, that would be UNUSUAL to the machine"
- "It's far outside the typical range we learned from the sample"

#### 3. Point Out Variations in Other Features

- **Sleep hours:** Low std dev (1.2) → tight clustering, not much variation
- **Attendance %:** High std dev (8.5) → more spread out, some extreme values
- **Prior GPA:** Medium std dev (0.35) → moderate variation

#### 4. Key Question: What Does This Mean for the Machine?

"When the machine sees a NEW student with 6 hours of study (or 8 hours of sleep), it knows: 'That's above average but not crazy unusual.'

When it sees 10 hours of study or 3 hours of sleep, it thinks: 'That's WAY outside the typical pattern I've learned.'"

### Checkpoint Questions for Step 2

1. **What does standard deviation tell a machine?**
   - Answer: It shows how spread out the data is from the mean. A small std dev means most values are close to the mean (tight clustering). A large std dev means values are more scattered.

2. **If the mean sleep is 6.1 hours with std dev 1.2, is 7 hours unusual? Is 8 hours unusual?**
   - Answer: 7 hours is within 1 std dev (6.1 + 1.2 = 7.3), so it's not unusual. 8 hours is beyond 1 std dev, getting more unusual (though not extreme).

3. **Which feature has the MOST variability (spread) in your sample? Why is that important?**
   - Answer: Attendance % (std dev 8.5). This tells the machine that attendance varies more—some students show up consistently, others are sporadic. The machine needs to account for this variability when making predictions.

---

## Step 3: Relationships & Correlations

### What You're Teaching

Now students see that machines discover CORRELATIONS: how features relate to the output (test scores) and to each other. This is where bivariate analysis from your bootcamp comes alive. **Emphasize: correlation ≠ causation, but machines use correlations for prediction anyway.**

### Key Relationships

| Feature ↔ Test Score | Correlation | Example | Pattern |
|---|---|---|---|
| **Hours Studied** | Strong positive | Emma (7h → 94), Frank (2h → 68) | ~+3 points per hour |
| **Prior GPA** | Strong positive | Emma (3.9 → 94), Frank (2.8 → 68) | ~+10 points per 0.1 GPA |
| **Sleep Hours** | Moderate positive | Emma (8h → 94), Bob (5h → 78) | ~+4 points per hour |
| **Attendance %** | Strong positive | Emma (98% → 94), Frank (70% → 68) | ~+0.3 points per 1% |

### Teaching Steps for Step 3

#### 1. Introduce Bivariate Analysis

"We've looked at each feature by itself. Now let's see how each feature RELATES to the test score. Remember correlation from your bootcamp? We're doing that here."

#### 2. Walk Through One Relationship: Hours Studied ↔ Test Score

**List students by hours studied (lowest to highest):**

| Hours | Students | Scores |
|-------|----------|--------|
| 2 | Frank | 68 |
| 3 | Bob, Jack | 78, 75 |
| 4 | David, Henry | 72, 80 |
| 5 | Carol, Iris | 85, 88 |
| 6 | Alice, Grace | 92, 90 |
| 7 | Emma | 94 |

**Ask:** "What do you notice? As hours studied increases, what happens to test scores?"

**Expected answer:** "They go up!"

**Reinforce:** "This is a POSITIVE correlation."

**Approximate the pattern:** "For every extra hour of study, scores go up about 3 points. The machine learns this pattern."

#### 3. Emphasize: Correlation ≠ Causation

**Ask:** "Does more SLEEP definitely CAUSE higher scores?"

**Expected answer:** "Probably not. But well-rested, disciplined students probably study more, sleep better, AND attend more. All these things move together."

**Conclude:** "The machine doesn't claim causation. It just says: 'I see a pattern. When students have these traits together, their scores are higher. I'll use that pattern to predict.'"

#### 4. Show the Relationships Summary Table

**Point out:**
- All features have POSITIVE correlations with test scores (fortunate!)
- They all push in the same direction (higher feature values → higher scores)
- Some features are stronger predictors (study hours, GPA) than others (sleep)
- The machine learns which matter more

### Checkpoint Questions for Step 3

1. **Is there a correlation between Prior GPA and test scores? Positive or negative?**
   - Answer: Yes, strong positive. Higher GPA → higher test scores.

2. **If we see that "students with high attendance have high test scores," can we say "good attendance causes high scores"?**
   - Answer: No! Correlation doesn't prove causation. It's possible that engaged, motivated students both attend more AND score higher. The causation might be indirect (motivation causes both) or unclear.

3. **If a feature had a NEGATIVE correlation with test scores, what would that mean?**
   - Answer: It would mean that as that feature increases, test scores tend to DECREASE. For example, if "anxiety level" had negative correlation: higher anxiety → lower scores. This would suggest the feature is harmful to test performance.

---

## Step 4: Making Predictions

### What You're Teaching

This is the payoff. Students see exactly how machines USE the distributions and relationships they've learned to make predictions for new, unseen data. This is multivariate prediction—combining all features.

### Meet Kevin: A New Student

**Kevin's features:**
- Hours studied: 5
- Prior GPA: 3.5
- Sleep hours: 6
- Attendance %: 88

### The Prediction Process

#### Step 4a: Compare Kevin to Learned Distributions

| Feature | Kevin's Value | Mean | Comparison | Interpretation |
|---------|---|---|---|---|
| Hours studied | 5 | 4.5 | Above average | ✓ Good sign |
| Prior GPA | 3.5 | 3.4 | Above average | ✓ Good sign |
| Sleep hours | 6 | 6.1 | About average | ~ Neutral |
| Attendance % | 88% | 85% | Above average | ✓ Slight positive |

**Explanation:**
- "Kevin studies 5 hours (mean 4.5, above average). That's a positive sign."
- "His GPA is 3.5 (mean 3.4, above average). Also good."
- "He sleeps 6 hours (mean 6.1). That's just about typical."
- "He attends 88% (mean 85%). Slightly above average."

#### Step 4b: Combine the Patterns (Simplified Model)

```
Baseline score (class mean):     81 points
+ Study bonus (5 hrs):            +2 points   (above average)
+ GPA bonus (3.5):                +1 point    (above average)
+ Sleep (6 hrs):                   0 points   (about average)
+ Attendance bonus (88%):         +1 point    (slightly above)
─────────────────────────────────────────
Predicted score:                 85 points
```

**What just happened:**
"The machine combined what it learned about each feature's relationship with the test score. Kevin has above-average study hours and GPA, so we predict he'll score above the class mean. This is called multivariate prediction—considering all features together."

### Teaching Steps for Step 4

#### 1. Show Kevin's Data

"A new student, Kevin, is about to take the test. We don't know his score yet. But based on what we've learned from our 10 students, can we predict it? Let's see."

#### 2. Ask Students to Predict FIRST

**Before revealing the machine's prediction, ask:**
- "What do YOU think Kevin will score?"
- "Why do you think that?"
- Get several predictions from volunteers

#### 3. Walk Through the Comparison

Go through each feature, discussing how it compares to the learned distributions.

#### 4. Build Up the Prediction Step-by-Step

Show the baseline, then add bonuses one by one, explaining each.

#### 5. Reveal Predicted Score

"Based on all these patterns combined, the machine predicts Kevin will score approximately **85**."

#### 6. Discuss the Prediction

**Ask:**
- "Why 85 and not 88 or 82?"
- "Why did we use all four features instead of just GPA?"
- "Is this a guarantee or an estimate?"

**Explain:**
- "Kevin's features are all above average but not exceptional"
- "He's a solid student who should do well, but not amazingly well"
- "This is an ESTIMATE based on patterns we learned, not a guarantee"
- "Kevin might study harder on test day, or have personal stress affecting him"

### Checkpoint Questions for Step 4

1. **If Kevin studied 3 hours instead of 5 (all other features the same), would his predicted score be higher or lower?**
   - Answer: Lower. Less study time → fewer points added to baseline.

2. **Why did we combine ALL four features instead of just using his prior GPA?**
   - Answer: Because each feature contains unique information. A student with a 3.5 GPA who studies 3 hours might score differently than one with the same GPA who studies 7 hours. All features together give a fuller picture than GPA alone.

3. **If Kevin's actual test score is 92 but we predicted 85, does that mean our machine "failed"?**
   - Answer: No. A prediction is based on learned patterns, not a guarantee. If Kevin actually scored 92 (7 points higher), he either performed better than expected on test day, or there's a factor not in our data (e.g., extra tutoring, less test anxiety). Predictions have uncertainty, which is normal.

---

## Step 5: The Learning Loop

### What You're Teaching

Machines get better as they see more data. This is the iterative nature of learning and ties to bootcamp concepts of population vs. sample size and the Central Limit Theorem.

### The Continuous Loop

```
1. Collect data
       ↓
2. Machine learns patterns
       ↓
3. Makes predictions
       ↓
4. Collects more data
       ↓
2. Machine re-learns (patterns sharpen)
       ↓
3. Predictions improve
       ↓
... repeat
```

### Teaching Steps for Step 5

#### 1. Introduce the Loop

"We made a prediction with just 10 students. But what happens next semester when we have 25 students? Then 50? Then 100?"

#### 2. Discuss Reliability with Sample Size

**Ask:** "If we calculated the mean study hours with 10 students and got 4.5, but then with 100 students we get 4.3, what changed?"

**Expected answer:** "The larger sample is more representative of the true population."

**Connect:** "This is the Central Limit Theorem and sampling from your bootcamp! Larger samples give better estimates."

#### 3. Show the Improvement Cycle

```
10 students     → rough patterns
50 students     → sharper patterns
500 students    → very reliable patterns
5000 students   → highly accurate predictions
```

#### 4. Key Insight

"Machine learning isn't a one-time event. It's a cycle: collect data → learn patterns → make predictions → collect more data → refine patterns → better predictions. The more good data you feed the machine, the better it learns."

### Checkpoint Questions for Step 5

1. **Why would a machine's predictions improve with MORE data?**
   - Answer: Because larger samples are more representative of the true population. The mean, std dev, and correlations become more reliable. The machine's estimates of what "typical" looks like get more accurate.

2. **If one outlier student (studied 0 hours, scored 95) is in your sample of 10, how much does it affect the mean study hours? What if you had 1000 students?**
   - Answer: In a sample of 10, that outlier pulls the mean significantly. In 1000 students, that one outlier has almost no effect on the mean.

3. **Does machine learning ever "stop"? Is there a point where you have "enough data"?**
   - Answer: Theoretically, machine learning is continuous. More data almost always helps (assuming good quality data). Some ML systems run continuously, updating their patterns as new data arrives daily.

---

## Key Concepts Checklist

Use this checklist to ensure students have grasped the core ideas:

### Understanding the Data

- [ ] Students can identify features (inputs) vs. output (target)
- [ ] Students can describe dataset shape (rows × columns)
- [ ] Students understand a sample represents a larger population

### Univariate Distributions

- [ ] Students can calculate or interpret mean (average)
- [ ] Students understand standard deviation as a measure of spread
- [ ] Students can identify "typical" vs. "unusual" values using mean ± std dev
- [ ] Students see how each feature is individually distributed

### Bivariate Relationships

- [ ] Students can spot positive/negative correlations
- [ ] Students understand correlation ≠ causation
- [ ] Students recognize that machines use correlations for prediction without claiming causation
- [ ] Students can estimate the strength of a relationship (strong, moderate, weak)

### Multivariate Prediction

- [ ] Students can compare new observations to learned distributions
- [ ] Students understand combining multiple features for better predictions
- [ ] Students see predictions as estimates with uncertainty (not guarantees)

### The Learning Loop

- [ ] Students understand machine learning is iterative
- [ ] Students see that larger samples → more reliable patterns
- [ ] Students connect this to Central Limit Theorem and sampling from bootcamp

---

## Assessment Questions

### During the Lesson (Formative)

#### After Step 1
- "How many students are in our sample?"
- "How many features do we have?"
- "Which column is what we're trying to predict?"

#### After Step 2
- "What's the mean (average) hours studied?"
- "If std dev of study hours is 1.6, what range includes most students?"
- "Which feature has the LEAST variation among students?"

#### After Step 3
- "Do higher study hours correlate with higher test scores?"
- "Do higher study hours definitely CAUSE higher test scores?"
- "Which feature is the STRONGEST predictor of test scores?"

#### After Step 4
- "Predict the score for a student with: 6 hours, 3.8 GPA, 7 hours sleep, 95% attendance"
- "Why did we use all four features instead of just GPA?"
- "Is this prediction a guarantee or an estimate?"

### End of Lesson (Summative)

1. **Explain to someone who wasn't in class today: How do machines learn to make predictions from data?**

2. **Why does a machine need to understand the distribution (mean, std dev) of each feature?**

3. **You discover that "students with high anxiety have lower test scores." Is this correlation? Causation? Explain.**

4. **If you had 500 student records instead of 10, how would your predictions change? Why?**

5. **In your own words: What's the difference between looking at one feature (univariate) vs. all features together (multivariate)?**

### Extension Discussion Questions

1. "What features might we add to better predict test scores? What about features we SHOULDN'T use?"

2. "Machines learned these patterns from past students. Are these patterns guaranteed to work for FUTURE students? Why or why not?"

3. "Imagine we predicted a new student's score as 85, but they actually scored 78. What could explain this difference?"

4. "Where else in the real world do you think machines learn from distributions and relationships in data?" (Examples: Netflix recommendations, credit scoring, medical diagnosis, loan approval, job recommendations)

---

## Connection to Data Literacy Bootcamp

### How This Lesson Ties Together Bootcamp Concepts

| Bootcamp Concept | This Lesson | Machine Learning Connection |
|---|---|---|
| **Data shape (rows × columns)** | Understanding dataset structure (10 × 6) | Machines need to know how much data they have to work with |
| **Measures of central tendency** | Computing means for each feature | Establishing what "normal" looks like |
| **Measures of dispersion** | Computing standard deviations | Determining what's "typical" vs. "unusual" |
| **Correlation** | Discovering relationships between features & output | Using patterns for prediction without claiming causation |
| **Population vs. Sample** | Learning from 10 students to predict future students | Sample patterns generalize to larger population |
| **Inference & prediction** | Making Kevin's prediction based on learned patterns | Generalizing from known data to predict unknown outcomes |
| **Sample size & Central Limit Theorem** | Improving predictions with more data | Larger samples = more reliable pattern estimates |

### Final Message to Students

> Everything you learned in the bootcamp about data, distributions, and relationships is the **FOUNDATION of machine learning**. When a machine learns, it's doing exactly what you just did: examining distributions, finding correlations, and using those patterns to make predictions. 
>
> You now understand the core idea behind how modern AI and machine learning work. In future lessons, you'll see more complex algorithms, but they're all built on these fundamental concepts: distributions, relationships, and inference from samples.

---

## References & Further Reading

### Concepts Covered
- Univariate analysis
- Bivariate analysis & correlation
- Multivariate prediction
- Sampling & inference
- Central Limit Theorem
- Distribution characteristics
- Statistical modeling basics

### Related Bootcamp Modules
- Data Types & Shapes
- Descriptive Statistics
- Distributions & Histograms
- Correlation & Relationships
- Population vs. Sample
- Inference & Prediction

### Key Takeaways

1. **Machines learn distributions** - They use mean, std dev, and range to understand "typical"
2. **Machines find relationships** - They discover correlations between features and outputs
3. **Machines combine patterns** - Multiple features together make better predictions than any single feature
4. **Machines iterate** - More data → sharper patterns → better predictions
5. **Machines don't guarantee** - Predictions are probability-based estimates, not certainties

---

## Files in This Repository

```
├── README.md (this file)
├── teaching-guide.docx          # Word version for printing/sharing
├── sample-data.csv              # 10-student dataset in CSV format
├── interactive-walkthrough.html # Interactive version for classroom display
└── student-workbook.md          # Fill-in-the-blank version for students
```

---

## How to Use This Guide

### For Instructors
1. Read through the entire guide before class
2. Familiarize yourself with the 10-student dataset
3. Practice walking through the prediction for Kevin
4. Use the checkpoint questions to gauge student understanding
5. Save/share the GitHub link with students for reference

### For Students
1. Review the learning objectives before class
2. Follow along with the sample dataset during the walkthrough
3. Take notes on each step
4. Work through checkpoint questions
5. Complete the end-of-lesson assessment questions

### For Self-Study
1. Start with the Overview & Learning Objectives
2. Work through each step in sequence
3. Pause at checkpoint questions and answer them
4. Review the Key Concepts Checklist
5. Test your understanding with Assessment Questions

---

## Contributing

Found an error or have suggestions for improvement? Please open an issue or submit a pull request!

## License

This teaching guide is provided as educational material. Feel free to use, adapt, and share with proper attribution.

---

**Last Updated:** 2025-05-16  
**Version:** 1.0  
**Status:** Ready for classroom use
