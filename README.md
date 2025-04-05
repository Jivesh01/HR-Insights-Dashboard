# HR-Insights-Dashboard

HR Insights Dashboard – Common DAX Measures
1. Total Employees
DAX
Copy
Edit
Total Employees = COUNT(HR[EmployeeID])
2. Average Age of Employees
DAX
Copy
Edit
Average Age = AVERAGE(HR[Age])
3. Attrition Rate (%)
DAX
Copy
Edit
Attrition Rate (%) = 
DIVIDE(
    CALCULATE(COUNT(HR[EmployeeID]), HR[Attrition] = "Yes"),
    [Total Employees]
) * 100
4. Employees by Department
DAX
Copy
Edit
Employees by Department = COUNTROWS(HR)
-- Use this in a table visual grouped by Department
5. Diversity Ratio (e.g., Female Employees %)
DAX
Copy
Edit
Female Employee % = 
DIVIDE(
    CALCULATE(COUNT(HR[EmployeeID]), HR[Gender] = "Female"),
    [Total Employees]
) * 100
6. Average Tenure
DAX
Copy
Edit
Average Tenure = AVERAGE(HR[YearsAtCompany])
7. New Hires (Monthly)
DAX
Copy
Edit
New Hires = 
CALCULATE(
    COUNT(HR[EmployeeID]),
    FILTER(HR, HR[HireDate] >= DATE(YEAR(TODAY()), MONTH(TODAY()), 1))
)
