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
 
# Day 07 - Principal Component Analysis (PCA)
 
**Date:** 08/07/2026 <br>
**Week:** 2 · Foundational Course <br>
**Session Focus:** Dimensionality Reduction with PCA
 
---
 
### Session Summary
The session addressed a real problem: a college dataset predicting student placement has 16 features (Age, Gender, CGPA, Attendance, Study Hours, Family Income, Hosteller, Internet Usage, Assignments, Projects, Sports, Seminar Score, Backlogs, Lab Marks, Programming Score, Communication Score). More features mean more computation, more memory, slower training, and sometimes even lower accuracy - a problem called **High Dimensional Data**. PCA was introduced as the solution, demonstrated on the student dataset.
 
**Trainer's Notes (Colab):** [Day 07 Notes](https://colab.research.google.com/drive/1-p_irOj3K61ZXDreBP4aof1_ApUfv3z0?usp=sharing)
 
 
---
 
### Topics Covered
 
### What is PCA?
Principal Component Analysis (PCA) is a mathematical technique used to reduce the number of features in a dataset while retaining as much of the original information (variance) as possible. 

It functions by transforming the original, often correlated features into a smaller set of new, uncorrelated features called **Principal Components**. Think of this as taking a complex, multi-dimensional object and projecting it onto a 2D or 3D surface; you lose some detail, but you gain a much clearer view of the underlying patterns and structure.

### Core Concepts

*   **Standardization**: Before applying PCA, data must be scaled. Because PCA identifies directions of maximum variance, features with larger numerical ranges would unfairly dominate the results if not brought to a common scale.
*   **Principal Components**: These are artificial features created by PCA. The first principal component captures the largest possible variance in the data, the second captures the next largest, and so on.
*   **Explained Variance**: This metric tells you how much "information" or original data structure has been preserved in your chosen number of components. A high cumulative variance ratio indicates that your reduced dataset is a reliable representation of the original.

### Why Use PCA?
*   **Efficiency**: By reducing the number of dimensions, models become faster to train and less memory-intensive.
*   **Visualization**: It is nearly impossible for humans to visualize data beyond three dimensions. PCA allows us to project high-dimensional clusters onto a 2D plot, making it possible to visually identify groups or outliers in student data.
*   **Noise Reduction**: By focusing only on the components that hold the most variance, PCA effectively ignores smaller fluctuations that may just be random noise rather than meaningful patterns.

---
 
## Key Learnings
- PCA doesn't remove features randomly - it combines correlated ones into fewer, information-dense components.
- Scaling is a required step before PCA, since it's sensitive to the original scale of each feature.
- `explained_variance_ratio_` tells you how much information you'd lose by reducing dimensions - useful for deciding how many components to keep.
---
 
## Reflection
The luggage analogy made PCA click faster than I expected - compressing without losing what matters. The scatter plot of PC1 vs PC2 was the best part, seeing students actually cluster by similarity. Explained variance ratio needs a bit more practice to interpret confidently. Want to check if my own dataset has enough correlated numeric features to justify using PCA.
 
---

# Day 08 - Handling Imbalanced Data

**Date:** 07/07/2026 <br>
**Week:** 2 · Foundational Course <br>
**Session Focus:** Resampling Techniques for Class Imbalance  

---

### Session Summary
This session introduced **Imbalanced Data** — when one class has far more samples than another. Such imbalance causes models to favor the majority class, leading to poor performance on the minority class and misleading accuracy.  
Example: In fraud detection or rare disease diagnosis, the minority class is the most critical, yet often overlooked.  

On the student dataset, out of 490 students, ~35% were *Placed* and ~75% were *Not Placed*, confirming imbalance. Multiple resampling techniques were demonstrated to address this issue.

**Trainer's Notes (Colab):** [Day 08 Notes](https://colab.research.google.com/drive/1m0WmZlZG9iEYE9XtxcdRmFbBK8jqeVYB?usp=sharing)

---

### Why Imbalanced Data is a Problem
- Models get biased toward the majority class.  
- Minority class instances may be treated as noise.  
- Accuracy becomes misleading (e.g., always predicting "Not Fraud" still gives 99% accuracy).  
- Skewed decision boundaries → poor generalization on minority class.  

---

### Checking the Imbalance
- Used **value counts** and **countplot** to measure imbalance.  
- Confirmed minority class (Placed) was significantly underrepresented.  

---

### Train-Test Split
- Important to split before resampling.  
- Used **stratify option** to preserve class ratios in both train and test sets.  

---

### Resampling Techniques

Resampling methods are strategies to balance datasets where one class dominates. Each technique has its own strengths, weaknesses, and ideal use cases.  

---

#### 1. Random Oversampling
- **How it works:** Duplicates minority class samples (with replacement) until both classes have equal counts.  
- **Advantages:**  
  - Very simple to implement.  
  - Ensures the minority class is represented equally.  
- **Disadvantages:**  
  - Creates exact duplicates, which can cause the model to memorize rather than generalize.  
  - Risk of **overfitting** to repeated minority examples.  
- **Use Case Example:** In a loan default dataset, existing defaulter records are copied multiple times until their count matches non‑defaulters.  

---

#### 2. Random Undersampling
- **How it works:** Removes majority class samples at random until both classes are balanced.  
- **Advantages:**  
  - Avoids duplication and reduces dataset size.  
  - Faster training since fewer samples remain.  
- **Disadvantages:**  
  - Discards potentially useful majority data.  
  - Can lead to loss of important patterns.  
- **Use Case Example:** In defect detection, where good products vastly outnumber defective ones, undersampling removes excess “good product” records.  

---

#### 3. SMOTE (Synthetic Minority Oversampling Technique)
- **How it works:** Creates synthetic minority samples by interpolating between existing minority points and their nearest neighbors.  
- **Advantages:**  
  - Produces more diverse minority samples.  
  - Reduces overfitting compared to simple duplication.  
- **Disadvantages:**  
  - Can generate unrealistic samples if minority data is sparse.  
  - May blur class boundaries if not carefully applied.  
- **Use Case Example:** In rare disease diagnosis, SMOTE generates synthetic patient records that resemble realistic variations.  

---

#### 4. Tomek Links
- **How it works:** Identifies pairs of nearest‑neighbor points from different classes (called Tomek links) and removes the majority class point.  
- **Advantages:**  
  - Cleans overlapping regions between classes.  
  - Sharpens decision boundaries.  
- **Disadvantages:**  
  - Does not balance classes by itself; usually combined with other methods.  
- **Use Case Example:** In spam filtering, Tomek Links remove borderline legitimate emails that closely resemble spam.  

---

#### 5. ADASYN (Adaptive Synthetic Sampling)
- **How it works:** Builds on SMOTE but focuses on generating synthetic samples near the decision boundary, especially for minority points that are harder to classify.  
- **Advantages:**  
  - Targets the most challenging regions for classification.  
  - Improves model robustness on difficult cases.  
- **Disadvantages:**  
  - Can introduce noise if boundary regions are not well defined.  
  - More computationally intensive than SMOTE.  
- **Use Case Example:** In fraud detection, ADASYN generates synthetic fraud transactions that closely resemble genuine ones, making the model better at catching subtle fraud.  

---

#### 6. SMOTETomek (Combined Approach)
- **How it works:** First applies SMOTE to generate synthetic minority samples, then uses Tomek Links to remove overlapping or noisy majority points.  
- **Advantages:**  
  - Balances classes while cleaning boundaries.  
  - Combines strengths of oversampling and boundary refinement.  
- **Disadvantages:**  
  - More complex to implement.  
  - May require careful parameter tuning.  
- **Use Case Example:** In loan default prediction, SMOTETomek generates synthetic default cases and removes ambiguous overlaps, resulting in a cleaner dataset for risk modeling.  

---

### Summary
- **Oversampling** → Adds minority samples (risk: overfitting).  
- **Undersampling** → Removes majority samples (risk: information loss).  
- **SMOTE/ADASYN** → Generate synthetic samples (better generalization).  
- **Tomek Links** → Clean overlapping boundaries.  
- **SMOTETomek** → Hybrid approach for balance + boundary clarity.  

---

### Key Learnings
- Imbalanced data is common in real-world problems.  
- Accuracy alone is not reliable for imbalanced datasets.  
- Resampling techniques (oversampling, undersampling, SMOTE, ADASYN, Tomek Links) help balance classes.  
- Always split train/test before resampling to keep evaluation realistic.  

---

### Reflection
This session highlighted why imbalance is dangerous and how naive accuracy can be misleading. Techniques like SMOTE and ADASYN felt powerful because they create synthetic variety rather than just duplicating data. Next step: apply these methods to my minor project dataset to ensure fair model performance.

 ---

 
[Back to Diary Home](README.md)
