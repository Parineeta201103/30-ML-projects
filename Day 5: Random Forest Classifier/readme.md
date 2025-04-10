# **Mental Health in Tech Survey - Day 5: Machine Learning Project**

## **Overview**
In this project, we aimed to predict whether individuals in the tech industry seek mental health treatment based on various factors, including demographics, work-related factors, and personal history. The dataset used for this analysis comes from the "Mental Health in Tech Survey," which collects responses from tech professionals regarding their mental health and treatment-seeking behaviors.

This is the 5th day of my **30 Days, 30 ML Projects** challenge, where I utilized a **Random Forest Classifier** to predict mental health treatment behavior.

## **Objective**
The goal of this project is to predict whether a tech professional is likely to seek treatment for mental health issues based on their survey responses. By identifying key features that influence treatment-seeking behavior, this project can provide insights that may inform mental health support programs in the tech industry.

## **Dataset**
The dataset contains information about:
- Demographic factors (e.g., age, gender)
- Work-related factors (e.g., remote work, work interference)
- Personal mental health history (e.g., family history of mental illness)

### **Columns:**
- **Age**: Age of the participant
- **Gender**: Gender of the participant (Male, Female, Other)
- **Self-employed**: Whether the participant is self-employed
- **Family history**: Whether the participant has a family history of mental illness
- **Work interference**: How often mental health issues interfere with work (e.g., Never, Rarely, Sometimes, Often)
- **Remote work**: Whether the participant works remotely
- **Treatment**: Target variable indicating whether the participant sought treatment for mental health issues (Yes/No)

## **Steps Taken**
### **1. Data Preprocessing**:
- Removed irrelevant columns (e.g., `Timestamp`, `comments`, `state`).
- Handled missing values by filling them with the mode (for categorical features).
- Cleaned the `Gender` column to standardize the entries (Male, Female, Other).
- Removed outliers in the `Age` column and dropped incorrect or invalid entries.
  
### **2. Exploratory Data Analysis (EDA)**:
- Visualized the distribution of `Age` and treatment-seeking behavior.
- Analyzed the relationship between **Gender**, **Family History**, **Work Interference**, **Remote Work**, and the target variable `Treatment`.
- Key findings:
  - **Females** are more likely to seek treatment than males.
  - People aged **30-50** are more likely to seek treatment than younger individuals.
  - **Work interference** with mental health leads to a higher likelihood of seeking treatment.
  - Individuals with a **family history** of mental illness are more likely to seek treatment.

### **3. Feature Engineering and Encoding**:
- Encoded categorical variables using **Label Encoding** for binary variables and **One-Hot Encoding** for multi-class variables.
- Scaled the **Age** feature using **StandardScaler** to ensure proper model performance.

### **4. Model Building**:
- Used a **Random Forest Classifier** to build the predictive model.
- Split the data into training and testing sets (80% train, 20% test).
- Evaluated model performance using:
  - **Accuracy**: 92%
  - **Confusion Matrix**: Good classification performance with no class imbalance.
  - **ROC Curve**: AUC of 0.90, indicating excellent model discrimination.

### **5. Key Visualizations**:
- **Treatment vs. No Treatment**: A bar plot showing the distribution of treatment-seeking vs non-treatment-seeking individuals.
- **Treatment by Gender**: Countplot visualizing the relationship between gender and treatment-seeking behavior.
- **Work Interference vs. Treatment**: Countplot showing how work interference affects the likelihood of seeking treatment.
- **Family History vs. Treatment**: A countplot showing that individuals with a family history of mental illness are more likely to seek treatment.

### **6. Feature Importance**:
- Identified the most important features influencing the prediction of mental health treatment:
  - **Work interference**
  - **Family history**
  - **Age**

## **Conclusion**
- **Key Insights**:
  - **Gender**: Females are more likely to seek treatment compared to males.
  - **Age**: Individuals aged 30-50 are more likely to seek treatment than younger individuals.
  - **Work Interference**: Those who report that mental health issues interfere with their work are more likely to seek treatment.
  - **Family History**: Respondents with a family history of mental illness are more likely to seek treatment.
- The model performed well with an accuracy of 92%, and the ROC curve suggests strong classification ability.

