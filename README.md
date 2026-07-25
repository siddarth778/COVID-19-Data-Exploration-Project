COVID-19 Data Exploration Project

Project Overview:

This project focuses on exploring global COVID-19 data to extract key insights regarding infection rates, death percentages, and vaccination progress across various countries and continents. Using SQL, raw datasets were queried and transformed into structured data formats, preparing them for downstream data visualization in tools like Tableau or Power BI.

Datasets Used:

The project uses two primary datasets. The first is CovidDeaths.xlsx, which contains records of COVID-19 cases, total deaths, populations, and geographical data. The second is CovidVaccinations.xlsx, which contains daily and cumulative vaccination counts per region.

SQL Concepts and Skills Applied:

The technical implementation relies on several key SQL techniques:

Joins were used to combine the CovidDeaths and CovidVaccinations tables on location and date.

CTEs (Common Table Expressions) were used to simplify complex queries and perform calculations on partitioned data.

Temp Tables were created to store intermediate metrics for further calculation.

Window Functions like SUM() OVER (PARTITION BY ... ORDER BY ...) were applied to calculate rolling vaccination totals.

Aggregate Functions such as SUM(), MAX(), and AVG() were used to calculate totals and rates.

Data Type Conversion was handled by casting string/varchar metrics using CAST() and CONVERT() to perform numerical operations.

Creating Views allowed saving optimized queries into database views for easy visualization access.

Key Insights and Analysis Breakdown:

Infection vs. Death Rates: Calculated the likelihood of dying after contracting COVID-19 in specific countries (e.g., United States) using (total_deaths / total_cases) * 100.

Population Infection Percentage: Evaluated what percentage of a country's total population tested positive for COVID-19 over time using (total_cases / population) * 100.

Highest Infection and Death Counts: Identified countries with the highest infection rates relative to their population size. Isolated total death counts by continent and individual nations by filtering out aggregate rows where continent IS NOT NULL.

Global Totals: Computed overall global figures, including total worldwide cases, total deaths, and the overall global mortality rate.

Vaccination Tracking (Rolling Totals): Joined mortality and vaccination data to calculate a running total of vaccinated individuals per location. Leveraged both a CTE (PopvsVac) and a Temp Table (#PercentPopulationVaccinated) to compute the percentage of population vaccinated over time.

Views for Visualization: Created a permanent SQL View (PercentPopulationVaccinated) to store transformed data for seamless integration with visualization tools like Tableau.

How to Run the Queries:

Step 1: Import the CovidDeaths.xlsx and CovidVaccinations.xlsx files into your SQL database (e.g., SSMS / MS SQL Server) under a database named PortfolioProject.

Step 2: Ensure the column data types match standard date and numeric formats where applicable.

Step 3: Run the SQL script sequentially to execute exploratory queries, build CTEs/Temp Tables, and create the final database view.
