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

# Day 17 - Wrapper Methods for Feature Selection
 
**Date:** 22/07/2026 <br>
**Week:** 4 · Foundational Course <br>
**Session Focus:** Wrapper Methods, Forward Selection, Backward Elimination, RFE, and RFECV
 
---
 
### Session Summary
Today's session covered **Wrapper Methods**, which treat feature selection as a search problem where a machine learning algorithm is used to evaluate different subsets of features and choose the combination that yields the best model performance. We implemented various iterative wrapper strategies using the Teen Mental Health dataset.
 
**Trainer's Notes (Colab):** [Day 17 Notes](https://colab.research.google.com/drive/10Zykipg1G_FzovqG66ie-rijJoqQ0fyU?usp=sharing)
 
---
 
### Topics Covered
 
**1. Introduction to Wrapper Methods**
- Uses a machine learning model to score feature subsets.
- Explores combinations iteratively (unlike filter methods which score independently of models).
- Computationally heavier than filter methods but generally yields higher predictive accuracy.
 
**2. Forward Selection**
- Starts with zero features and adds one feature at a time based on performance improvement.
- Process: `No Features` $\rightarrow$ `Age` $\rightarrow$ `Age + Stress` $\rightarrow$ `Age + Stress + Anxiety` $\rightarrow$ `Stop`.
- Evaluated using `SequentialFeatureSelector` with Logistic Regression and Decision Tree classifiers.
 
**3. Backward Elimination**
- Starts with all features and removes the least significant feature one at a time as long as performance does not drop.
- Process: `All Features` $\rightarrow$ `Remove Gender` $\rightarrow$ `Remove Platform` $\rightarrow$ `Best Features Remain`.
 
**4. Recursive Feature Elimination (RFE)**
- Ranks all features by training the model, removing the least important feature based on coefficients or feature importances, and repeating until the desired number of features remain.
- Configured using `LogisticRegression` to select top features like `gender`, `daily_social_media_hours`, `sleep_hours`, `stress_level`, and `anxiety_level`.
 
**5. Recursive Feature Elimination with Cross-Validation (RFECV)**
- An automated version of RFE that integrates cross-validation to find the optimal number of features automatically instead of manually specifying $k$.
- Automatically determined an optimal count of 7 features for the dataset.
 
---
 
## Key Learnings
- Wrapper methods leverage actual model performance to guide feature selection, making them highly effective for specific algorithms.
- Forward selection builds up from scratch, whereas backward elimination and RFE prune down from the complete feature space.
- RFECV removes the guesswork of choosing how many features to keep by optimizing cross-validation scores automatically.
 
---
## Reflection
Using wrapper methods like RFE and RFECV gives a much clearer picture of feature contributions compared to simple filters. Implementing RFECV will be very useful for my minor project to automatically determine the optimal feature subset for predicting service-level agreement breaches without manual trial and error.
 
---

 # Day 18 - Hyperparameter Tuning Techniques
 
**Date:** 23/07/2026 <br>
**Week:** 4 · Foundational Course <br>
**Session Focus:** Hyperparameter Tuning, GridSearchCV, and RandomizedSearchCV
 
---
 
### Session Summary
Today's session explored **Hyperparameter Tuning**, the process of determining the optimal set of configuration settings for machine learning algorithms before training. We differentiated between model parameters and hyperparameters, reviewed key configurations for popular algorithms like Decision Trees, Random Forests, KNN, and SVM, and implemented exhaustive and randomized search techniques using scikit-learn.
 
**Trainer's Notes (Colab):** [Day 18 Notes](https://colab.research.google.com/drive/1LvPtZTSA5KUAJS_0XqtBhpShwkpjr44A?usp=sharing)
 
---
 
### Topics Covered
 
**1. Parameters vs. Hyperparameters**
- **Parameters:** Learned automatically from data during training (e.g., weights, biases). Cannot be manually set.
- **Hyperparameters:** Set manually before training to control the learning process (e.g., `max_depth`, `n_estimators`, `learning_rate`).
 
**2. Key Model Hyperparameters**
- **Decision Tree:** `max_depth`, `min_samples_split`, `min_samples_leaf`, `criterion` (`gini` or `entropy`).
- **Random Forest:** `n_estimators`, `max_depth`, `max_features`, `min_samples_leaf`.
- **KNN:** `n_neighbors`, `metric`, `weights`.
- **SVM:** `C` (regularization strength), `kernel` (`linear`, `RBF`, `polynomial`), `gamma`.
 
**3. GridSearchCV**
- An exhaustive search method that evaluates all possible combinations of a user-defined parameter grid using cross-validation.
- Implemented on a `DecisionTreeClassifier` with parameters like `max_depth`, `criterion`, and `min_samples_split`, identifying the best configuration to maximize cross-validation accuracy.
 
**4. RandomizedSearchCV**
- A more efficient alternative to GridSearchCV that samples a fixed number of parameter combinations randomly from specified distributions (using `scipy.stats.randint`).
- Configured with `n_iter=15` to quickly locate optimal model parameters without testing every single permutation.
 
---
 
## Key Learnings
- Proper hyperparameter tuning prevents underfitting or overfitting, significantly boosting model generalization on unseen data.
- GridSearchCV guarantees finding the best combination within the grid but can be computationally expensive for large search spaces.
- RandomizedSearchCV offers a faster, scalable approach by exploring random subsets of hyperparameter configurations efficiently.
 
---
## Reflection
Understanding how to systematically search for optimal hyperparameters using GridSearchCV and RandomizedSearchCV removes guesswork from model building. Applying these tuning methods to my minor project classifier will help squeeze out better performance and prevent overfitting on the training data.
 
---
 
[Back to Diary Home](README.md)
