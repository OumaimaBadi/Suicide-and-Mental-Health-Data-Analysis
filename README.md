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
The ETL process is implemented using Talend, involving data extraction from Excel and CSV files, data transformation to ensure consistency and integrity, and data loading into the Oracle data warehouse.

### Steps
1. **Extraction**: Data is extracted from the raw files located in the `/data` directory.
2. **Transformation**: Data is cleaned, aggregated, and transformed using Talend jobs.
3. **Loading**: Transformed data is loaded into the respective tables in the data warehouse.

## Usage
To run the ETL process, navigate to the `/scripts` directory and execute the Talend jobs in the following order:
1. `load_dim_country.job`
2. `load_dim_year.job`
3. `load_dim_mhd.job`
4. `load_fact_mental_health.job`

## Visualizations
The visualizations created in Tableau can be found in the `/visualizations` directory. They provide insights into:
- Prevalence of mental health disorders over time
- Social support rates by country
- Suicide rates by country and year

![Mental Health Disorders Prevalence](/visualizations/mental_health_prevalence.png)
![Social Support Rates by Country](/visualizations/social_support_by_country.png)
![Suicide Rates Trends](/visualizations/suicide_rates_trends.png)

## Conclusion
This project underscores the complex interplay between mental health disorders, suicide rates, and social support. It emphasizes the necessity of providing adequate support and medical care to individuals suffering from mental health issues to mitigate suicide risks.

## Contributors
- [Your Name]
- [Team Member 2]
- [Team Member 3]

## License
This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.
