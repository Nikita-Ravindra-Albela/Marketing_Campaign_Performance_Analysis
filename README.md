# Marketing Campaign Performance Analysis

An end-to-end marketing analytics project focused on investigating messy campaign data, improving data quality, evaluating campaign performance, and developing actionable insights to support data-driven marketing decisions.

**Project Status:** In Progress

## 1. Project Overview

Marketing teams need reliable data to understand which campaigns attract audiences, generate clicks, and drive conversions. However, inconsistent formats, missing values, duplicate records, and invalid metrics can lead to misleading performance reports.

This project uses a messy marketing campaign dataset to simulate a real-world analytics workflow, starting with raw data profiling and quality assessment, followed by data cleaning, validation, SQL-based analysis, KPI development, and interactive dashboarding.

The goal is to build a reproducible analytics pipeline that transforms raw campaign data into a reliable foundation for business decision-making.

## 2. Business Objectives

- Assess the quality, completeness, consistency, and reliability of raw marketing data.
- Identify and investigate missing values, duplicate records, inconsistent categories, and anomalous metrics.
- Develop a documented and reproducible data-cleaning workflow.
- Evaluate campaign performance across marketing channels and campaign attributes.
- Calculate relevant marketing KPIs to measure engagement, efficiency, and conversion performance.
- Build an interactive Power BI dashboard to communicate findings and support marketing decisions.

## 3. Dataset Description

**Dataset:** Marketing Campaign Data (Messy)

**Source:** Kaggle

**Initial dataset size:** Approximately 2,020 records.

The dataset contains campaign-level information, including campaign identifiers, dates, channels, engagement metrics, spend, conversions, and campaign status.

### Key columns

| Column | Description |
|---|---|
| `Campaign_ID` | Unique campaign identifier candidate |
| `Campaign_Name` | Name assigned to the campaign |
| `Start_Date` | Campaign start date |
| `End_Date` | Campaign end date |
| `Channel` | Marketing channel used |
| `Impressions` | Number of times campaign content was displayed |
| `Clicks` | Number of clicks generated |
| `Spend` | Campaign expenditure |
| `Conversions` | Recorded conversions attributed to the campaign |
| `Active` | Campaign activity status |
| `Campaign_Tag` | Campaign classification or tag |

The raw data also contains a whitespace-variant click column (`Clicks `), which is being investigated as part of the data-quality assessment.

The original dataset is preserved separately from the cleaned outputs to maintain traceability and support reproducibility.

## 4. Technology Stack

| Technology | Purpose |
|---|---|
| Python | Data profiling, cleaning, and exploratory analysis |
| Pandas | Data manipulation, validation, and quality checks |
| Jupyter Notebook | Documenting the analytical workflow |
| SQL Server / SSMS | Planned SQL-based validation and analytical queries |
| Power BI | Planned interactive dashboard and KPI reporting |
| Git and GitHub | Version control and project documentation |

## 5. Project Workflow

The project follows a structured analytics workflow.

### Phase 1: Data Profiling and Quality Assessment

The raw dataset is inspected before applying cleaning transformations.

Activities include:

- Examining dataset dimensions and column data types.
- Assessing missing values and completeness.
- Identifying exact duplicate records.
- Checking duplicate identifiers and repeated campaign names.
- Inspecting inconsistent category values and whitespace.
- Investigating negative spend and invalid campaign durations.
- Examining inconsistent numeric formats and potential outliers.

### Phase 2: Data Cleaning and Transformation

The identified quality issues are investigated and addressed using documented rules.

Planned activities include:

- Standardizing column names and data types.
- Normalizing campaign status values.
- Resolving or flagging duplicate records.
- Parsing spend values into a consistent numeric format.
- Investigating missing conversion values without automatically assuming they represent zero.
- Flagging invalid dates, negative spend, and other suspicious records.
- Maintaining appropriate missing-value indicators and data-quality flags.

Cleaning decisions will be documented to preserve transparency and prevent unsupported assumptions.

### Phase 3: Data Validation

After cleaning, validation checks will be performed to assess whether the transformation rules were applied correctly.

These checks will include:

- Comparing raw and cleaned record counts.
- Verifying column names and data types.
- Rechecking duplicates and missing values.
- Validating date ranges and numeric constraints.
- Checking campaign identifiers and categorical consistency.
- Confirming that derived fields and KPI calculations follow documented business rules.

### Phase 4: SQL Analysis

The validated dataset will be loaded into SQL Server for structured querying and analytical reporting.

Planned analyses include:

- Campaign and channel performance comparisons.
- Aggregation of spend, clicks, impressions, and known conversions.
- Identification of high- and low-performing campaigns.
- Analysis of engagement and conversion patterns.
- Validation of KPI calculations using SQL.

### Phase 5: Exploratory Data Analysis

Exploratory analysis will investigate campaign performance patterns and potential business opportunities.

Areas of investigation include:

- Performance variation across marketing channels.
- Relationships between impressions, clicks, spend, and conversions.
- Campaign-level engagement and conversion efficiency.
- Spend distribution and unusual campaign performance.
- Campaign activity duration and its relationship with outcomes.

### Phase 6: KPI Development and Power BI Dashboard

The final reporting layer will present campaign performance through interactive visualizations and clearly defined metrics.

Planned KPIs include:

| KPI | Formula | Business purpose |
|---|---|---|
| Click-Through Rate (CTR) | Clicks ÷ Impressions × 100 | Measures audience engagement |
| Cost per Click (CPC) | Spend ÷ Clicks | Measures cost efficiency per click |
| Conversion Rate | Conversions ÷ Clicks × 100 | Measures conversion efficiency |
| Cost per Acquisition (CPA) | Spend ÷ Conversions | Measures cost per recorded conversion |

KPI calculations will account for missing or invalid inputs, zero denominators, and the distinction between unknown conversions and confirmed zero conversions.

ROAS and ROI will only be calculated if reliable revenue or return data becomes available. Spend and conversion counts alone are insufficient to calculate these metrics.

## 6. Initial Data Quality Findings

Initial profiling identified several issues that require investigation before the dataset can be used for reliable performance reporting.

| Data quality issue | Initial finding |
|---|---|
| Duplicate records | 19 exact duplicate rows identified |
| Missing conversions | 200 missing values identified |
| Missing channel values | 101 missing values identified |
| Negative spend | 19 negative spend values identified |
| Invalid campaign dates | 78 records where the end date precedes the start date |
| Inconsistent column names | Both `Clicks` and `Clicks ` appear in the raw data |
| Inconsistent status values | Multiple representations, including `Y`, `Yes`, `True`, `1`, `No`, `False`, and `0` |
| Inconsistent spend formats | Spend values include mixed currency representations |
| Campaign tags | Invalid tag values and conflicting campaign-tag information require investigation |

These are preliminary profiling observations. Final cleaned-data statistics and analytical conclusions will be documented after the cleaning and validation stages are completed.

## 7. Expected Deliverables

- Documented data-profiling notebook.
- Reproducible Python data-cleaning workflow.
- Cleaned dataset with appropriate quality flags.
- Data-quality validation checks and results.
- SQL queries for campaign analysis and KPI calculations.
- Exploratory data analysis and business findings.
- Interactive Power BI dashboard.
- Project documentation describing assumptions, limitations, and analytical decisions.

## 8. Business Value

This project is designed to demonstrate how a Data Analyst can improve the reliability of marketing reports before drawing business conclusions.

The intended outcomes include:

- More trustworthy campaign performance reporting.
- Better visibility into channel-level engagement and efficiency.
- Identification of campaigns that warrant further investigation.
- Consistent KPI definitions across analytical tools.
- A transparent and reproducible workflow from raw data to business reporting.

The final business recommendations will be based on validated analysis rather than assumptions made during the profiling stage.

## 9. Repository Structure

The repository is organized around the project workflow.

```text
Marketing_Campaign_Analytics/
│
├── Raw Data/
│   └── marketing_campaign_data_messy.csv
│
├── Python/
│   └── Marketing_Analytics_Profiling.ipynb
│
├── SQL/
│   └── SQL analysis scripts (planned)
│
├── Power BI/
│   └── Campaign performance dashboard (planned)
│
├── README.md
└── .gitignore
```

Additional folders and files will be added as the project progresses.

## 10. How to Run the Project

### Prerequisites

- Python 3.x
- Jupyter Notebook or JupyterLab
- Pandas and NumPy
- Microsoft SQL Server and SSMS for the SQL stage
- Power BI Desktop for dashboard development

### Getting started

1. Clone the repository.

   ```bash
   git clone https://github.com/Nikita-Ravindra-Albela/Marketing_Campaign_Analytics.git
   ```

2. Navigate to the project directory.

   ```bash
   cd Marketing_Campaign_Analytics
   ```

3. Install the Python dependencies.

   ```bash
   pip install pandas numpy jupyter
   ```

4. Launch Jupyter Notebook.

   ```bash
   jupyter notebook
   ```

5. Open `Python/Marketing_Analytics_Profiling.ipynb` and execute the profiling workflow.

The raw dataset should remain unchanged. Subsequent cleaning and analysis stages will use clearly defined outputs to maintain reproducibility.

## 11. Limitations and Analytical Considerations

- Missing conversions cannot automatically be interpreted as zero conversions.
- Negative spend and invalid campaign dates require investigation before exclusion or correction.
- Duplicate campaign names do not necessarily indicate duplicate campaigns.
- Campaign-level relationships do not, by themselves, establish causation.
- Revenue-based metrics cannot be derived without suitable revenue or return data.
- Findings and recommendations will be finalized only after data cleaning, validation, and analysis.

## 12. Key Learning Outcomes

Through this project, I aim to strengthen my practical skills in:

- Data profiling and data-quality assessment.
- Python and Pandas for data preparation.
- Data validation and analytical documentation.
- SQL querying and KPI development.
- Marketing performance measurement.
- Power BI dashboard development.
- Git-based version control and reproducible analytics.

---

**Author:** Nikita Ravindra Albela

**GitHub:** [Nikita-Ravindra-Albela](https://github.com/Nikita-Ravindra-Albela)

*This is an ongoing portfolio project. The README will be updated as cleaning, validation, SQL analysis, exploratory analysis, and dashboard development are completed.*
