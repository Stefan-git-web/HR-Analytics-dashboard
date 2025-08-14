# 🧑‍💼 HR Analytics Dashboard – Power BI

This project presents an **interactive HR Analytics Dashboard** built in **Power BI** to track employee attrition trends, demographic patterns, and satisfaction levels.  
The dashboard helps HR teams make data-driven decisions to reduce turnover and improve employee retention.

---

## 🚀 Features
- **KPIs**:
  - Total Employees
  - Total Attrition Count
  - Attrition Rate
  - Average Age
  - Average Salary
  - Average Years in Company
- **Attrition breakdowns**:
  - By Gender
  - By Education Field
  - By Age Group
  - By Salary Slab
  - By Years at Company
  - By Job Role
- **Employee Feedback** scores by Job Role
- Interactive **Department filter** for Human Resources, Research & Development, Sales

---

## 📂 Dataset
The dataset contains:
- Employee demographic details (age, gender, education, salary, years at company)
- Job-related data (role, department, feedback score)
- Attrition indicator
- Salary Slabs
- Education fields

---

## 🛠 Steps Followed

### 1️⃣ Data Loading & Cleaning
- Imported dataset into Power BI
- Removed duplicates and null values
- Verified data types for each column (Date, Number, Text)

### 2️⃣ Data Modelling
- Created relationships between tables (Fact Table: Employee Attrition, Dimensions: Departments, Job Roles, Education Fields)
- Ensured a **Star Schema** model

#  3️⃣ Visualization

Card visuals for KPIs

Donut Chart for Attrition by Education Field

Clustered Bar Chart for Attrition by Age Group, Salary Slab, Job Role

Matrix Table for Employee Feedback by Job Role

Line Chart for Attrition by Years at Company

Slicers for Department filter

# 4️⃣ Formatting

Used red-themed gradient background

Added clear legends and labels

Kept consistent visual order for easy analysis

# 💡 Insights

Total Employees: 1,470, with 237 attrition cases (16.1% rate)

Highest attrition age group: 26–35 years (116 employees)

Top attrition job role: Sales Executive (57 employees)

Education field with highest attrition: Life Sciences (37.55%)

Highest attrition salary slab: Up to 5k

Most attrition occurs within 1 year of joining (59 employees)

Males have higher attrition (140) compared to females (79)

# 🛠 Tools Used

Power BI for data modeling & visualization
Excel/CSV as the data source

### 5️⃣ DAX Measures
**KPIs**
```DAX
Count of Employees = COUNTROWS(Employees)

Attrition = CALCULATE(COUNTROWS(Employees), Employees[Attrition] = "Yes")

Attrition Rate = DIVIDE([Attrition], [Count of Employees], 0)

Avg Age = AVERAGE(Employees[Age])

Avg Salary = AVERAGE(Employees[MonthlyIncome])

Avg Years = AVERAGE(Employees[YearsAtCompany])

# Attrition by Category
Attrition Count = CALCULATE(COUNTROWS(Employees), Employees[Attrition] = "Yes")
Attrition % by Field = DIVIDE([Attrition Count], CALCULATE([Attrition Count], ALL(Employees[EducationField])), 0)

### Feedback Total
Total Feedback = SUM(Employees[Feedback])

