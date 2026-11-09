# Employee Data Summary

**Veda Technology Internship · Data Analytics Track · Task 31 (Level 1)**

A grouped workforce analysis in Excel that summarizes employees by department, role, and salary, with a summary sheet and three charts.

## Files

| File | Description |
|------|-------------|
| `employee_data_summary.xlsx` | Workbook with the `Summary` sheet (tables and 3 charts) and the `Employee Data` sheet |
| `employee_data.csv` | The same dataset as plain CSV |
| `README.md` | Approach and outcome (this file) |

## Dataset
60 employees across 5 departments (Engineering, Sales, Marketing, HR, Finance) and 15 roles, with a salary for each. This is **sample data generated for this exercise**, not real employee records.

## Approach
1. Prepared the `Employee Data` sheet (Employee ID, Name, Department, Role, Salary) with filters and a frozen header.
2. Built the `Summary` sheet using formulas linked to the data, so it updates when the data changes:
   - Headcount: `COUNTIF`
   - Average salary: `AVERAGEIF`
   - Median salary: `MEDIAN(IF(...))` array formula
   - Total payroll: `SUMIF`
   - Avg minus Median column to show how much outliers pull the average
3. Added a role-level table (headcount, average, median).
4. Added three charts:
   - Headcount by Department (column)
   - Average vs Median Salary by Department (clustered column)
   - Payroll Share by Department (pie)

> Note: the hint suggested PivotTables. I used formula-based summaries instead so the sheet recalculates automatically and the logic is visible. You can also insert a PivotTable from `Employee Data` (Insert > PivotTable) to get the same grouping.

## Key Results

| Department | Headcount | Avg Salary | Median Salary | Total Payroll |
|-----------|-----------|-----------|---------------|---------------|
| Engineering | 18 | 77,544 | 76,050 | 1,395,800 |
| Sales | 14 | 64,579 | 60,050 | 904,100 |
| Marketing | 10 | 65,610 | 61,500 | 656,100 |
| HR | 8 | 65,775 | 61,700 | 526,200 |
| Finance | 10 | 67,670 | 59,100 | 676,700 |
| **Total** | **60** | **69,315** | **68,250** | **4,158,900** |

- Engineering is the largest team (18 of 60) and has the highest average salary, so it takes about a third of the total payroll.
- In every department the average is higher than the median, meaning a few high earners (managers) pull the average up.
- Finance shows the biggest gap (about 8,570), so its average overstates what a typical employee earns.

## Interview Questions
**Why use median salary?**
Salary data is usually skewed by a few very high earners. The median is the middle value, so it is not distorted by outliers and better reflects a typical employee. Comparing it with the average shows how skewed the pay is.

**What can department counts tell you?**
Where the workforce is concentrated, how the organization allocates people, and which teams may be under- or over-staffed. Combined with payroll, they show cost per team and help with hiring and budget planning.

## Tools
Microsoft Excel: `COUNTIF`, `AVERAGEIF`, `SUMIF`, `MEDIAN`, array formulas, charts, filters
