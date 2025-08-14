🧑‍💼 HR Analytics Dashboard – Power BI

This project showcases an interactive HR Analytics Dashboard built in Power BI to analyze employee attrition, demographics, and job satisfaction trends.
The goal is to help HR teams make data-driven decisions to reduce turnover and improve retention.

## 📊 Dashboard Preview
![HR Analytics Dashboard](https://github.com/Stefan-git-web/HR-Analytics-dashboard/blob/main/Screenshot%202025-08-14%20172143.png)


🚀 Features

Key Performance Indicators (KPIs):

Total Employees

Total Attrition Count

Attrition Rate (%)

Average Age

Average Monthly Salary

Average Years at Company

Attrition Analysis:

By Gender

By Education Field

By Age Group

By Salary Slab

By Years at Company

By Job Role

Employee Feedback by Job Role

Interactive Department Filter (Human Resources, R&D, Sales)

📂 Dataset

The dataset contains:

Employee demographics (Age, Gender, Education, Salary, Years at Company)

Job-related details (Role, Department, Feedback score)

Attrition indicator

Salary Slabs & Education Fields

🛠 Steps Followed
1️⃣ Data Loading & Cleaning

Imported dataset into Power BI

Removed duplicates and handled null values

Verified correct data types for each field (Date, Number, Text)

2️⃣ Data Modelling

Created relationships between Fact Table: Employee Attrition and Dimension Tables: Departments, Job Roles, Education Fields

Implemented a Star Schema model

3️⃣ Visualizations

Cards for KPIs

Donut Chart – Attrition by Education Field

Clustered Bar Chart – Attrition by Age Group, Salary Slab, Job Role

Matrix Table – Employee Feedback by Job Role

Line Chart – Attrition by Years at Company

Slicers – Department filter

4️⃣ Formatting

Used red-themed gradient background

Added legends, labels, and consistent color schemes

Organized visuals for intuitive analysis

💡 Key Insights

Total Employees: 1,470

Attrition Count: 237 (16.1% rate)

Highest attrition age group: 26–35 years (116 employees)

Top attrition job role: Sales Executive (57 employees)

Education field with highest attrition: Life Sciences (37.55%)

Highest attrition salary slab: Up to 5k

Most attrition occurs within 1 year of joining (59 employees)

Male attrition higher (140) than female (79)

🛠 Tools Used

Power BI – Data modeling & visualization

Excel / CSV – Data source

📐 DAX Measures

KPIs

Count of Employees = COUNTROWS(Employees)

Attrition = CALCULATE(
    COUNTROWS(Employees),
    Employees[Attrition] = "Yes"
)

Attrition Rate = DIVIDE([Attrition], [Count of Employees], 0)

Avg Age = AVERAGE(Employees[Age])

Avg Salary = AVERAGE(Employees[MonthlyIncome])

Avg Years = AVERAGE(Employees[YearsAtCompany])


Attrition by Category

Attrition Count = CALCULATE(
    COUNTROWS(Employees),
    Employees[Attrition] = "Yes"
)

Attrition % by Field = DIVIDE(
    [Attrition Count],
    CALCULATE([Attrition Count], ALL(Employees[EducationField])),
    0
)


Feedback Total

Total Feedback = SUM(Employees[Feedback])

