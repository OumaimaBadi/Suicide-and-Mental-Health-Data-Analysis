# Suicide-and-Mental-Health-Data-Analysis

## Project Overview
This project aims to analyze the correlation between mental health issues, suicide rates, and social support by country from 2015 to 2022. We've built a data warehouse to facilitate complex analyses and support efforts in mental health improvement and suicide prevention.

## Data Sources
- **Kaggle**: Used for country-specific suicide data and social support rates.
- **Our World in Data**: Utilized for detailed mental health disorder prevalence by country.


## Data Warehouse Design
Our data warehouse consists of three dimension tables and one fact table structured as follows:

### Dimension Tables
- **Country Dimension** (`dim_country`)
  - `ID_COUNTRY`: Primary key (non-significant, numeric)
  - `COUNTRY_NAME`: Name of the country
  - `CODE`: Country code
  - `REGION`: Geographic region of the country

- **Year Dimension** (`dim_year`)
  - `ID_YEAR`: Primary key (non-significant, numeric)
  - `YEAR`: Calendar year

- **Mental Health Disorder Dimension** (`dim_mhd`)
  - `ID_MHD`: Primary key (non-significant, numeric)
  - `NAME_MHD`: Name of the mental health disorder

### Fact Table
- **Mental Health Facts** (`fact_mental_health`)
  - `ID_MENTAL_HEALTH`: Primary key
  - `ID_COUNTRY`, `ID_YEAR`, `ID_MHD`: Foreign keys linking to dimension tables
  - `SOCIAL_SUPPORT_RATE`: Social support rate in the country for the year
  - `PREVALENCE_OF_MHD`: Prevalence of mental health disorder
  - `SUICIDE_RATE`: Suicide rate in the country for the year

## ETL Process
The ETL process is implemented using Talend, involving data extraction from Excel, CSV and JSON files, data transformation to ensure consistency and integrity, and data loading into the Oracle data warehouse.

### Steps
1. **Extraction**: Data is extracted from the raw files located in the `/data` directory.
2. **Transformation**: Data is cleaned, aggregated, and transformed using Talend jobs.
3. **Loading**: Transformed data is loaded into the respective tables in the data warehouse.

### Data Warehouse Design and ETL Process

In the **/data_warehouse_conception_and_ETL** directory:
- **Conception**: Contains screenshots of the data warehouse schema including dimension and fact tables.
- **ETL Process**: Screenshots of the ETL process using Talend, demonstrating how data is extracted from source files, transformed, and loaded into our data warehouse.

## Visualizations
The visualizations created in Tableau can be found in the `/visualizations` directory. They provide insights into:
- Prevalence of mental health disorders over time
- Suicide per year and per country

### Social Support Rates by Country
![Social Support Rates by Country](/visualisations/Social_support_by_country.png)

This chart shows the countries with high social support, colored in green, and countries with low social support, colored in red. For instance, countries in Africa and South Asia have less social support compared to American and European countries.

### Suicide Rates by Country
![Suicide Rates by Country](/visualisations/Suicide_rates_by_country.png)

This chart displays countries with high suicide rates, colored in red, and countries with low suicide rates, colored in green. For example, Russia has a higher suicide rate than other countries, unlike Saudi Arabia, which has the lowest suicide rate.


## Conclusion
This project underscores the complex interplay between mental health disorders, suicide rates, and social support. It emphasizes the necessity of providing adequate support and medical care to individuals suffering from mental health issues to mitigate suicide risks.

## Contributors
- BADI Oumaima
