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

## 📋 Dashboard Pages

### 1️⃣ Demographics Dashboard
**Purpose:** Understand the student population, diversity, and class size balance.  

**Key Visuals:**
- KPI cards for Total Students, Teachers, Ratio, and Average Age  
- Map visualization showing students by nationality  
- Donut chart showing level distribution  
- Departmental score comparison by gender  

**Analysis Questions:**
- Which departments or levels have the highest student population?  
- How balanced is the student–teacher ratio?  
- What is the demographic distribution of students by nationality?

### 2️⃣ Key Trends Dashboard
**Purpose:** Track academic performance trends and yearly growth.  

**Key Visuals:**
- Line chart of average score by assessment type  
- Matrix of monthly/weekly score breakdowns  
- Column chart of weighted average scores by year  

**Analysis Questions:**
- How are scores trending across semesters and years?  
- Which assessment types yield higher performance?  
- What’s the YoY enrollment growth rate?

### 3️⃣ Performance Dashboard
**Purpose:** Evaluate student and teacher-level performance.  

**Key Visuals:**
- Donut chart: Average Weighted Score by Teachers  
- Top 3 Students by Average Score (Bar Chart)  
- Individual Student Card (Profile + KPIs)  
- Departmental Performance Table (Weighted Score, Avg, Grade)

**Analysis Questions:**
- Which teachers drive higher student performance?  
- Who are the top-performing students overall?  
- What are each student’s strengths by department?

## 🧠 Key DAX Measures

```DAX
-- Weighted Score
Weighted Score =
SUMX(
    FactPerformance,
    FactPerformance[Score] * RELATED(DimSubject[CreditUnit])
)

-- Average Weighted Score
Average Weighted Score =
DIVIDE(
    [Weighted Score],
    SUMX(FactPerformance, RELATED(DimSubject[CreditUnit])),
    0
)

-- Pass Rate
Pass Rate =
DIVIDE(
    CALCULATE(COUNTROWS(FactPerformance), FactPerformance[Score] >= 50),
    COUNTROWS(FactPerformance),
    0
)

-- Student–Teacher Ratio
Student Teacher Ratio =
DIVIDE(
    COUNT(DimStudents[StudentID]),
    COUNT(DimTeachers[TeacherID])
)

## Tools & Technologies
- Power BI Desktop – Dashboard design & DAX modeling
- Microsoft Excel – Data source for dimensions and fact tables
- DAX – Calculated measures for KPIs
- Star Schema – Optimized data modeling



