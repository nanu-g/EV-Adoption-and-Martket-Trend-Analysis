Electric Vehicle Adoption and Market Trend Analysis Using Data Science in R
Overview
This project explores global electric vehicle (EV) adoption using R and data from the International Energy Agency (IEA) Global EV Outlook 2026. It analyzes historical electric car sales, compares EV sales shares across countries, examines publicly available charging infrastructure, and forecasts global electric car sales from 2026 to 2030.
Objectives
- Analyze global electric car sales trends from 2010 to 2025.
- Compare country-wise EV sales shares for 2025.
- Visualize trends in publicly available EV charging points.
- Evaluate Baseline, ARIMA, and ETS forecasting models.
- Forecast global electric car sales for 2026–2030 using the best-performing model in the evaluation.
Dataset
Source: IEA Global EV Outlook 2026 – EV data by country

The project reads the GEVO_EV_2026 sheet from the Excel dataset. The original dataset contains 49,375 rows and 9 columns; after removing duplicate rows, 49,360 rows remain.

Fields include region_country, category, parameter, mode, powertrain, year, unit, value, and Aggregate group.
Missing values were retained during initial cleaning and handled through analysis-specific filters. Obtain the Excel dataset from the IEA source if it is not included in this repository.

Tools and Libraries
- R – data analysis and time-series forecasting
- RStudio / R Markdown – analysis and reporting
- readxl – importing Excel data
- dplyr – data cleaning and manipulation
- ggplot2 – data visualization
- forecast – ARIMA and ETS modeling
- scales – plot axis formatting
Methodology
1. Data loading and preprocessing: Import the Excel sheet, inspect missing values, and remove duplicates.
2. Global sales analysis: Visualize historical global electric car sales (2010–2025).
3. Country-wise adoption: Rank countries by EV sales share in 2025.
4. Charging infrastructure: Compare the growth of publicly available charging points by charging type.
5. Forecast evaluation: Train on 2010–2022 data and evaluate predictions for 2023–2025 using MAE, RMSE, and MAPE.
6. Future forecasting: Refit ETS on the full 2010–2025 sales series and forecast 2026–2030 with 95% prediction intervals.
Key Findings
- Global electric car sales increased from 7,400 vehicles in 2010 to 21 million in 2025 in the analyzed series.
- Norway (97%), Denmark (71%), and Nepal (68%) had the highest EV sales shares among the countries shown for 2025.
- The analysis shows substantial expansion in publicly available charging infrastructure.
- ETS achieved the lowest error among the three forecasting approaches on the 2023–2025 test set.
Forecasting Model Comparison
Model	MAE	RMSE	MAPE
Baseline	7,333,333.3	7,874,007.9	40.71%
ARIMA	20,038,503.3	24,850,144.7	104.85%
ETS	568,360.4	609,590.9	3.18%


Global Electric Car Sales Forecast
Year	Predicted sales (vehicles)
2026	24,511,909
2027	27,761,391
2028	30,668,497
2029	33,211,883
2030	35,397,640


These are model-based projections, not guaranteed outcomes. The original analysis also reports 95% prediction intervals that widen over the forecast horizon.
How to Run
1. Install R and optionally RStudio.
2. Install the required R packages:
   install.packages(c("readxl", "dplyr", "ggplot2", "forecast", "scales"))
3. Download the IEA Excel dataset and ensure the workbook includes the GEVO_EV_2026 worksheet.
4. Open the project's R script or R Markdown source file in RStudio, if included in this repository.
5. Update the file_path variable to point to your downloaded Excel file:
   file_path <- "path/to/EV data by country 2026.xlsx"
6. Run the analysis chunks in order to reproduce the tables, charts, model comparison, and forecasts.
Note: The uploaded report is a rendered PDF. To run the analysis, you need the original R/R Markdown source code and the Excel dataset.

Limitations
- Model comparison uses only three test years (2023–2025).
- Forecasts based on historical trends may not capture policy, economic, or technological changes.
- Some dataset fields contain missing values.
- Long-range forecast uncertainty increases over time.
Future Scope
- Test models over longer validation periods.
- Incorporate EV prices, charging availability, government policies, and economic indicators.
- Compare additional forecasting methods and validate them on unseen data.
References
- International Energy Agency – Global EV Outlook 2026
- R Project
- R Markdown
- forecast R package
Author
Gundlapally Ananya

Academic case study: Electric Vehicle Adoption and Market Trend Analysis Using Data Science in R.
