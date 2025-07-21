# University-ETL-DW
University academic performence Data Warehouse 📊🎓

> A complete Data Warehousing and Business Intelligence (DW & BI) solution developed for analyzing university academic data.

## 📌 Project Overview

This project simulates a real-world academic performance analytics system built for a fictitious institution, **TechVerse University**. It leverages a full DW & BI pipeline — from **ETL** to **cube processing** to **interactive Power BI dashboards** — offering insights into student performance, course trends, feedback analytics, and more.

## 🗃️ Dataset

The dataset includes over **3,000 synthetic records** covering:
- Student profiles
- Course offerings
- Enrollments
- Grades & GPA
- Attendance logs
- Lecturer information
- Student feedback

📂 Dataset Link: [Click here to view](https://mysliit-my.sharepoint.com/:f:/g/personal/it22118936_my_sliit_lk/ElwkuxTO6U5Jj82hnSwWpukBnqVlqu-LbbfHEuxgwEM1dw?e=isi56h)

---

## 🏗️ Solution Architecture

### 📚 Source Database
- Name: `University_DataSourceDB`
- Imported `.csv`, `.txt`, and `.xlsx` files using **Flat File Import** and **Import Data Wizard**

### ⭐ Data Warehouse
- Name: `University_DataSource_DW`
- Designed in **Star Schema**
- Includes slowly changing dimension (`DimStudent` as SCD Type 2)

#### 🔹 Dimension Tables:
- `DimStudent`
- `DimCourse`
- `DimLecturer`
- `DimGrade`
- `DimDate`
- `DimSemester`
- `DimFeedbackCategory`

#### 🔸 Fact Table:
- `Fact_Student_Performance`  
  Stores GPA, feedback scores, dropout flag, timestamps, and derived performance metrics.

---

## 🔄 ETL Process (SSIS)

- Developed using **Stored Procedures** and **Data Flow Tasks**
- Applied transformations: derived columns, lookups, SCD logic
- ETL handled via OLEDB Commands with mappings and data conversions
- Accumulated fact table with transaction timestamps and processing time

📂 ETL Queries Link: [View Queries](https://mysliit-my.sharepoint.com/:f:/g/personal/it22118936_my_sliit_lk/EtPwrjUtNf1GuSSkpJZuImEBIUD6JryuYTUcByCBTmbkjw?e=YgYm1V)

---

## 🧠 SSAS OLAP Cube

- Created using **SQL Server Data Tools (SSDT)**
- Star schema mapped into cube structure
- Created meaningful **hierarchies**:
  - Calendar: Year → Quarter → Month → Day
  - Lecturer: Department → Type → Hire Date
  - Academic Course: Faculty → Course → Mode → Credit → Term

### ✅ OLAP Operations Demonstrated:
- Roll-up & Drill-down
- Slice & Dice
- Pivoting and Filtering in Excel
- Connected directly to SSAS Cube from Excel

---

## 📊 Power BI Dashboards

Connected Power BI to the **SSAS Cube** and built 4 dashboards:

1. **Matrix Report**
   - Hierarchical display of courses vs. term with conditional formatting

2. **Interactive Dashboard**
   - Slicers for Faculty and Program
   - Bar, line, card, and donut visuals for academic performance

3. **Drill-down Report**
   - Explore data by Academic Year → Semester → Course → Lecturer

4. **Drill-through Report**
   - Navigate to detailed student or course pages via right-click filters

**🧰 Tools & Technologies**

| Tool/Platform        | Purpose                                 |
| -------------------- | --------------------------------------- |
| Microsoft SQL Server | Data warehouse & database               |
| SSIS                 | ETL process development                 |
| SSAS                 | Cube design & multidimensional modeling |
| Microsoft Excel      | OLAP visualization                      |
| Power BI             | Interactive reporting & dashboards      |

**👨‍🎓 Author**
Enith Samarasinghe
3rd-Year Undergraduate, BSc (Hons) in Information Technology (Specializing in Data Science)
Sri Lanka Institute of Information Technology (SLIIT)
