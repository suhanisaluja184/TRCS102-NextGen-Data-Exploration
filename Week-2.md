# Week 2 - Advanced Data Exploration

This week builds on Week 1's foundations, moving into feature engineering, PCA, imbalanced data handling, and anomaly detection. Each day's activities and learning outcomes are documented below.

---

# Day 06 - Feature Engineering

**Date:** 07/07/2026 <br>
**Week:** 2 · Foundational Course <br>
**Session Focus:** Feature Engineering Techniques

---

### Session Summary
The session covered Feature Engineering - transforming raw data into useful features that improve machine learning model performance. Five of the seven common techniques (Create, Transform, Scale, Encode, Bin) were demonstrated on the student dataset.

**Trainer's Notes (Colab):** [Day 06 Notes](https://colab.research.google.com/drive/1n-fsko1cr7PLRGOtOXmzN3y8bPDy0ZiY?usp=sharing)


---

### Topics Covered

**Feature Creation** - Creating entirely new columns from existing ones to capture relationships a single column can't show alone.
- `Work_Performance` = Tasks_Completed * Attendance – combines productivity and consistency into one workplace metric.
- `Savings_Stability` = Savings / Monthly_Expenses – shows resilience of financial planning.
- `Learning_Effectiveness` = Skills_Acquired / Study_Hours – captures efficiency of knowledge gained per hour invested.

**Feature Transformation** - Used when data exists but in the wrong form for analysis or modeling. Common transformation ways discussed: Square Root, Cube Root, Reciprocal, and Normalization.
- Applied `np.log()` on the `Family_Income` column, which was originally right-skewed (most values bunched at lower incomes with a long tail toward higher incomes).
- Plotted histograms before and after the log transform - the original distribution was uneven across income bins, while the log-transformed version looked much closer to a normal, bell-shaped distribution.

**Feature Scaling** - Necessary because columns like CGPA (0-10) and Attendance (0-100) exist on very different scales, which can bias distance-based ML models.
- **StandardScaler** - standardizes data to have mean 0 and standard deviation 1; applied to CGPA and Attendance together.
- **MinMaxScaler** - rescales data into a fixed range (0 to 1); applied separately to CGPA.

**Encoding** - Machine learning models understand numbers, not text labels, so categorical columns must be converted.
- `pd.get_dummies(df, columns=["Department"])` - one-hot encoding, creating a separate 0/1 column for each department.
- `LabelEncoder` - converted `Placement_Status` into binary numeric form (Placed = 1, Not Placed = 0).

**Binning** - Grouping continuous numeric values into meaningful categories.
- `pd.cut(df["Attendance"], bins=[0,70,85,100], labels=["Low","Medium","High"])` - converted the numeric Attendance column into an Attendance_Level column with Low/Medium/High categories.

---

## Key Learnings
- New features (ratios, products) can capture relationships a single column can't show alone.
- Log transform helps normalize heavily skewed data like income.
- Encoding is necessary since ML models only understand numbers, not text labels.

---

## Reflection
Feature engineering felt like a toolbox session - lots of distinct techniques rather than one big concept. Scaling and encoding made sense quickly since the code pattern is similar each time. Want to try binning and log transforms on my own dataset next.

---

[Back to Diary Home](README.md)
