
# Technology Adoption and Gender Gaps in Unpaid Laundry Work

An empirical analysis of the relationship between household washing methods and gender differences in time spent washing clothes in India, using the **2024 Time Use Survey (TUS)** and R.

## Overview

This project examines whether the gender gap in time spent washing clothes differs between households that use manual washing, mechanical washing and outsourced washing.

The analysis investigates whether mechanical washing is associated with a smaller female–male difference in laundry time, while accounting for individual and household characteristics. Since the data are observational, the findings are interpreted as associations rather than causal effects.

## Research Questions

- How does time spent washing clothes differ by gender and household washing method?
- Is the female–male gap in laundry time smaller in households using mechanical washing than in households using manual washing?
- Do these relationships remain after accounting for individual and household characteristics?
- Do the results differ when participation in washing is analysed separately from time spent among participants?

## Data

**Source:** 2024 Time Use Survey (TUS), conducted by the National Statistical Office (NSO), India.

The analysis combines:

- **Person-level data:** Gender, age, education, marital status, principal activity and detailed time-use activity records.
- **Household-level data:** Household size, monthly consumer expenditure and household washing method.

The survey records a 24-hour reference period in 48 half-hour time slots. The final analytical dataset contains **454,192 individuals aged six years and above**. Survey multipliers are used as weights.

## Measuring Laundry Time

The main outcome is the number of minutes each individual spent on activity code **341 (washing clothes)**.

Where multiple activities were recorded in the same time slot, the 30 minutes were divided across the recorded activities. The allocated washing minutes were then summed across the day. Individuals who did not report activity 341 were assigned zero minutes.

The household washing-method variable is grouped into three categories:

- Manual washing
- Mechanical washing
- Outsourced washing

## Methodology

The analysis was conducted in R and involved:

1. Cleaning and preparing person-level and household-level survey data.
2. Constructing individual and household identifiers and merging the two data levels.
3. Processing time-use activity records and allocating time across simultaneous activities.
4. Calculating individual daily laundry time.
5. Applying survey weights.
6. Comparing weighted mean laundry time by gender and washing method.
7. Estimating survey-weighted regression models with gender-by-washing-method interactions.
8. Controlling for age, education, marital status, principal activity, household size, household expenditure and sector.
9. Conducting robustness checks using alternative model specifications.
10. Estimating a two-part model to distinguish participation in washing from time spent among participants.

The main coefficient of interest is the **Female × Mechanical** interaction. A negative coefficient indicates that the adjusted female–male gap is smaller under mechanical washing than under manual washing.

## Key Findings

- In the weighted descriptive results, the female–male gap was **18.56 minutes per day under manual washing** and **18.25 minutes under mechanical washing** — a raw difference of approximately 0.32 minutes.
- In the fully controlled regression, the Female × Mechanical interaction was **−1.281 minutes** (SE = 0.287, p < 0.001).
- The adjusted predicted female–male gap was **10.27 minutes under manual washing** and **8.99 minutes under mechanical washing**.
- Robustness checks reported a similar negative interaction.
- The two-part model also found a smaller female–male gap among participants under mechanical washing.
- Overall, the reduction in the adjusted gender gap is modest. Mechanical washing does not eliminate the gender division of laundry work.

## Limitations

- The data are observational, so the analysis identifies associations and cannot establish that mechanical washing causes the gender gap to decrease.
- The outcome includes activity code 341 (washing clothes), not all laundry-related activities.
- The survey groups all transgender respondents into one category and does not distinguish transgender men from transgender women or provide categories for other gender identities.
- Household circumstances and social factors not fully captured by the model may also influence the results.

## Tools and Technologies

- R
- dplyr
- tidyr
- survey
- readr
- ggplot2
- knitr
- Survey-weighted descriptive statistics
- Linear regression and interaction models
- Robustness checks

## Repository Files

| File | Description |
|---|---|
| `analysis.Rmd` | R Markdown source containing data preparation and statistical analysis code |
| `report.html` | Knitted HTML output containing the analysis and rendered results |
| `research-paper.pdf` | Written research paper presenting the methodology, results and discussion |
| `README.md` | Project overview and documentation |

## Project Type

**Individual Research Project**

An independent empirical research project involving survey data preparation, statistical analysis, econometric modelling and interpretation of findings.
