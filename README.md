# **Data Jobs Dashboard**

![](/assets/dashboard_gif.gif)

## **Introduction**

 This dashboard was created to help those looking for jobs in the data field. It contains some useful filters such as country, job type and title.

The dataset used is from 2023 and contains detailed information about positions in the data area such as:

- 👨‍💼 **Job titles**
- 💰 **Salaries**
- 📍 **Locations**

### **Dashboard File**

My final dashboard is [Dashboard.xlsx](/Dashboard.xlsx).

### **Excel Skills Used**

- 📉 **Charts**
- 🧮 **Formulas and Functions**
- ❎ **Data Validation**

## **Dashboard Build**

### 📊 **Data Science Job Salaries**

![](/assets/data_title_salary.PNG)

- 🛠️ **Excel Features:** Utilized bar chart feature (with formatted salary values) and optimized layout for clarity.
- 🎨 **Design Choice:** Horizontal bar chart for visual comparison of median salaries.
- 📉 **Data Organization:** Sorted job titles by descending salary for improved readability.
- 💡 **Insights Gained:** This enables quick identification of salary trends, noting that data scientists have the lowest salary among other data professions in Brazil.

#### 🧮 **Formulas and Functions**

```excel
=MEDIAN(
  IF(
    (jobs[job_title_short]=A2)*
    (jobs[salary_year_avg]<>0)*
    (jobs[job_country]=country)*
    (ISNUMBER(SEARCH(type;jobs[job_schedule_type])));
    jobs[salary_year_avg]
  )
)
```

- 🔍 **Multi-Criteria Filtering:** Checks job title, country, schedule type, and excludes blank salaries.
- 📊 **Array Formula:** Utilizes `MEDIAN()` function with nested `IF()` statement to analyze an array.
- 🎯 **Tailored Insights:** Provides specific salary information for job titles, regions, and schedule types.

### 🗺️ **Country Median Salaries**

![](/assets/map_gif.gif)

- 🛠️ **Excel Features:** Utilized Excel's map chart feature to plot median salaries globally.
- 🎨 **Design Choice:** Color-coded map to visually differentiate salary levels across regions.
- 📊 **Data Representation:** Plotted median salary for each country with available data.
- 👁️ **Visual Enhancement:** Improved readability and immediate understanding of geographic salary trends.
- 💡 **Insights Gained:** Enables quick grasp of global salary disparities and highlights high/low salary regions.

### ⏰ **Job Schedule Type Salaries and Count**

![](/assets/data_schedule_salary.PNG)

- 🛠️ **Excel Features:** Utilized bar chart feature (with formatted salary values) and optimized layout for clarity.
- 🎨 **Design Choice:** Horizontal bar chart for visual comparison of median salaries.
- 📉 **Data Organization:** Sorted job schedule types by descending salary for improved readability.

#### 🧮 **Formulas and Functions**

```excel
=FILTER(J2#,(NOT(ISNUMBER(SEARCH("and",J2#))+ISNUMBER(SEARCH(",",J2#))))*(J2#<>0))
```

- 🔍 **Unique List Generation:** This Excel formula below employs the `FILTER()` function to exclude entries containing "and" or commas, and omit zero values.

## ❎ **Data Validation**

![](/assets/data_validation_gif.gif)

- 🔒 **Enhanced Data Validation:** Implementing the filtered list as a data validation rule under the Job Title, Country, and Type option in the Data tab ensures:
    - 🎯 User input is restricted to predefined, validated schedule types.
    - 🚫 Incorrect or inconsistent entries are prevented.
    - 👥 Overall usability of the dashboard is enhanced.

## **Conclusion**

This dashboard gives us some quick insights into average salaries filtered by country, job title, and programming type. It’s useful for anyone looking for a job in the data field and need some useful information.