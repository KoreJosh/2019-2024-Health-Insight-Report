# Health-Insight-from-2019--2024

![](https://github.com/KoreJosh/2019-2024-Health-Insight-Report/blob/main/health%20gam.png)

---

# Introduction

This project involves a comprehensive analysis of healthcare data from 2019 to 2024. The analysis was carried out in two phases: data cleaning and visualization. The data cleaning phase was executed using Python, while the visualization was created using Tableau. The primary goal of this project is to gain insights into various health-related metrics such as the number of health cases, hospital and doctor counts, patient demographics, medical conditions, and more.

---

# Data Cleaning with Python

The data cleaning process was performed in a Jupyter Notebook, using the Pandas library for data manipulation and cleaning. Here are the detailed steps:

1. **Loading the Data:**
   ```python
   import pandas as pd
   df = pd.read_csv('health_data.csv')
   ```

2. **Understanding the Data:**
   We begin by understanding the structure and basic statistics of the dataset.
   ```python
   df.info()
   df.describe()
   df.columns
   ```

3. **Handling Missing Values:**
   Missing values were identified and handled appropriately.
   ```python
   df.isnull().sum()
   df = df.dropna()  # Alternatively, fillna() could be used depending on the context
   ```

4. **Data Type Conversion:**
   Ensuring that each column has the correct data type.
   ```python
   df['Date of Admission'] = pd.to_datetime(df['Date of Admission'])
   df['Discharge Date'] = pd.to_datetime(df['Discharge Date'])
   df['Year of Admission'] = df['Date of Admission'].dt.year
   df['Month of Admission'] = df['Date of Admission'].dt.month
   df['Day of Admission'] = df['Date of Admission'].dt.day_name()
   df['Duration of Stay'] = df['Discharge Date'] - df['Date of Admission']
   ```

5. **Creating Additional Features:**
   Additional features were created to enhance the dataset.
   ```python
   df['Age Group'] = pd.cut(df['Age'], bins=[0, 18, 35, 60, 100], labels=['Teenager', 'Adult', 'Senior', 'Elderly'])
   ```

6. **Saving the Cleaned Data:**
   The cleaned dataset was saved for further analysis.
   ```python
   df.to_csv('cleaned_health_data.csv', index=False)
   ```

---

# Visualization with Tableau

After cleaning the data, Tableau was used to create interactive and insightful visualizations. The dashboards were designed to provide a holistic view of the healthcare data across various dimensions.

**Dashboard 1: Overview**

- **Health Cases, Hospitals, Doctors, and Insurance Providers:**
  The total counts of health cases, hospitals, doctors, and insurance providers are displayed at the top.
  - Health Cases: 55,500
  - Number of Hospitals: 39,876
  - Number of Doctors: 40,341
  - Number of Insurance Providers: 5

- **Gender Distribution:**
  A pie chart visualizing the gender distribution of patients.
  - Male: 27,774
  - Female: 27,726

- **Medical Condition by Year:**
  A stacked area chart showing the number of different medical conditions over the years from 2019 to 2024.

- **Blood Group Distribution:**
  A bubble chart representing the distribution of different blood groups among patients.

- **Age Group Distribution:**
  A bar chart showing the number of patients in different age groups.
  - Teenager: 1,693
  - Adult: 24,309
  - Senior: 17,087
  - Elderly: 12,411

- **Medical Condition Counts:**
  A bar chart showing the count of different medical conditions such as Arthritis, Asthma, Cancer, Diabetes, Hypertension, and Obesity.

- **Admission Type:**
  A treemap showing the distribution of admission types (Elective, Emergency, Urgent).

**Dashboard 2: Financial Insights**

- **Medical Condition Billing:**
  A bar chart displaying the billing amounts for different medical conditions.

- **Insurance Billing:**
  A bar chart showing the billing amounts covered by different insurance providers.

- **Insurance for Medical Conditions:**
  A bar chart representing the coverage provided by different insurance providers for various medical conditions.

- **Medication for Medical Conditions:**
  A dot plot illustrating the medications prescribed for different medical conditions.

**Dashboard 3: Hospital and Doctor Insights**

- **Top 15 Hospitals by Insured Patients:**
  A bar chart listing the top 15 hospitals based on the number of insured patients.

- **Top 10 Hospitals by Room Count:**
  A bar chart showing the top 10 hospitals based on room count.

- **Top 10 Doctors Based on Medical Condition:**
  A stacked bar chart highlighting the top 10 doctors based on the medical conditions they treat.

- **Test Results by Medical Condition:**
  A bar chart displaying the test results for various medical conditions.

---

#### Insights

1. **Gender and Age Distribution:**
   The data is nearly evenly split between male and female patients. Adults constitute the largest age group, followed by seniors and elderly patients.

2. **Medical Conditions Trends:**
   The number of medical conditions fluctuates over the years, with notable increases in some conditions like Diabetes and Hypertension.

3. **Admission Types:**
   Emergency and urgent admissions are significantly higher than elective admissions, indicating a high volume of critical cases.

4. **Financial Insights:**
   Cancer and Diabetes have the highest billing amounts, highlighting the financial burden of these diseases. Insurance billing varies widely across providers, with UnitedHealthcare and Medicare covering the highest amounts.

5. **Hospital and Doctor Performance:**
   Certain hospitals and doctors consistently appear as top performers in terms of patient numbers and medical condition management.

 🏥📊 See & interacte with the trends.👉[Check it out!](https://bit.ly/3KJilyh)  
---

### Conclusion

In this project I demonstrated the power of data cleaning and visualization in deriving actionable insights from healthcare data. The combination of Python and Tableau allowed for efficient data processing and the creation of interactive dashboards that presented complex data in an easily understandable format. This portfolio piece showcases the capability to handle large datasets, clean and preprocess data, and generate meaningful visualizations to drive decision-making in the healthcare industry.
### Futhermore
Still to come is a predictive model on the dataset
