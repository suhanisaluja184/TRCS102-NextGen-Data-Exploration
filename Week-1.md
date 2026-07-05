# Week 1 - Foundations of Data Exploration

This week introduced the fundamental concepts of data exploration and Python programming that are essential for understanding data analytics and machine learning. Each day's activities and learning outcomes are documented below.

---

# Day 01 - Introduction to Data, ML & Generative AI

**Date:** 30/06/2026
**Week:** 1 · Foundational Course
**Session Focus:** Foundations of Data Exploration

---

### Session Summary
The opening session provided a foundation for understanding data and its role in modern computing.
Data was defined as raw facts and observations collected from diverse sources, while **Information** was described as processed data that carries meaning and supports decision-making.
To illustrate this distinction, the trainer highlighted examples where unorganized values become insightful once structured and analyzed.

---

### Types of Data
The session categorized data into multiple forms:
- **Structured Data** - neatly organized in rows and columns, such as relational databases.
- **Semi-Structured Data** - flexible schema formats like JSON or XML.
- **Unstructured Data** - free-form content such as images, videos, or text documents.

Additionally, the difference between **Numerical Data** (quantitative values like age or salary) and **Categorical Data** (qualitative labels like gender or country) was explained.

---

### Data Modality
- Data can exist in multiple forms, each requiring specialized techniques for analysis and machine learning.  
- **Text** captures written or spoken language and is widely used in NLP tasks.  
- **Images** represent visual information, often analyzed with computer vision methods.  
- **Audio** stores sound patterns, enabling speech recognition and acoustic analysis.  
- **Video** combines sequential visuals and audio, requiring temporal and spatial modeling.  
- **Tabular data** is structured in rows and columns, common in databases and spreadsheets.  
- **Time‑series data** records values across time intervals, essential for forecasting and trend analysis.
   
Recognizing these modalities is crucial because the choice of algorithms, preprocessing methods, and models depends heavily on the nature of the data being handled. 

---

### Exploration & Outliers
The trainer stressed the importance of **Data Exploration** as the first step in any data-science project.
Exploration helps identify missing values, outliers, relationships, and patterns before applying algorithms.
The concept of **Outliers** was discussed with examples, showing how unusual observations can distort statistical analysis and model performance.

---

### Machine Learning & Generative AI  
- The session concluded with an introduction to **Machine Learning (ML)** and **Generative AI**.  
- **Machine Learning (ML)** enables computers to learn patterns from data and make predictions.  
- **Generative AI** focuses on creating new content such as text, images, audio, and code.  
- Applications highlighted include:  
  - Personalized product recommendations  
  - Intelligent chatbots for customer support  
  - Automated image and video generation  
  - Fraud detection in financial transactions  
  - Predictive analytics in healthcare diagnosis  
- **Example – Amazon Collaboration:**  
  Amazon uses ML and Generative AI to collaborate with different business companies by hosting their products on its marketplace.  
  - **Recommendation systems** suggest relevant products to customers based on browsing and purchase history.  
  - **Generative AI tools** help sellers create product descriptions, images, and marketing content.  
  - **Fraud detection models** protect both Amazon and partner businesses from fraudulent activities.  
  This collaboration allows small and large companies to reach global customers while leveraging Amazon’s AI‑powered ecosystem.  

---

## Key Learnings
- Data becomes valuable only once it's turned into Information.
- Data type and modality decide which tools/models to use later.
- Outliers can be errors *or* important insights - always worth investigating.
- ML predicts from patterns; Gen AI creates new content - different goals.

---

## Reflection
Day 1 set a good foundation - the Data vs Information distinction made a lot of things click, especially why raw numbers alone don't mean much until they're organized. The data modality and outlier concepts felt a little abstract without seeing real code yet, so I want to revisit these once I actually work with a dataset. Looking forward to connecting today's theory with hands-on practice in the next few days.



---

# Day 02 - Python Data Types, Data Structures & Intro to Pandas

**Date:** 01/07/2026
**Week:** 1 · Foundational Course
**Session Focus:** Python Fundamentals for Data Analysis

---

### Session Summary
The session moved from Python fundamentals into real data-handling tools. It began with data types and data structures, reinforced through 12 hands-on practice questions, then introduced **Pandas** as the core library for working with tabular data.

**Trainer's Notes (Colab):** [Day 02 Notes](https://colab.research.google.com/drive/1G9JkmY5zoWsuCv93gpGI79sGQvJP7U4a?usp=sharing).

---

### Data Types in Python
Python needs to know what kind of data it's handling before it can process it:
- **Integer (`int`)** - whole numbers, e.g., `age = 21`
- **Float (`float`)** - decimal values, e.g., `salary = 55000.75`
- **String (`str`)** - text values, e.g., `name = "Aman"`
- **Boolean (`bool`)** - `True` / `False` values, e.g., `is_placed = True`

---

### Python Data Structures
Since data analytics rarely works with single values, four core collection types were covered:
- **List** - ordered, mutable, created with `[]`; allows duplicates and mixed types (e.g., `marks = [78, 85, 90, 67, 88]`).
- **Tuple** - ordered, immutable, created with `()`; memory-efficient (e.g., `months = ("Jan", "Feb", "Mar")`).
- **Dictionary (`dict`)** - unordered key-value pairs, created with `{key: value}`; keys must be unique (e.g., `student = {"Name": "Aman", "CGPA": 8.4}`).
- **Set** - unordered, unique elements only, created with `{}` or `set()`; automatically removes duplicates.

---

### Practice Questions
12 practice questions were solved covering data types, lists, tuples, dictionaries, and sets - including attendance eligibility, Rock-Paper-Scissors game, unique list elements, and dictionary operations.

**Full code & solutions:** [Day 02 Practice Notebook](https://colab.research.google.com/drive/1pu-fgPR6PvUC5K3kCRDFvSBzZwPwMGeo?usp=sharing)

---

### Introduction to Pandas
- **Series** - a single column of data (e.g., `pd.Series([21, 22, 23, 24])`).
- **DataFrame** - a full table similar to an Excel sheet, built from a dictionary of columns (e.g., Name, Age, Marks).
- `df.dtypes` was used to check the data type of each column.

---

## Key Learnings
- Choosing the right data structure (List/Tuple/Dict/Set) depends on whether you need order, mutability, or uniqueness.
- Practicing small logic problems builds the foundation needed for real data manipulation later.
- Pandas turns raw CSV data into a structured DataFrame that's easy to clean and analyze.

---

## Reflection
Today felt more hands-on and satisfying since I could actually run code and see outputs immediately. The 12 practice questions helped reinforce when to use a list vs a tuple vs a dictionary - I was mixing these up before. The Rock-Paper-Scissors exercise was the most fun and made loops and conditionals feel less mechanical. Pandas Series and DataFrames still feel new; I want to spend more time exploring DataFrame operations before the next session.



---

# Day 03 - Data Cleaning: Missing Values, Duplicates & Outliers

**Date:** 02/07/2026
**Week:** 1 · Foundational Course
**Session Focus:** Data Cleaning Techniques

---

### Session Summary
The session covered **Data Cleaning** - the process of identifying and correcting errors, inconsistencies, and inaccuracies in raw data before analysis. All commands were demonstrated on the student dataset as a teaching example.

**Trainer's Notes (Colab):** [Day 03 Notes](https://colab.research.google.com/drive/1SDLZmZa6XtBTw_1pYRkciHwXe6opo7xc?usp=sharing)

> **Action Item:** Apply all the commands below on my own minor project dataset, not just the student dataset used for demonstration.

---

### Missing Values
Missing values occur when no data is recorded for a particular observation (e.g., a student absent, sensor failure, or a skipped survey question). Detected using `df.isnull()` and `df.isnull().sum()`.

**Four ways to handle them:**
- **Remove Row** (`df.dropna()`) - good when only a few records are affected.
- **Fill with Mean** - best for numerical columns (e.g., Age, CGPA).
- **Fill with Median** - best when outliers are present (e.g., Attendance).
- **Fill with Mode** - best for categorical data (e.g., Gender, City).

---

### Duplicate Rows
- Checked with `df.duplicated()` and counted with `df.duplicated().sum()`.
- Removed using `df.drop_duplicates()`.

---

### Cleaning Text Data
- **Standardizing case** - e.g., fixing "Male", "male", "MALE" inconsistencies with `.str.title()`.
- **Removing extra spaces** - using `.str.strip()`.
- **Converting to uppercase** - using `.str.upper()` (used for Department codes).

---

### Outliers
An outlier is an observation that is significantly different from the rest of the data. Two detection methods were covered:
- **Boxplot** - visual method using Seaborn (`sns.boxplot`).
- **IQR Method** - calculate Q1, Q3, and IQR (`Q3 - Q1`); any value below `Q1 - 1.5xIQR` or above `Q3 + 1.5xIQR` is flagged as an outlier.
- Outlier rows were filtered out to create a clean dataset (`df_clean`), and the final cleaned data was exported using `df.to_csv()`.

---

## Key Learnings
- There's no single "correct" way to handle missing values - the right method (drop/mean/median/mode) depends on the column type and whether outliers are present.
- Median is safer than mean for filling missing values when a column has outliers.
- Text data needs cleaning too - inconsistent casing or spacing can silently break groupings and filters.
- The IQR method gives a repeatable, non-visual way to detect outliers, useful when boxplots aren't practical for many columns.
- These aren't just demo commands - the real task is applying this exact cleaning pipeline on my own minor project dataset.

---

## Reflection
Data cleaning felt like the most 'real-world' session so far - it's clear now why every data project starts here instead of jumping straight to analysis. The four ways to handle missing values (drop/mean/median/mode) made sense individually, but deciding which one to use on my own dataset still needs practice. The IQR method for outliers was new and felt more systematic than just eyeballing a boxplot. Need to actually run this whole cleaning pipeline on my minor project dataset before the next session, as instructed.



---

# Day 04 - Exploratory Data Analysis: Univariate, Bivariate & Multivariate

**Date:** 03/07/2026
**Week:** 1 · Foundational Course
**Session Focus:** Exploratory Data Analysis Techniques

---

### Session Summary
The session covered Exploratory Data Analysis (EDA) in depth - starting with categorical column summaries, then moving through Univariate, Bivariate, and Multivariate analysis, correlation, sorting/filtering, and a first look at Feature Engineering. All commands were demonstrated on the student dataset as a teaching example.

**Trainer's Notes (Colab):** [Day 04 Notes](https://colab.research.google.com/drive/1LsnDcyFon_POUCja8vu8Dw2Vz5zFXpFL?usp=sharing)

> **Action Item:** Apply all the commands below on my own minor project dataset, not just the student dataset used for demonstration.

---

### Categorical Column Summaries
Before deeper analysis, categorical columns were explored using:
- `.unique()` - lists all distinct values in a column (e.g., Department).
- `.nunique()` - counts how many distinct values exist.
- `.value_counts()` - shows frequency of each category (used on Department, City, Gender, Placement_Status).

---

### Univariate Analysis
Univariate means analyzing one variable at a time. Applied on CGPA using `.mean()`, `.mode()`, `.median()`, `.max()`, and `.min()` to understand its central tendency and spread.

---

### Bivariate Analysis
Bivariate means studying the relationship between two variables, mainly using `groupby()` - a pandas method that splits a DataFrame into groups based on column values.
- Department vs average CGPA
- Department vs average Attendance
- Placement_Status vs average CGPA
- Department vs average Study_Hours

---

### Multivariate Analysis
Multivariate means studying relationships among multiple variables at once.
- Grouped Department against both CGPA and Attendance together.
- **Crosstab** - `pd.crosstab()` gives a tabular summary showing how often combinations of two categories (Department and Placement_Status) occur together.

---

### Correlation
`df.corr(numeric_only=True)` measures how strongly and in what direction two numeric variables move together:
- **+1.0** - perfect positive correlation (both increase together).
- **-1.0** - perfect negative correlation (one increases, other decreases).
- **0.0** - no linear correlation between the variables.

---

### Sorting and Filtering
- `sort_values(by="CGPA", ascending=False)` - highest CGPA on top.
- `sort_values(by="Attendance")` - lowest Attendance on top.
- `nlargest(10, "CGPA")` - top 10 students by CGPA.
- Conditional filtering used to extract specific groups: students with CGPA > 9, placed students, hostel residents, and students from a specific city (Delhi).

---

### Feature Engineering (Introduction)
Feature engineering means generating entirely new variables from existing data. Two new columns were created:
- **Excellent** - a True/False column based on whether CGPA >= 9.
- **Scholarship** - a True/False column based on combined conditions (CGPA >= 8.5 AND Attendance >= 90).

---

## Key Learnings
- Univariate, Bivariate, and Multivariate analysis build on each other - start with one variable, then two, then several together.
- `groupby()` is the core tool for comparing categories against a numeric measure.
- Correlation values only capture linear relationships, and don't imply causation.
- Feature engineering often starts as a simple boolean condition on existing columns, not something complicated.
- Filtering and sorting are as important as summary statistics for actually understanding a dataset.

---

## Reflection
This was a dense session - univariate, bivariate, and multivariate analysis in one day took a bit of re-reading to keep straight. groupby() clicked well since it's similar to pivot tables I've used before. The crosstab and correlation sections were useful but I'd like more practice interpreting correlation values in a real dataset rather than just reading the numbers. Feature engineering felt easier than expected - creating True/False columns from conditions is intuitive. Applying all of today's techniques on my own dataset is the next priority.



---
 
[Back to Diary Home](README.md)
