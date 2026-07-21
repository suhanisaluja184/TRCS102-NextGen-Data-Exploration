# Week 4 - Advanced Feature Engineering & Selection
 
This week transitions from basic model building into data optimization, focusing on advanced preprocessing, feature selection techniques, and statistical tests to improve model accuracy and interpretability. Each day's activities and learning outcomes are documented below.
 
---

# Day 16 - Feature Selection Techniques
 
**Date:** 21/07/2026 <br>
**Week:** 4 · Foundational Course <br>
**Session Focus:** Feature Selection Methods and Statistical Tests
 
---
 
### Session Summary
The session focused on **Feature Selection**, exploring how to systematically identify and retain the most important features from a dataset while removing irrelevant, redundant, or noisy columns before model training. We covered various statistical techniques and filters using the Teen Mental Health dataset to evaluate feature relevance.
 
**Trainer's Notes (Colab):** [Day 16 Notes](https://colab.research.google.com/drive/1JBnFvWnZGAKzajhx0lH5frL6hW5uwAlh?usp=sharing)
 
---
 
### Topics Covered
 
**1. Introduction to Feature Selection**
- The process of selecting subset-relevant features to improve model performance.
- Benefits: Faster model training, higher accuracy, reduced overfitting, easier interpretation, lower memory usage, and removal of irrelevant columns.
- Methods categories: Filter Methods, Wrapper Methods, and Embedded Methods.
 
**2. Variance Threshold**
- Removes features with very low variance (near-constant values) as they contribute little useful information to the learning process.
- Using a threshold of $0.5$ successfully filtered out low-variance columns like `gender`, `academic_performance`, and `physical_activity`.
 
**3. Correlation Coefficient & Heatmap**
- Measures the linear relationship between features and the target variable, helping identify which features have the strongest predictive linear association.
- Visualized using Seaborn heatmaps with `coolwarm` palette to spot multicollinearity and feature-target linear correlation.
 
**4. Chi-Squared Test ($\chi^2$)**
- Evaluates dependency between categorical features and the target variable.
- Higher Chi-Square scores indicate a stronger relationship; top scoring features included `sleep_hours`, `stress_level`, and `anxiety_level`.
 
**5. Mutual Information**
- Measures how much information a feature provides about the target variable, capable of capturing both linear and non-linear relationships.
- A value of $0$ indicates total independence between the feature and the target.
 
**6. F-Test (ANOVA)**
- Measures whether the mean values of a feature differ significantly across target classes using $F$-scores and $P$-values.
- Higher $F$-scores denote greater separation between classes, identifying features like `sleep_hours` and `daily_social_media_hours` as highly discriminative.
 
---
 
## Key Learnings
- Feature selection is crucial for cutting down noise, reducing training time, and preventing overfitting on high-dimensional data.
- Different statistical tests (Correlation, Chi-Square, Mutual Information, and ANOVA F-Test) target different types of relationships (linear, non-linear, categorical, or continuous).
- Combining and ranking feature importance scores gives a holistic view of which variables truly drive model predictions.
 
---
## Reflection
Learning how to programmatically rank features using metrics like Mutual Information and ANOVA F-scores provides a rigorous way to clean up datasets rather than just guessing. It will be helpful to apply these feature selection filters to my minor project dataset to see which bug attributes actually matter for SLA breach prediction.
 
---

[Back to Diary Home](README.md)
