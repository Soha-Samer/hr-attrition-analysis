# HR Attrition Analysis & Dashboard

Analysis of employee attrition drivers for a mid-size organization, combining a Python/Jupyter statistical analysis with an interactive Tableau dashboard. Framed around a hypothetical CHRO request: identify where attrition risk is concentrated, what HR can actually control, and back recommendations with data.

> **Note:** This is an independent portfolio project built on IBM's publicly released HR Analytics sample dataset. It is not an official IBM product and is not affiliated with or endorsed by IBM.

## Contents

| File | Description |
|---|---|
| `HR_KPI_Analysiss.ipynb` | Full analysis: data cleaning, exploratory analysis, statistical testing (chi-square, Mann-Whitney U), cost modeling, and an executive summary with three costed recommendations |
| `data/HR-Employee-Attrition.csv` | Source dataset (IBM HR Analytics Employee Attrition dataset — see Data Source below) |
| `dashboard/BMI_Attrition_Dashboard.twbx` | Interactive Tableau dashboard (packaged workbook, opens in Tableau Desktop or Tableau Public) |
| `dashboard/Dashboard-Image.png` | Static image of the dashboard |
| `exports/` | Cleaned/summarized CSVs exported from the notebook for use in the dashboard |
| `requirements.txt` | Python dependencies needed to run the notebook |

## Dashboard

![BMI Attrition Metrics Dashboard](dashboard/Dashboard-Image.png)

The dashboard covers headline KPIs (headcount, attrition rate, attrition cost, overtime rate), attrition breakdowns by department, job role, tenure, age group, and overtime status, cost by department and job role, and a satisfaction comparison between stayers and leavers.

## Key Findings

- **Overall attrition rate: 16.1%**, costing an estimated **$6.8M** annually in replacement costs.
- **Overtime is the strongest lever:** employees working overtime leave at **30.5%** vs **10.4%** for those who don't — a 2.9x multiplier (chi-square p < 0.001), consistent across departments.
- **Sales Executives are the single largest cost center:** 57 departures totaling $2.56M (38% of total attrition cost).
- **Job Satisfaction and Environment Satisfaction** are the only satisfaction dimensions that significantly predict attrition (both p < 0.001); workplace relationships show no meaningful effect.
- A **20–30% reduction in attrition** across the three recommended interventions is estimated to save **$1.36M–$2.04M annually**.
- **Attrition skews heavily toward younger employees:** the 18–25 age group has a noticeably higher attrition rate than every other bracket, consistent with the tenure finding that 0–1yr employees are the highest-risk group.
- **Leavers earn less than stayers:** the monthly income distribution for employees who left is shifted noticeably lower than for those who stayed (median ~$3K vs ~$5K), reinforcing the income-gap finding from the notebook's Mann-Whitney test.

See the notebook's executive summary for full recommendations, evidence, and caveats on causality.

## Tools Used

- Python (pandas, numpy, matplotlib, seaborn, scipy)
- Tableau

## How to Reproduce

```bash
git clone https://github.com/<your-username>/hr-attrition-analysis.git
cd hr-attrition-analysis
pip install -r requirements.txt
jupyter notebook HR_KPI_Analysiss.ipynb
```

Run all cells — this regenerates the summary CSVs in `exports/`. Then open `dashboard/BMI_Attrition_Dashboard.twbx` in Tableau Desktop or Tableau Public to explore the dashboard interactively.

## Data Source & Attribution

This project uses the **IBM HR Analytics Employee Attrition & Performance** dataset, a fictional/synthetic dataset created by IBM data scientists for analytics training and demonstration purposes. It contains no real employee data.

- Commonly distributed via [Kaggle](https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset)
- All company names, metrics, and figures in this analysis are illustrative and used for educational/portfolio purposes only

## License

The analysis code and dashboard in this repository are shared under the MIT License (see `LICENSE`). The dataset itself remains subject to its original distributor's terms.

## Author

Soha Elansary
