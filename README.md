# Business Case: Yulu - Hypothesis Testing

## About Yulu
Yulu is India’s leading micro-mobility service provider, offering unique vehicles for daily commuting. Starting as a mission to eliminate traffic congestion in India, Yulu provides a safe and eco-friendly commuting solution through a user-friendly mobile app. Yulu zones are strategically placed at metro stations, bus stops, office spaces, and residential areas to ensure smooth first and last-mile connectivity. 

### Problem Statement
Yulu has experienced significant dips in its revenue and seeks to understand the factors that influence the demand for its shared electric cycles. The company is particularly interested in the variables that predict demand and how well they describe the electric cycle demand in the Indian market.

## Objective
To identify:
1. Which variables are significant in predicting the demand for shared electric cycles.
2. How well these variables describe electric cycle demand.

## Data Overview
The dataset consists of information about the demand for Yulu cycles, with the following key variables:
- `datetime`: The timestamp of the ride.
- `season`: The season during the ride.
- `holiday`: Whether the ride was on a holiday.
- `workingday`: Whether the ride was on a working day.
- `weather`: Weather condition during the ride.
- `temp`: Temperature during the ride.
- `atemp`: Feels-like temperature during the ride.
- `humidity`: Humidity level during the ride.
- `windspeed`: Wind speed during the ride.
- `casual`: Number of casual riders.
- `registered`: Number of registered riders.
- `count`: Total number of rides.

### Sample Data
| datetime            | season | holiday | workingday | weather | temp  | atemp | humidity | windspeed | casual | registered | count |
|---------------------|--------|---------|------------|---------|-------|-------|----------|-----------|--------|------------|-------|
| 2011-01-01 00:00:00 | 1      | 0       | 0          | 1       | 9.84  | 14.4  | 81       | 0.0       | 3      | 13         | 16    |
| 2011-01-01 01:00:00 | 1      | 0       | 0          | 1       | 9.02  | 13.6  | 80       | 0.0       | 8      | 32         | 40    |
| 2011-01-01 02:00:00 | 1      | 0       | 0          | 1       | 9.02  | 13.6  | 80       | 0.0       | 5      | 27         | 32    |

### Data Insights
- **Datetime:** Timestamp of rides.
- **Season & Weather:** Strong impact on user preferences.
- **Registered & Casual Riders:** Provides insight into customer segmentation.

## Data Visualization
### Distribution of Numerical Variables
- **Temperature Distribution:** Visualized via histograms.
- **Humidity Distribution:** Represented in a histogram.
- **Rental Count Distribution:** Showcased using a KDE plot.

### Correlation Matrix
- Strong positive correlations:
  - `temp` & `atemp` (as expected).
  - `casual` & `registered` riders.
  - `registered` riders & total trip count.
  
- Weak correlations:
  - Weather with ridership (unclear).
  
### Handling Outliers
Outliers in the `count` variable were handled using IQR-based filtering, reducing the dataset from 10,886 to 10,583 rows.

## Hypothesis Testing

### 1. Does Working Day Affect the Number of Electric Cycles Rented?
- **Null Hypothesis (H0):** Working day has no effect on the number of electric cycles rented.
- **Alternative Hypothesis (H1):** Working day has an effect on the number of electric cycles rented.

#### Results:
- **T-statistic:** -2.45
- **P-value:** 0.0143
- **Conclusion:** Since the p-value (0.0143) is less than 0.05, we reject the null hypothesis. There is evidence to suggest that working days have an effect on the number of electric cycles rented.

### 2. Does Season Affect the Number of Electric Cycles Rented?
- **Null Hypothesis (H0):** Season has no effect on the number of electric cycles rented.
- **Alternative Hypothesis (H1):** Season has an effect on the number of electric cycles rented.

#### Results:
- **K-statistic:** 619.37
- **P-value:** 6.38e-134
- **Conclusion:** Since the p-value is extremely small, we reject the null hypothesis. There is strong evidence to suggest that the number of cycles rented differs across different seasons.

### 3. Does Weather Affect the Number of Electric Cycles Rented?
- **Null Hypothesis (H0):** Weather has no effect on the number of electric cycles rented.
- **Alternative Hypothesis (H1):** Weather has an effect on the number of electric cycles rented.

#### Results:
- **K-statistic:** 284.82
- **P-value:** 1.76e-62
- **Conclusion:** The p-value is much smaller than the significance level, leading to the rejection of the null hypothesis. Weather significantly affects the number of electric cycles rented.

## Conclusion
This analysis provides valuable insights into the factors influencing the demand for Yulu electric cycles. By understanding the impact of working days, seasons, and weather conditions, Yulu can make data-driven decisions to improve its service offerings and potentially recover from its recent revenue dips.
