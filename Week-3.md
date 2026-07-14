# Week 3 - Machine Learning Essentials
 
This week moves from data preparation into actual model building - supervised learning, classification vs regression, evaluation metrics, and train-test/cross-validation practices. Each day's activities and learning outcomes are documented below.
 
---
 
# Day 11 - Introduction to Supervised Learning: Classification & Regression
 
**Date:** 14/07/2026 <br>
**Week:** 3 · Foundational Course <br>
**Session Focus:** Supervised Learning Fundamentals
 
---

### Session Summary
Today’s session marked the transition from data preparation to active model building by introducing **Supervised Learning**. The core concept involves training an algorithm on a labeled dataset, where both the input features and the corresponding target outputs (labels) are provided. By analyzing these pairs, the model learns the underlying mapping function, allowing it to predict outcomes for new, previously unseen data—much like a student learning to solve problems by studying examples and their solutions.

**Trainer's Notes (Colab):** [Day 11 Notes](https://colab.research.google.com/drive/1kUVNb4Gl54pCHssdhx73EnAEZBmQL5Fw?usp=sharing)

---

### Topics Covered

### The Supervised Learning Workflow
Every project follows a consistent, cyclical pipeline:
1.  **Data Collection & Preparation**: Utilizing the cleaning and feature engineering techniques from previous sessions.
2.  **Splitting**: Dividing the data into training and testing sets to evaluate performance objectively.
3.  **Model Training**: Allowing the algorithm to learn patterns from the training data.
4.  **Evaluation**: Testing the model's accuracy on the unseen test set.
5.  **Prediction**: Using the trained model to forecast outcomes for new inputs.

### Classification vs. Regression
Choosing the correct approach depends entirely on the nature of the target variable:

*   **Classification**: Used when the goal is to assign observations to discrete, predefined categories (e.g., "Placed" vs. "Not Placed" or "Spam" vs. "Not Spam"). These models often calculate probabilities for each class and apply a threshold to finalize the category.
*   **Regression**: Used when the target is a continuous numerical value. Instead of labels, the output is a real number (e.g., salary predictions, house prices, or temperature).

### Core Algorithms
*   **Classification**: Logistic Regression, Naive Bayes, K-Nearest Neighbors (KNN), Support Vector Machine (SVM), Decision Tree, and Random Forest.
*   **Regression**: Linear Regression, Ridge Regression, and Lasso Regression.

---

### Practical Application & Generalization
The session demonstrated the versatility of **Logistic Regression** by applying the exact same workflow to two distinct domains:
*   **Student Placement**: Predicting placement status based on features like CGPA, attendance, and study hours.
*   **Teen Mental Health**: Predicting depression labels using factors such as social media usage, sleep, and stress levels.

The success of these models—reaching ~80.6% and ~99% accuracy respectively—underscored that supervised learning is not domain-specific. Rather, it is a robust, generalizable framework where the model weighs the *combination* of all input features to arrive at a prediction, rather than relying on any single variable in isolation.

---

### Key Learnings
*   **Target-Driven Choice**: The format of the output variable dictates the selection between classification and regression models.
*   **Feature Synergy**: Models derive their predictive power from the interaction of multiple features, reflecting complex real-world relationships.
*   **Consistency**: The same pipeline—train/test split, algorithm application, and prediction—remains effective even when shifting from academic datasets to sensitive, real-world health applications.

---

### Summary
Supervised learning transforms raw, labeled data into predictive capability. By mastering the fundamental workflow—from data split to final evaluation—one can apply these models across diverse fields, moving from simple descriptive analysis to proactive, data-driven decision making.

---
 
[Back to Diary Home](README.md)
