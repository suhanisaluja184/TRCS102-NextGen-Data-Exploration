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

# Day 12 - Comparing Classification Algorithms: Naive Bayes, KNN & SVM
 
**Date:** 15/07/2026 <br>
**Week:** 3 · Foundational Course <br>
**Session Focus:** Classification Algorithm Comparison
 
---
 
### Session Summary
Building on Day 11's Logistic Regression model, the session introduced three more classification algorithms - Naive Bayes, K-Nearest Neighbors (KNN), and Support Vector Machine (SVM) - and trained all three on the same Teen Mental Health dataset (predicting Depressed/Not Depressed from social media hours, sleep hours, academic performance, stress, anxiety, and addiction level), so their accuracy and behavior could be directly compared side by side.
 
**Trainer's Notes (Colab):** [Day 12 Notes](https://colab.research.google.com/drive/18R61tX4X_RBEh79kUJpXe_TUqo72gMbc?usp=sharing)
 
---
 
### Topics Covered
 
- **Naive Bayes**
A probabilistic algorithm based on Bayes' Theorem - predicts the class with the highest probability given the input features. Very fast, works well on small datasets, and excellent for text classification (like spam detection), but assumes features are independent, which hurts accuracy when features are correlated. On the Teen Mental Health dataset, it reached about 99.2% accuracy.
 
- **K-Nearest Neighbors (KNN)**
Predicts the class of a new point by majority vote among its K nearest neighbors (e.g., with K=3, if 2 of 3 nearest points are Class A, the new point is Class A). Simple, no real training step, good for small datasets - but slow on large datasets and sensitive to feature scaling and noise. Reached about 98.3% accuracy on the same dataset, and disagreed with Naive Bayes on one test case despite similar overall accuracy.
 
- **Support Vector Machine (SVM)**
Finds the best boundary (hyperplane) that separates classes, maximizing the margin between them. Can be **Linear** (straight boundary) or **Non-Linear** (curved boundary, for classes that overlap or enclose each other). High accuracy, works well on high-dimensional data - but slow on very large datasets and needs feature scaling. Reached about 98.3% accuracy, matching KNN.
 
- **Comparing All Three**
Naive Bayes (99.17%) edged out KNN and SVM (both 98.33%) on this dataset. A "best algorithm for the situation" guide was also shared: Naive Bayes for spam/email/medical text, KNN or SVM for student placement, Naive Bayes or SVM for medical diagnosis, SVM for image classification and face recognition, and KNN for recommendation systems.
 
---
 
## Key Learnings
- No single algorithm is universally "best" - the right choice depends on dataset size, feature correlation, and whether the problem is more probability-based, distance-based, or boundary-based.
- Similar overall accuracy doesn't mean two models agree on individual predictions, as seen when Naive Bayes and KNN/SVM disagreed on the same test case.
- Real-world algorithm choice (spam detection, face recognition, recommendations) often follows well-known patterns worth remembering, rather than needing to test everything from scratch each time.
---
 
## Reflection
Comparing three algorithms on the exact same dataset and test case made the differences between them click much faster than reading about them separately would have. It was surprising that Naive Bayes and KNN/SVM disagreed on one prediction despite all having 98%+ accuracy - a good reminder that accuracy alone doesn't tell the whole story. The "best algorithm for the situation" table feels like something worth keeping handy for the minor project.
 
---
 
[Back to Diary Home](README.md)
