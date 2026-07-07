# Week 1 - Foundations of Data Exploration

This week introduced the fundamental concepts of data exploration and Python programming that are essential for understanding data analytics and machine learning. Each day's activities and learning outcomes are documented below.

---

# Day 01 - Introduction to Data, ML & Generative AI

**Date:** 30/06/2026 <br>
**Week:** 1 · Foundational Course <br>
**Session Focus:** Foundations of Data Exploration

---

### Session Summary
The opening session provided a foundation for understanding data and its role in modern computing.
Data was defined as raw facts and observations collected from diverse sources, while **Information** was described as processed data that carries meaning and supports decision-making.
To illustrate this distinction, the trainer highlighted examples where unorganized values become insightful once structured and analyzed.

---

### Topics Covered

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
### Applications highlighted include:  
- Personalized product recommendations  
- Intelligent chatbots for customer support  
- Automated image and video generation  
- Fraud detection in financial transactions  
- Predictive analytics in healthcare diagnosis    

---

## Key Learnings
- Data becomes valuable once it's turned into Information.
- Data type and modality decide which tools/models to use later.
- ML predicts from patterns; Gen AI creates new content.

---

## Reflection
Good foundation day - the Data vs Information distinction was the clearest takeaway. Data modality and outliers still feel a bit abstract without real code, so I want to revisit them once I start working with an actual dataset.



---

# Day 02 - Python Data Types, Data Structures & Intro to Pandas

**Date:** 01/07/2026 <br>
**Week:** 1 · Foundational Course <br>
**Session Focus:** Python Fundamentals for Data Analysis

---

### Session Summary
The session moved from Python fundamentals into real data-handling tools. It began with data types and data structures, reinforced through 12 hands-on practice questions, then introduced **Pandas** as the core library for working with tabular data.

**Trainer's Notes (Colab):** [Day 02 Notes](https://colab.research.google.com/drive/1G9JkmY5zoWsuCv93gpGI79sGQvJP7U4a?usp=sharing).

---

### Topics Covered

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
More hands-on and satisfying since I could run code and see results right away. The practice questions cleared up confusion between lists, tuples, and dictionaries. Want to spend more time on DataFrames before the next session.


---

# Day 03 - Data Cleaning: Missing Values, Duplicates & Outliers

**Date:** 02/07/2026 <br>
**Week:** 1 · Foundational Course <br>
**Session Focus:** Data Cleaning Techniques

---

### Session Summary
The session covered **Data Cleaning** - the process of identifying and correcting errors, inconsistencies, and inaccuracies in raw data before analysis. All commands were demonstrated on the student dataset as a teaching example.

**Trainer's Notes (Colab):** [Day 03 Notes](https://colab.research.google.com/drive/1SDLZmZa6XtBTw_1pYRkciHwXe6opo7xc?usp=sharing)

---

### Topics Covered

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
- Missing value method (drop/mean/median/mode) depends on column type and outliers.
- Median is safer than mean when outliers are present.
- IQR method gives a repeatable way to detect outliers beyond just boxplots.

---

## Reflection
Felt like the most "real-world" session so far - clear now why cleaning always comes before analysis. Deciding which missing-value method to use still needs practice. Next step: run this same pipeline on my own dataset.



---

# Day 04 - Exploratory Data Analysis: Univariate, Bivariate & Multivariate

**Date:** 03/07/2026 <br>
**Week:** 1 · Foundational Course <br>
**Session Focus:** Exploratory Data Analysis Techniques

---

### Session Summary
The session covered Exploratory Data Analysis (EDA) in depth - starting with categorical column summaries, then moving through Univariate, Bivariate, and Multivariate analysis, correlation, sorting/filtering, and a first look at Feature Engineering. All commands were demonstrated on the student dataset as a teaching example.

**Trainer's Notes (Colab):** [Day 04 Notes](https://colab.research.google.com/drive/1LsnDcyFon_POUCja8vu8Dw2Vz5zFXpFL?usp=sharing)


---

### Topics Covered

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
- Univariate → Bivariate → Multivariate analysis build on each other.
- `groupby()` is the core tool for comparing categories against a metric.
- Correlation shows strength/direction only, not causation.

---

## Reflection
Dense session - a lot to take in across univariate, bivariate, and multivariate analysis. groupby() clicked quickly, correlation needs more practice. Next priority: apply these techniques on my own dataset.



---

# Day 05 - Data Visualization with Matplotlib & Seaborn

**Date:** 06/07/2026  
**Week:** 1 · Foundational Course  
**Session Focus:** Data Visualization Techniques  

---

### Session Summary
This session focused on **Data Visualization**, the art of representing data graphically to make patterns, relationships, and insights easier to understand. Instead of scanning through raw tables, charts such as bar graphs or scatter plots allow immediate recognition of trends. For example, comparing average CGPA by department is far more intuitive when shown as a bar chart rather than a numeric table.

We explored the differences between **Matplotlib** and **Seaborn**, practiced nearly every major chart type on the student dataset, and concluded with correlation analysis using heatmaps and pairplots. The emphasis was on choosing the right visualization for the right type of data.

**Trainer's Notes (Colab):** [Day 05 Notes](https://colab.research.google.com/drive/1q0dAmLuilpNvNx5qR24ejMlYsADrGGE4?usp=sharing)  

---

### Topics Covered

### Why Visualization Matters
Visualization is not just about making data look attractive — it is about making data **meaningful**. Key benefits include:
- Quickly understanding large datasets  
- Identifying **trends** over time  
- Detecting **outliers** that may distort analysis  
- Comparing groups or categories effectively  
- Discovering hidden relationships between variables  
- Supporting better **business and academic decisions**  

---

### Matplotlib vs Seaborn
- **Matplotlib** - basic plotting library, highly customizable, good for simple charts.
- **Seaborn** - built on top of Matplotlib, has more attractive default styles, easier statistical plots, and better integration with Pandas.
---

### Chart Selection Guide

| Chart        | Data Type             | Purpose                  |
|--------------|-----------------------|--------------------------|
| Histogram    | Numerical             | Distribution of values   |
| Boxplot      | Numerical             | Spread & outliers        |
| Countplot    | Categorical           | Frequency counts         |
| Bar Chart    | Categorical + Numeric | Group comparisons        |
| Pie Chart    | Categorical           | Percentages              |
| Line Chart   | Time Series           | Trends over time         |
| Scatter Plot | Numerical + Numerical | Relationships            |
| Heatmap      | Numerical             | Correlation matrix       |

---

### Distribution Charts
- **Histogram (`plt.hist`)**: Plotted Attendance distribution across 10 bins to observe spread.  
- **Histogram with KDE (`sns.histplot` with `kde=True`)**: Added smooth Kernel Density Estimate curve on Study Hours, highlighting concentration zones more clearly than bars alone.  

---

### Boxplots
Boxplots summarize data using **minimum, Q1, median, Q3, maximum, and outliers**.  
- Example: CGPA boxplot revealed spread and flagged unusual values.  
- Outliers appeared as dots beyond whiskers, useful for spotting anomalies.  

---

### Categorical Charts
- **Countplot (`sns.countplot`)**: Showed number of students per Department and Placement_Status.  
- **Bar Plot (`sns.barplot`)**: Displayed average CGPA and Attendance by Department (after `groupby()` summarization).  
- **Pie Chart (`df[...].value_counts().plot(kind="pie")`)**: Placement_Status percentages with `autopct="%1.1f%%"`.  

---

### Line and Area Charts
- **Line Chart (`plt.plot`)**: Average CGPA across semesters, with markers and gridlines for clarity.  
- **Area Chart (`plt.fill_between`)**: Same CGPA trend, but shaded under the line to emphasize magnitude.  

---

### Violin Plots
Violin plots combine **boxplot statistics** with **distribution shape (KDE)**.  
- Wide regions = many students in that CGPA range.  
- Narrow regions = fewer students.  
- Long violin = high variation; short violin = values clustered.  
- Used to compare CGPA distribution across departments.  

---

### Scatter Plots
- Scatter plots are used to display the relationship between two numerical variables.  
- They help in identifying patterns such as positive or negative correlations, clusters of data points, or unusual outliers. By adding color or grouping, scatter plots can also highlight differences across categories, making relationships easier to interpret visually.


---

### Correlation and Heatmaps
Correlation values range from -1 to +1:  

| Value Range       | Interpretation              |
|-------------------|-----------------------------|
| +1                | Perfect positive correlation |
| +0.7 to +0.9      | Strong positive correlation  |
| +0.3 to +0.7      | Moderate positive correlation|
| 0                 | No relationship              |
| Negative values   | Inverse relationship         |

- Example: Attendance vs CGPA correlation ≈ **+0.85** (strong positive).  
- **Heatmap (`sns.heatmap(df.corr())`)**: Visualized correlations across all numeric columns with color scale + annotations.  
- **Pairplot (`sns.pairplot`)**: Compared CGPA, Attendance, Study_Hours, Family_Income in one grid for quick relationship spotting.  

---

### Key Learnings
- Chart choice depends on data type.  
- Seaborn simplifies statistical plots.  
- Correlation shows strength, not causation.  
- Heatmaps/pairplots quickly reveal multiple relationships.  

---

### Reflection
The scatter plot of Attendance vs CGPA made correlation visually clear. The chart‑selection guide will help until choosing becomes instinctive. Violin plots were new but comparing them with boxplots clarified their meaning. Next step: apply this toolkit to my minor project dataset.

---


[Back to Diary Home](README.md)
