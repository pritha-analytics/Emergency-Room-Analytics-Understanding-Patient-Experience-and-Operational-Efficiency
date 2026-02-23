# Emergency-Room-Analytics-Understanding-Patient-Experience-and-Operational-Efficiency

## 1. Project Overview

This project analyzes emergency room (ER) operations and patient experience using synthetic hospital visit data.  
It starts from a focused question:

> **Hypothesis:** “Operational factors like wait time, age, and department drive low patient satisfaction and admission decisions.”

Through the analysis, this narrow hypothesis is tested and then expanded into a broader view of how the ER operates overall.

---

## 2. Business Question & Hypothesis

**Core question**  
Are operational metrics (wait time, admission status, age, department) strong drivers of patient dissatisfaction and admission outcomes?

**Initial hypothesis**  
- Longer wait times increase the likelihood of:
  - Low satisfaction
  - Hospital admission  
- Certain demographics and departments experience:
  - Longer waits
  - Higher/lower admission rates

This README walks through how the analysis supports or challenges this hypothesis.

---

## 3. Data & Methodology

### 3.1 Dataset

- Synthetic ER visit-level dataset
- Key columns :
  - `Patient Age`
  - `Patient Gender`
  - `Patient Race`
  - `Age Group`
  - `Department Referral`
  - `Patient Waittime`
  - `Patient Admission Flag`
  - `Patient Satisfaction Score`


### 3.2 Analytical Steps

1. **Data cleaning & preparation**
   - Parsed and standardized admission dates and times
   - Created age groups and day-of-week features
   - Handled missing department values (e.g. set to `Unknown/No Referral`)
   - Engineered `Low Satisfaction` flag from satisfaction score

2. **Exploratory analysis**
   - Demographic distributions (age, gender, race)
   - Traffic patterns by hour, day, month
   - Department and admission breakdowns

3. **Statistical / correlation checks**
   - Correlation between:
     - Wait time and admission
     - Wait time and satisfaction
     - Age and satisfaction
     - Department and satisfaction (via one‑hot encoding)

4. **Visualization**
   - Age and race distributions
   - Department utilization by age and race
   - Heatmaps of correlation matrices

---

## 4. Key Findings

### 4.1 Demographic Overview

The ER serves a broad and demographically diverse population across all age groups, with a strong presence of young adults, adults, and seniors.  
Gender is nearly balanced, and race distribution is diverse, with White and African American patients forming the largest groups.

**Implication:**  
The ER serves a wide cross‑section of the community without major demographic imbalance.

---

### 4.2 Department Utilization Patterns

Across **all age groups**, General Practice accounts for roughly **mid‑40% to low‑50%** of admissions, with **Orthopedics** consistently second (≈ mid‑20% range).  
Across **races**, General Practice remains the dominant referral destination, with similar patterns in Orthopedics and other specialties.

**Implication:**  
Department routing appears driven by overall case mix rather than demographic bias; the workload is shared in a stable, predictable way.

---

### 4.3 Case Severity & Admission Patterns

Most visits fall into the lowest case‑management / triage category, suggesting demand is largely driven by **lower‑acuity cases** rather than critical emergencies.  
Admission rates across departments cluster tightly (roughly high‑40% to low‑50%), with no department disproportionately driving admissions.

**Implication:**  
High visit volume is primarily non‑critical, and admission decisions appear clinically driven rather than skewed by department or queue dynamics.

---

### 4.4 Wait Time Stability

Average wait times remain in a **mid‑30‑minute band** across:
- Hours of the day
- Days of the week
- Months of the year
- Genders
- Departments

Hourly variation is modest (roughly low‑ to high‑30 minutes), with only slight increases in certain early‑morning periods. Weekly and seasonal shifts are similarly small.

**Implication:**  
The ER shows strong operational stability with no major temporal bottlenecks.

---

### 4.5 Wait Time vs Admission

Correlation analysis shows **virtually no linear relationship** between:
- Wait time and admission status (correlation close to 0)

**Implication:**  
Longer waits do not meaningfully change the probability of admission, reinforcing the idea that more severe cases are prioritized independent of queue length.

---

### 4.6 Satisfaction Drivers

Using a `Low Satisfaction` flag and testing against:
- Wait time  
- Admission status  
- Age  
- Department (one‑hot encoded)

All correlations with low satisfaction are **near zero**.

**Implication:**  
Dissatisfaction is **not strongly explained** by these operational metrics. Qualitative factors (communication, expectations, bedside manner, clarity of information) are likely more important drivers.

---

### 4.7 Equity & Fairness

No meaningful differences were detected in:
- Wait times
- Admission probabilities

across major demographic slices (gender, age group, department).

**Implication:**  
From the perspective of available variables, the ER appears operationally equitable.

---

## 5. Overall Conclusion

The analysis starts from a narrow hypothesis that **operational metrics drive satisfaction and admissions** and expands to a broader system view:

- Demographics are diverse and balanced.
- Visit mix is predominantly low‑acuity.
- Wait times are stable across time and groups.
- Admission rates are balanced across departments.
- No strong operational predictors of dissatisfaction emerge.

**System characterization:**  
The ER appears **operationally mature and stable**, with no obvious structural bottlenecks or fairness issues in the measured variables.

**Opportunities for improvement:**

- Streamline pathways for low‑acuity cases.
- Reduce moderate wait times further where feasible.
- Focus on patient experience levers:
  - Communication quality
  - Expectation management
  - Perception of care
- Improve completeness and consistency of referral documentation (`Unknown/No Referral`).

---
