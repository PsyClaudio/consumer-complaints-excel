# Consumer Complaints Analysis with Excel

Excel portfolio project by **Claudio Lombardi**, developed for the Fundamentals of Data Analysis with Excel course in the ProfessionAI Master in Data Analytics.

## Overview

The FinServ Solutions educational case study focuses on organizing consumer complaints about financial products and services. The workbook supports inspection of complaint records, geographic summaries, identification of frequent issues, and calculation of the elapsed time between receipt and forwarding to a company.

## Workbook structure

| Worksheet | Purpose |
| --- | --- |
| Consumer_Complaints_ct | Source records with product, issue, company, state, dates and complaint identifiers |
| Consumer complaints | A focused view of complaint IDs, receipt dates, forwarding dates and elapsed days, sorted by complaint ID |
| Geographical insights | Counts by state code, percentages rounded upward, and conditional formatting |
| Statistical insights | Distinct issues, their frequencies and the most frequent categories |

## Verified findings

- **200 complaint records** in the source dataset.
- **198 records with a state code** and **2 without state information**.
- **38 distinct recorded state codes** in the geographic summary.
- California has **27 complaints**, the highest count in this dataset.
- The receipt-date filter selects dates **before 8 August 2016**, leaving **19 records visible** in Consumer complaints.
- Two issue categories tie for the highest frequency, with **22 complaints each**:
  - Incorrect information on credit report
  - Loan servicing, payments, escrow account

These results describe the supplied dataset; counts are not population-adjusted complaint rates or measures of company quality.

## Methods

### Elapsed days

The workbook calculates calendar days as:

```text
Date sent to company − Date received
```

This measures the interval between receipt and forwarding, not complaint resolution time or the company's response time.

### Geographic summary

COUNTIF counts complaints for each recorded state code. Percentages use the **198 records with a known state**, excluding the two missing values from the denominator.

CEILING.MATH rounds each share upward to the next whole percentage point. Conditional formatting marks the rounded values green below 2% and red at or above 2%. Because each percentage is rounded upward independently, the displayed percentages can sum to more than 100%.

### Most frequent issues

UNIQUE lists the issue categories and COUNTIF calculates their frequencies. IF identifies every category with the maximum frequency; FILTER and TEXTJOIN combine the tied categories in cell B7.

This identifies the most frequent issue labels, rather than taking the numerical mode of the frequency counts.

### Filter scope

The date filter applies to the Consumer complaints view. The geographic and issue summaries reference the full source dataset and do not change when rows in that view are filtered out.

## Validation

The complaint IDs were checked for ascending order in the focused view. Its dates were reconciled to source records by complaint ID, and all elapsed-day results matched the date differences. Geographic counts were independently reconciled to the source data, and the two leading issue counts were verified. The saved date-filter visibility matched the stated cutoff. No Excel error values were found in the saved cells inspected.

## Opening and using the workbook

Download `customers_complaints_assignment_Claudio_Lombardi - Portfolio.xlsx` and open it in an Excel version that supports UNIQUE and FILTER, such as Microsoft 365 or Excel 2021 or later.

Explore the source data and the three analytical worksheets. Remove or change the receipt-date filter to inspect other records in the focused view. The workbook uses fixed analysis ranges for the supplied dataset; if adding records, extend the formulas and analytical ranges and reconcile the totals. The focused view contains copied identifiers and dates, so source changes should also be checked there.

## Dataset

The workbook uses the dataset supplied for the ProfessionAI consumer complaints assignment. The original assignment workbook is available from the [ProfessionAI project repository](https://github.com/Profession-AI/progetti-excel/tree/main/Analisi%20dei%20reclami%20dei%20consumatori).

## Skills demonstrated

Microsoft Excel · Data organization · Sorting and filtering · Date arithmetic · COUNTIF · Dynamic array functions · Frequency analysis · Conditional formatting · Data reconciliation

## Author

**Claudio Lombardi** — [GitHub portfolio](https://github.com/PsyClaudio)
