# IBM HR Analytics: Employee Attrition Prediction 👥📉

![R](https://img.shields.io/badge/R-276DC3?style=for-the-badge&logo=r&logoColor=white)
![ggplot2](https://img.shields.io/badge/ggplot2-276DC3?style=for-the-badge&logo=r&logoColor=white)
![Logistic Regression](https://img.shields.io/badge/Model-Logistic_Regression-F2C811?style=for-the-badge)

## 📌 Executive Summary
Employee turnover (attrition) is a critical challenge for human resources departments. This project leverages the **IBM HR Employee Attrition and Performance dataset** to analyze the factors influencing employee departures and builds a predictive model to identify at-risk employees[cite: 1]. By utilizing Exploratory Data Analysis (EDA) and Logistic Regression in **R**, this project aims to help HR departments develop data-driven strategies to enhance employee engagement and reduce attrition rates[cite: 1].

## 📊 Dataset Overview
* The dataset consists of **1,470 observations and 35 variables**[cite: 1].
* Features include demographics (Age, DistanceFromHome), job roles (Department, BusinessTravel), and performance metrics[cite: 1].
* **Data Quality:** A thorough check confirmed there are absolutely no missing values in the dataset[cite: 1].

## 🔍 Key Insights from Exploratory Data Analysis (EDA)
Data visualizations utilizing the `ggplot2` package revealed several critical business insights[cite: 1]:
* **Departmental Distribution:** The workforce is heavily concentrated in the Research & Development (R&D) and Sales departments, with Human Resources operating with the fewest personnel[cite: 1].
* **Income vs. Attrition:** Employees who stay with the company generally have a higher median monthly income and a broader income range compared to those who leave[cite: 1]. 
* **Education & Compensation:** Salary distributions vary significantly across departments and educational backgrounds. Technical and Medical degree holders earn higher salaries in R&D and Sales, whereas Marketing and Life Sciences graduates achieve the highest pay in the Sales department[cite: 1]. The HR department consistently shows lower salary ranges across all education fields[cite: 1].

## ⚙️ Predictive Modeling (Logistic Regression)
A Logistic Regression model was developed using the `glm()` function to predict the likelihood of employee attrition[cite: 1]. 
* **Data Partitioning:** The dataset was split into 70% training and 30% testing sets using `createDataPartition()`, carefully accounting for the class imbalance[cite: 1].
* **Feature Selection:** The model was optimized using the `stepAIC()` method to eliminate insignificant variables[cite: 1].
* **Threshold Optimization:** The optimal classification threshold was determined using the Youden index on the ROC curve to maximize predictive performance[cite: 1].

## 📈 Model Performance & Evaluation
The optimized model delivered strong overall discriminative ability, though it highlights the inherent challenge of predicting minority classes in HR data:
* **AUC Score:** **0.8746**, indicating a strong ability to distinguish between employees who stay and those who leave[cite: 1].
* **Accuracy:** **82.05%**[cite: 1].
* **Sensitivity:** **80.28%**[cite: 1].
* **Negative Predictive Value (NPV):** **95.6%**, meaning the model is highly effective at identifying employees who will stay[cite: 1].
* **Positive Predictive Value (PPV):** **46.72%**. Due to the low prevalence of attrition (16.14%), the model struggles to pinpoint exact departures, misclassifying some attrition cases[cite: 1].
* **Kappa Statistic:** **0.4858**, showing moderate agreement beyond chance[cite: 1]. The McNemar's test (p-value = 1.85e-08) confirms that classification errors are not equally distributed between the two classes[cite: 1].

## 🚀 Conclusion & Business Impact
While the model perfectly identifies the stable workforce, further tuning (e.g., handling the rare positive class via advanced resampling techniques) could improve the false positive rate for predicting departures[cite: 1]. Overall, these insights provide HR leadership with a solid quantitative foundation to restructure compensation and retention strategies, particularly for vulnerable departments.
