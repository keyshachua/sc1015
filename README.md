# SC1015: Data Science Mini Project - Airbnb Scams

School of Computer Science and Engineering\
Nanyang Technological University\
Lab Group: FCS4\
Group : 9

Members: <br/>
1. Nur Shaqilah Izyan Binte Rosli<br/>
2. Keysha Chua

---
### Description:
Welcome to our repository! This repository contains all the Jupyter Notebooks, datasets, video presentations, and the source materials/references we have utilised for the Mini Project for SC1015: Introduction to Data Science and AI.

This README provides a concise overview of what we have accomplished in this project. For a more detailed explanation and nuanced insights, we encourage you to explore the Jupyter Notebook inside this repository. It contains in-depth descriptions and additional details not mentioned in this README. For convenience, we have divided the notebooks into 5 parts which broadly relate to the 5 main sections of this project.

---
### Table of Contents:
1. [Problem Formulation](#1-Problem-Formulation)
2. [Data Preparation and Cleaning](#2-Data-Preparation-and-Cleaning)
3. [Exploratory Data Analysis](#3-Exploratory-Data-Analysis)
4. [Models](#4-Models)
5. [Data Driven Insights and Conclusion](#5-Data-Drive-Insights-and-Conclusion)
6. [References](#6-References)


---
### 1. Problem Formulation
**Our Dataset:** Airbnb for Boston with fraud detection<br/>
**Our Question:** How do we identify whether an Airbnb listing is a scam?<br/>
**Rationale:** We believe that this dataset as well as the question we pose is critically relevant in today's context. When going overseas, we usually opt to rent houses/apartments instead of booking hotel rooms since the earlier alternative is more cheaper, and valuable. Unfortunately, the scammers know that too, and thus, exploit us. People are left stranded and financially impacted. According to a survey conducted by Dwellsy, it is estimated that annual losses resulting from rental fraud could reach a staggering $16.1 billion. That’s not a small amount, and many people fall for this trick. By being able to properly identify a scam, we might be able to avoid unnecessary losses.




### 2. Data Preparation and Cleaning
In this section of our project, we prepared and cleaned our dataset to ensure that it could be effectively utilized for data analysis and applied in machine learning models later in the project. Our data cleaning process aimed to address potential issues and refine the dataset for better accuracy in detecting Airbnb listing scams. Here's a comprehensive overview of the steps we undertook:
1. Data Assessment:
- Examining Data Types: We evaluated the data types of each column with **`airbnb_data.dtypes`**. to ensure they were appropriate for our analysis.
- Identifying Unique Entries: We used **`airbnb_data.nunique()`** to determine the uniqueness of the entries, which helped in understanding the diversity of the data.
- Checking for Duplicates: We found 36 duplicated rows using **`airbnb_data.duplicated().sum()`**. These duplicates were critically assessed to determine their impact on our scam detection analysis.
2. Handling Duplicates:
- Reviewing Duplicated Rows: We isolated and reviewed the duplicated rows using **`airbnb_data[airbnb_data.duplicated()]`** to understand their characteristics.
- Decision on Duplicates: After careful consideration, we decided to retain these duplicated rows. Our rationale was that multiple listings might indicate a higher possibility of fraudulent activity, which is central to our analysis.
3. Data Structuring for Analysis:
- Feature Selection: As of now, we selected all 20 variables except for **`Fraud`** as features, with **`Fraud`** as the predictor.
4. Descriptive Statistics:
- Summary Statistics: We generated descriptive statistics for the features using **`features.describe()`** to gain insights into the central tendency and variability of our data.
  
This methodical approach to data preparation has set a robust foundation for the subsequent phases of our analysis, where these clean and structured datasets will be utilised to build and evaluate models for detecting fraudulent Airbnb listings.

### 3. Exploratory Data Analysis
In order to better understand our data, we printed out some visualisation. Are there any patterns? Are there any valuable relationships between the predictor and the responses? What can we deduce from all these visualisations?
To achieve our analysis objectives, we did the following:
- Explored **`Correlation Matrix`** : To better understand the relationships between different features.
- Explored **`Principal Component Analysis (PCA)`** : To reduce dimensionality and identify the most significant feature
- Explored **`Resampling`** : To avoid data leaking and overfitting as current existing dataset was imbalanced
For further findings and explanations, please refer to the Jupyter Notebook on EDA.

### 4. Models
With the 8 columns (derived from PCA and our understanding) as well as applied weighted accuracy, we then trained various models:
- **`Decision Tree`**
- **`Random Forest`**
- **`Logistic Regression`**
- **`K-Nearest Neighbours`**
  
The reasons for this are:
- **`Decision Tree`**: Chosen for its simplicity and interpretability. Decision Trees are beneficial for our context as they provide clear decision paths and are easily understandable, which is helpful for making informed decisions.
- **`Random Forest`**: Chosen for its robustness and effectiveness in handling outliers and imbalanced data, which is typical in fraud detection scenarios. Random Forest, an ensemble of decision trees, typically achieves higher accuracy and better generalisation compared to a single decision tree.
- **`Logistic Regression`**: Chosen for its efficiency in binary classification problems. Logistic Regression is a straightforward approach that outputs probabilities associated with each classification. This model can provide insights into the likelihood of a listing being a scam, which is helpful for risk assessment.
- **`K-Nearest Neighbours (KNN)`**: Chosen for its ability to adapt quickly to changes, which is ideal in a dynamic marketplace like Airbnb. KNN is a non-parametric method that we used to capture the intuition that similar listings (in terms of features) often have similar legitimacy.

In general, in this section, we mainly focused on:
- **`Model Training`**: Train each model on the training dataset.
- **`Model Evaluation`**: Evaluate the models using appropriate metrics such as accuracy, precision, recall, and F1-score to determine each model’s effectiveness in detecting fraudulent listings. Visualise these results with a confusion matrix.
(**Parameters were chosen using Cross-Validation, GridSearchCV)

Analysing the results of the various models has helped us identify the best-performing model based on the defined metrics, thereby guiding future decisions on model deployment for scam detection. 
That model is **`Decision Tree`**.


### 5. Data Driven Insights & Conclusion
In this section, we gathered insights through the model analysis.
**`Feature Importance`** : How much each feature contributed towards the decision tree model in predicting for fake/real listings.
The feature that contributed most to Decision Tree is : number_of_reviews.

We also dived into analysing the features we used to see what insights we could discover.

In conclusion we learnt:
- How to apply different varieties of Machine Learning Models for a specific problem
- Importance of Data Quality for model training
- Different ways to improve our model’s performance
- Variety of ways to interpret a model’s performance


### 6. References
[https://www.kaggle.com/datasets/hawkingcr/airbnb-for-boston-with-fraud-detection](https://www.kaggle.com/datasets/hawkingcr/airbnb-for-boston-with-fraud-detection)
[https://commercialobserver.com/2023/07/rental-fraud-housing-rentspree/#:~:text=The%20survey%20findings%20show%20that,billion%2C%20according%20to%20the%20survey.](https://commercialobserver.com/2023/07/rental-fraud-housing-rentspree/#:~:text=The%20survey%20findings%20show%20that,billion%2C%20according%20to%20the%20survey.)


