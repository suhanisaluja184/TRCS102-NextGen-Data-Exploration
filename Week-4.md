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

# Day 19 - ML Pipelines and Model Interpretation
 
**Date:** 24/07/2026 <br>
**Week:** 4 · Foundational Course <br>
**Session Focus:** Machine Learning Pipelines and Model Interpretation Techniques
 
---
 
### Session Summary
Today's session covered **ML Pipelines** to streamline the end-to-end workflow from data preprocessing to model training without data leakage, followed by **Model Interpretation** techniques to understand how models make predictions. We explored automated pipelines using scikit-learn and model explainability concepts.
 
---
 
### Topics Covered
 
**Introduction to ML Pipelines**
- A pipeline bundles multiple processing steps (such as imputation, scaling, encoding, and modeling) into a single scikit-learn object.
- Benefits: Prevents data leakage during cross-validation, simplifies code organization, ensures identical transformations on train and test sets, and streamlines production deployment.
 
**Building End-to-End Pipelines (`Pipeline` & `ColumnTransformer`)**
- Combining `Pipeline` with `ColumnTransformer` to handle numerical and categorical columns differently (e.g., applying standard scaling to continuous variables while encoding categorical variables).
- Chaining preprocessing transformers directly with a classifier model (like Random Forest or Logistic Regression) so that `.fit()` and `.predict()` execute the full sequence seamlessly.
 
**Introduction to Model Interpretation**
- The necessity of looking inside "black-box" machine learning models to build trust, verify fairness, and debug errors.
- Differentiating between global interpretability (understanding overall feature importance across the entire dataset) and local interpretability (explaining individual predictions for a single data point).
 
**Feature Importance & Explainability Concepts**
- Utilizing built-in model coefficients and tree-based feature importances to rank variable influence.
- Overview of advanced interpretation tools like SHAP (SHapley Additive exPlanations) and LIME (Local Interpretable Model-agnostic Explanations) to interpret complex model outputs intuitively.
 
---
 
## Key Learnings
- Pipelines are essential best practices in machine learning engineering, eliminating manual preprocessing steps and protecting against data leakage.
- Combining `ColumnTransformer` with `Pipeline` makes handling mixed data types clean and modular.
- Model interpretation bridges the gap between high predictive accuracy and human understanding, ensuring transparency in critical decision-making applications.
 
---
## Reflection
Building reusable ML pipelines will make my machine learning workflow much cleaner and less prone to manual preprocessing errors. Implementing a complete pipeline for my minor project will ensure that scaling and encoding are correctly encapsulated alongside the final classifier model.
 
---

# Day 20 - Final Project Submission: MediVitals AI Pro
 
**Date:** 27/07/2026 <br>
**Week:** 4 · Foundational Course <br>
**Session Focus:** Capstone Project Integration, End-to-End ML Pipeline Deployment, and Final Presentation
 
---
 
### Session Summary
Today marked the culmination of the foundational course with the final submission and presentation of our capstone project, **MediVitals AI Pro**. We integrated all the advanced machine learning techniques learned throughout the course—including data preprocessing, feature selection, hyperparameter tuning, and robust pipeline construction—into a production-ready health monitoring and predictive classification system.
 
---
 
### Topics Covered
 
**Capstone Architecture & Problem Formulation**
- Designed an end-to-end clinical health analytics workflow using patient vitals and demographic attributes to predict early health risk indicators.
- Structured the repository following standard software engineering practices, separating data ingestion, preprocessing pipelines, model training scripts, and evaluation modules.
 
**Pipeline Integration & Data Leakage Prevention**
- Deployed a comprehensive scikit-learn `Pipeline` combined with `ColumnTransformer` to handle missing value imputation, robust scaling of continuous biomarkers, and categorical encoding without leakage across cross-validation folds.
 
**Optimized Modeling & Hyperparameter Tuning**
- Evaluated multiple classification algorithms including Random Forest, Gradient Boosting, and Support Vector Machines.
- Applied `RandomizedSearchCV` and `GridSearchCV` to fine-tune critical hyperparameters, significantly boosting cross-validation accuracy and minimizing false negatives for critical health alerts.
 
**Model Interpretability & Deployment Readiness**
- Incorporated feature importance metrics and evaluation reports (Precision, Recall, F1-Score, and ROC-AUC curves) to ensure clinical transparency.
- Exported the finalized model pipeline using `joblib` for seamless inference integration into a web interface or API service.
 
---
 
## Key Learnings
- Building an end-to-end machine learning project requires rigorous adherence to modular pipelines to ensure that training and inference environments remain identical.
- Systematic hyperparameter tuning and thoughtful feature selection are essential for moving a baseline model into high-accuracy production territory.
- Clear model evaluation and interpretability are critical, especially in healthcare domains where trust and explainability drive adoption.
 
---
## Reflection
Wrapping up the foundational course with **MediVitals AI Pro** brought together every skill learned over the past four weeks—from exploratory data analysis and advanced feature engineering to hyperparameter tuning and automated pipelines. Seeing a complete, production-grade model run seamlessly from raw CSV input to final risk prediction gives me great confidence to tackle complex machine learning problems independently moving forward.
 
---
 

[Back to Diary Home](README.md)
