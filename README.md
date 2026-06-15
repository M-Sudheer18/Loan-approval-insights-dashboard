# Loan Approval Insights Dashboard

## Project Overview

The Loan Approval Insights Dashboard is a Power BI project designed to analyze loan application data and uncover key factors that influence loan approvals and rejections. The dashboard provides a comprehensive view of applicant demographics, education levels, employment status, property areas, income distribution, and approval trends.

The primary objective of this analysis is to help financial institutions understand customer behavior, identify approval patterns, assess lending risks, and support data-driven decision-making.

---

# Business Problem

Financial institutions receive numerous loan applications every day. Evaluating these applications manually can be time-consuming and may not always reveal hidden trends.

This dashboard helps answer important business questions such as:

- Who applies for loans most frequently?
- What type of applicants receive more approvals?
- Does education influence loan applications?
- How does employment status impact lending?
- Which property areas generate the highest loan demand?
- Does family size affect loan approvals?
- What is the overall financial strength of applicants?

---

# Dataset Information

The dataset contains information about loan applicants, including:

| Column | Description |
|----------|------------|
| Gender | Applicant Gender |
| Married | Marital Status |
| Dependents | Number of Dependents |
| Education | Graduate / Non-Graduate |
| Self_Employed | Employment Type |
| ApplicantIncome | Applicant Income |
| CoapplicantIncome | Co-Applicant Income |
| LoanAmount | Requested Loan Amount |
| Loan_Amount_Term | Loan Repayment Term |
| Credit_History | Credit History Status |
| Property_Area | Urban, Rural, Semiurban |
| Loan_Status | Approved or Rejected |

---

# Dashboard KPIs

## Total Applicants

**Formula**

```DAX
Total Applicants = COUNTROWS(loan)
```

### Result
480 Applicants

### Meaning

This KPI shows the total number of loan applications available in the dataset. It serves as the foundation for all further analysis.

### Insight

The organization processed 480 loan applications, indicating significant loan demand.

---

## Approved Loans

**Formula**

```DAX
Approved Loans =
CALCULATE(
    COUNTROWS(loan),
    loan[Loan_Status] = "Y"
)
```

### Result
332 Approved Loans

### Meaning

Represents applicants whose loans were successfully approved.

### Insight

Most applicants met the lender's eligibility requirements, indicating healthy lending activity.

---

## Rejected Loans

**Formula**

```DAX
Rejected Loans =
CALCULATE(
    COUNTROWS(loan),
    loan[Loan_Status] = "N"
)
```

### Result
148 Rejected Loans

### Meaning

Represents applicants whose loan requests were denied.

### Insight

Rejected applications help lenders identify risk factors and improve screening procedures.

---

## Approval Rate

**Formula**

```DAX
Approval Rate =
DIVIDE([Approved Loans],[Total Applicants]) * 100
```

### Result

69.2%

### Meaning

Shows the percentage of applications that were approved.

### Insight

Almost seven out of every ten applicants successfully received a loan.

---

# Dashboard Visual Analysis

---

# 1. Credit History by Gender

## Visual Type

Bar Chart

## Fields Used

### Axis
```text
Gender
```

### Values
```DAX
Total Applicants
```

## Analysis

The chart compares the number of applicants based on gender.

### Findings

- Male applicants dominate the dataset.
- Female applicants represent a smaller portion of total applications.
- Loan demand is considerably higher among male applicants.

### Business Interpretation

The lender may explore strategies to improve financial inclusion and loan participation among female customers.

---

# 2. Loan Applications by Education

## Visual Type

Pie Chart

## Fields Used

### Legend
```text
Education
```

### Values
```DAX
Total Applicants
```

## Analysis

The chart shows the distribution of applicants based on educational qualifications.

### Findings

- Graduates account for approximately 80% of applicants.
- Non-Graduates account for approximately 20%.

### Business Interpretation

Individuals with higher education levels are more likely to seek loans, likely due to better employment opportunities and income stability.

---

# 3. Loan Applications by Dependents and Self-Employment

## Visual Type

Clustered Column Chart

## Fields Used

### Axis
```text
Dependents
```

### Legend
```text
Self_Employed
```

### Values
```DAX
Total Applicants
```

## Analysis

The chart compares applicant counts based on family dependents and employment type.

### Findings

- Applicants with no dependents form the largest group.
- Non-self-employed applicants dominate every category.
- Applications decrease as the number of dependents increases.

### Business Interpretation

Applicants with fewer financial responsibilities are more likely to apply for loans.

---

# 4. Loan by Property Area

## Visual Type

Area Chart

## Fields Used

### Axis
```text
Property_Area
```

### Values
```DAX
SUM(LoanAmount)
```

## Analysis

The chart compares total loan amounts across different property regions.

### Findings

- Semiurban areas show the highest loan activity.
- Rural areas contribute moderately.
- Urban areas show comparatively lower loan activity.

### Business Interpretation

Semiurban regions represent the strongest market for loan products and housing finance.

---

# 5. Self-Employment Distribution

## Visual Type

Donut Chart

## Fields Used

### Legend
```text
Self_Employed
```

### Values
```DAX
Total Applicants
```

## Analysis

The chart categorizes applicants into self-employed and non-self-employed groups.

### Findings

- Most applicants are salaried employees.
- Self-employed applicants represent a much smaller share.

### Business Interpretation

Stable monthly income appears to be a common characteristic among loan applicants.

---

# 6. Dependents-wise Approved Loans

## Visual Type

Horizontal Bar Chart

## Fields Used

### Axis
```text
Dependents
```

### Values

```DAX
Approved Loans
```

## Analysis

The chart shows approved loans categorized by number of dependents.

### Findings

- Applicants with no dependents receive the highest number of approvals.
- Approval counts decrease as family size increases.
- Applicants with three dependents have the lowest approvals.

### Business Interpretation

Lower family obligations may improve loan eligibility and repayment confidence.

---

# 7. Total Applicants Income

## Visual Type

Gauge Chart

## Formula

```DAX
Total Income =
SUM(loan[ApplicantIncome])
```

## Analysis

The gauge displays the combined income of all applicants.

### Result

₹3 Million

### Findings

- Applicant income levels are generally strong.
- Income exceeds the midpoint of the gauge range.

### Business Interpretation

Higher income levels contribute positively to loan eligibility and repayment capability.

---

# Key Business Insights

### Applicant Characteristics

- Most applicants are male.
- Most applicants are graduates.
- Most applicants are not self-employed.
- Most applicants have no dependents.

### Loan Approval Trends

- Loan approvals significantly exceed rejections.
- Applicants with fewer dependents receive more approvals.
- Stable employment contributes positively to approval likelihood.

### Geographic Insights

- Semiurban regions generate the highest loan demand.
- Rural regions contribute moderate demand.
- Urban regions contribute the lowest demand within this dataset.

### Financial Insights

- Applicant income levels appear healthy.
- Strong earning capacity supports higher approval rates.

---

# Recommendations

### 1. Focus on Semiurban Markets

Semiurban areas show the highest loan activity. Expanding loan offerings in these regions can increase business growth.

### 2. Develop Products for Self-Employed Customers

Since self-employed applicants represent a smaller segment, customized loan products may help increase approvals and customer acquisition.

### 3. Improve Female Customer Participation

Targeted financial awareness campaigns can encourage more female applicants.

### 4. Enhance Risk Assessment Models

Analyzing rejected applications can help improve approval accuracy while minimizing default risk.

### 5. Promote Financial Literacy Programs

Educating potential borrowers about eligibility requirements may improve application quality and approval rates.

---

# Final Conclusion

The Loan Approval Insights Dashboard reveals that loan approvals are strongly associated with education level, employment stability, income strength, and family size. Graduate applicants, salaried employees, and applicants with fewer dependents represent the majority of successful loan approvals. Semiurban areas emerge as the most active market segment, indicating strong demand for financial products. Overall, the lender maintains a healthy approval rate, demonstrating effective loan evaluation and risk management practices while supporting a broad range of qualified applicants.
