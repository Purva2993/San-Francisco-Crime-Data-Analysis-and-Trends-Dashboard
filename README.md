# San-Francisco-Crime-Data-Analysis-and-Trends-Dashboard
An interactive data visualization project analyzing over 900,000 police incident reports from San Francisco (2018-Present) using Python for data processing and Tableau for visualization.

# Project Overview
This project transforms raw crime data into actionable insights through comprehensive data analysis and interactive dashboards. The goal is to provide law enforcement, policymakers, and citizens with a clear understanding of San Francisco's crime landscape and trends.

# Live Dashboard
View Interactive Dashboard on Tableau Public

# Technologies Used

Python 3.x - Data cleaning and preprocessing
Pandas - Data manipulation and analysis
NumPy - Numerical operations
Tableau Public - Data visualization and dashboard creation

# Project Structure
data/ - Data storage directory

raw/ - Original datasets

Police_Department_Incident_Reports_2018_to_Present.csv - Raw crime data from SF Open Data

processed/ - Cleaned and processed datasets

sf_crime_data_cleaned.csv - Processed data ready for visualization

notebooks/ - Jupyter notebooks for exploration

data_cleaning_and_preprocessing.ipynb - Data analysis and cleaning workflow

scripts/ - Python scripts

data_preprocessing.py - Automated data processing pipeline

dashboards/ - Tableau workbooks

SF_Crime_Dashboard.twbx - Complete Tableau dashboard file

README.md - Project documentation

Installation and Setup
Prerequisites

Python 3.7 or higher
Tableau Public (free) or Tableau Desktop

Clone Repository
bashgit clone https://github.com/yourusername/sf-crime-analysis.git
cd sf-crime-analysis
Install Dependencies
bashpip install pandas numpy jupyter
Data Source
Dataset: San Francisco Police Department Incident Reports (2018 to Present)
Source: San Francisco Open Data Portal
Size: 900,000+ records
Update Frequency: Daily
Key Data Fields

Incident DateTime
Police District
Incident Category/Subcategory
Resolution Status
Neighborhood
Geographic Coordinates

# Data Processing Pipeline
1. Data Cleaning (scripts/data_preprocessing.py)
pythonimport pandas as pd
import numpy as np

# Load and clean data
df = pd.read_csv("raw/Police_Department_Incident_Reports_2018_to_Present.csv")
df['Incident Datetime'] = pd.to_datetime(df['Incident Datetime'])

# Feature Engineering
df['Hour'] = df['Incident Datetime'].dt.hour
df['Time Of Day'] = df['Hour'].apply(get_time_of_day)
df['Is Evening Crime'] = (df['Time Of Day'] == 'Evening').astype(int)
df['Is Weekend'] = df['Incident Day of Week'].isin(['Saturday', 'Sunday']).astype(int)
2. Feature Engineering

Time Classification: Morning, Afternoon, Evening, Night
Binary Flags: Weekend crimes, Evening crimes
Temporal Features: Hour, Day of Week, Month, Year
Resolution Status: Open/Active vs Resolved

# Dashboard Components
Dashboard 1: Crime Overview

Monthly crime trends (2018-Present)
Key Performance Indicators (KPIs)
Year-over-year percentage changes
Total incidents summary

Dashboard 2: Time & Hour Analysis

Crime distribution by time of day
Weekday vs Hour heatmap
Peak crime hours identification

Dashboard 3: Geographic Analysis

District-wise crime distribution
Neighborhood crime intensity map
Evening crime percentage by area

Dashboard 4: Resolution Analysis

Resolution rates by crime category
Top 10 crime types analysis
Temporal resolution trends

# Key Insights Discovered
Temporal Patterns

Peak Hours: Afternoon (12-17h) shows highest crime rates
Weekend Effect: Saturday and Sunday have distinct patterns
Seasonal Trends: Post-pandemic spike observed in 2021

Geographic Patterns

High-Risk Districts: Central, Bayview, Ingleside
Evening Crime Hotspots: Specific neighborhoods identified
Resolution Disparities: Varies significantly by location

Crime Categories

Most Frequent: Larceny Theft dominates incidents
Highest Resolution: Drug-related crimes (>95% resolution rate)
Lowest Resolution: Property crimes remain challenging

# Interactive Features
Filters Available

Time Period Selection
Police District Filter
Crime Category Filter
Time of Day Selection

Dashboard Actions

Hover Tooltips: Detailed incident information
Click Interactions: Cross-dashboard filtering
Parameter Controls: Dynamic year selection

# Usage Instructions
Running the Analysis

Download raw data from San Francisco Open Data Portal
Run the preprocessing script:
bashpython scripts/data_preprocessing.py

Open Tableau and load the cleaned dataset
Import the dashboard file: dashboards/SF_Crime_Dashboard.twbx

Exploring the Dashboard

Visit the live dashboard
Use filters to explore specific time periods or districts
Hover over visualizations for detailed information
Click on elements to trigger cross-filtering

# Future Enhancements

 Predictive Modeling: Crime forecasting using machine learning
 Real-time Updates: Automated data refresh pipeline
 Anomaly Detection: Identify unusual crime patterns
 Weather Correlation: Analysis of weather impact on crime
 Mobile Optimization: Responsive dashboard design
 API Integration: Real-time data streaming
