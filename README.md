# 🎓 Students Performance Report Dashboard

## FP20 Analytics Challenge 31
**Author**: Jonathan Audu Egbe

## [Report Link](https://https://bit.ly/4o3JGwS) 

## Project Overview
This project was created for the **FP20 Analytics Challenge 31 (October 2025)**
Educational performance data provides a powerful lens into student achievement, teaching effectiveness, and the impact of the curriculum. By examining assessment results, grades, and progress metrics, schools and educators can gain a deeper understanding of learning trends, identify students at risk, and recognize top achievers. This challenge invites participants to dive deep into a comprehensive dataset that tracks student scores, assessment outcomes, and course results across subjects and time periods. The goal of this dashboard is to provide data-driven insights into student performance and teacher impact. Analyze key trends such as enrollment growth, pass/fail distribution and weighted scores. Help educational administrators make informed decisions for curriculum improvement and resource allocation.

## Dataset Overview
The dataset comprises five main tables:
- `FactPerformance`(Fact Table): Students’ academic results, and scores
- `DimStudents` – Student demographic and academic information
-  `DimTeachers` – Teacher profiles and department mapping
-  `DimSubjects` – Subject details with credit units and departmental ownership
-  `DimAssessment` - Assessment details with weighted and max scores
A **Date Table** was created in power BI using DAX to enable yearly, monthly and quaterly trends analysis.
A **Bridge Table** was created to effectively manage many-to-many relationships between the FactPerformance, DimStudents, and DimSubjects tables.

## Dashboard Design
The power BI report consist of three **interactive pages**. It's designed using **ZoomCharts PRO Visuals** for dynamic drill-downs, combined with selected Matrix visuals for detailed-level insights.

## 🧮 Core KPIs

| KPI | Description |
|-----|--------------|
| **Total Students** | Count of all active/enrolled students |
| **Total Teachers** | Number of teachers in the academic session |
| **Student–Teacher Ratio** | Ratio of total students to teachers (e.g., 10:1) |
| **Average Age** | Mean student age |
| **Average Score** | Overall mean performance score |
| **Pass Rate** | % of students scoring above the passing threshold |
| **Enrollment Growth Rate (YoY)** | Year-over-year change in student enrollment |






