# EDS-213: Food Poisoning Outbreaks and Health Outcomes

### Evaluating Severity in Health Outcomes against Poverty Rates

This repository contains code from R and SQL to clean data, build a SQL database in DuckDB, and produce explanatory visualizations to answer the question of if states with higher poverty rates suffer worse outcomes from food poisoning outbreaks reported to the CDC. Data estimating the United States and State populations between 1910-2024 and poverty percentage rates were obtained from the U.S. Census Bureau. These data were joined to form table 'census', and Center for Disease Control and Prevention (CDC) National Outbreak Reporting System (NORS) were used to create table 'outbreaks'. 

## Data Access

Data was publicly available and accessed from CDC NORS and U.S. Census Bureau

## Author: Nathalie Bonnet

## Folders and Files

data: contains raw data and processed data subfolders. Raw data comes directly from cited data download links. Processed data are written by **data-cleaning.qmd**; which contains the code and written decisions that went into creating the data used in the database.

food_poisoning.duckdb: SQL database built using DuckDB containing U.S Census Data and CDC data.

**food_poisoning_outbreaks**: SQL file used to create DuckDB SQL database by copying data from csvs, and preliminary queries for data exploration.

**final-query-viz.qmd** contains the R code to produce final visualizations by querying the database. The visualizations include a map and a line graph. 

**dependencies.txt**: contains all package versions used in cleaning, analysis, and final visualization.


## Contents

```
.gitignore
│   .Rhistory
│   data-cleaning.qmd
│   dependencies.txt
│   final-query-viz.qmd
│   food_poisoning.duckdb
│   food_poisoning_outbreaks
│   README.md
│
└───data
    ├───processed
    │       census.csv
    │       outbreaks.csv
    │
    └───raw
            apportionment.csv
            est23us.xls
            NORS_20260422.csv
```

## Data Citation

<table>
  <thead>
    <tr>
      <th>#</th>
      <th>Dataset</th>
      <th>Publisher</th>
      <th>Year</th>
      <th>Format</th>
      <th>Topic</th>
      <th>URL</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>1</td>
      <td><strong>National Outbreak Reporting System (NORS)</strong><br><sub>Aggregate outbreak data reported by state, local, and territorial health departments to CDC, covering foodborne, waterborne, enteric, and fungal disease outbreaks. Includes pathogen, setting, implicated food/water source, illness counts, and date/location.</sub></td>
      <td>Centers for Disease Control &amp; Prevention (CDC)</td>
      <td>2009–present</td>
      <td>CSV / API</td>
      <td>Public Health</td>
      <td><a href="https://data.cdc.gov/Foodborne-Waterborne-and-Related-Diseases/NORS/5xkq-dg7x/data_preview">data.cdc.gov/…/NORS/5xkq-dg7x</a></td>
    </tr>
    <tr>
      <td>2</td>
      <td><strong>2020 Decennial Census Apportionment Data</strong><br><sub>State-level apportionment population counts from the 2020 Census used to allocate the 435 seats in the U.S. House of Representatives. Includes resident population plus overseas federal employees and their dependents allocable to a home state.</sub></td>
      <td>U.S. Census Bureau (Decennial Census)</td>
      <td>2021 (2020 Census)</td>
      <td>CSV</td>
      <td>Demographics</td>
      <td><a href="https://www2.census.gov/programs-surveys/decennial/2020/data/apportionment/apportionment.csv">census.gov/…/apportionment.csv</a></td>
    </tr>
    <tr>
      <td>3</td>
      <td><strong>Small Area Income &amp; Poverty Estimates (SAIPE) — 2023 State &amp; County</strong><br><sub>Model-based annual estimates of poverty and median household income for all U.S. states and counties, derived from ACS data, federal tax records, SNAP benefits data, and decennial census figures. The only federal source for single-year county-level median household income.</sub></td>
      <td>U.S. Census Bureau (SAIPE Program)</td>
      <td>2024 (est. year 2023)</td>
      <td>XLS</td>
      <td>Economics</td>
      <td><a href="https://www2.census.gov/programs-surveys/saipe/datasets/2023/2023-state-and-county/est23us.xls">census.gov/…/est23us.xls</a></td>
    </tr>
  </tbody>
</table>
