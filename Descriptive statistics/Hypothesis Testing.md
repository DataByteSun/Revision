# Hypothesis Testing
## Introduction:
Hypothesis testing is a powerful statistical tool for drawing conclusions from data. It guides decision-making in diverse fields like scientific research and business analytics.

- Formulating Hypotheses
  - Null Hypothesis (H0): Represents the default assumption, often stating no effect or difference.
  - Alternative Hypothesis (H1): Contradicts the null, asserting an effect, difference, or relationship.

- Choosing Test Statistic and Significance Level
  - Test Statistic: A summary of sample data used to evaluate the null hypothesis.
  - Significance Level (α): Determines the threshold for rejecting the null hypothesis. Common levels include 0.05 and 0.01.

- Collecting Data and Calculating Test Statistic
  - Researchers gather representative sample data and compute the test statistic, tailored to the research question and data type.

- Determining the p-value
  - The p-value quantifies evidence against the null hypothesis, indicating the likelihood of observing the test statistic under the null hypothesis.

- Making a Decision
  - If the p-value is less than α, the null hypothesis is rejected, favoring the alternative hypothesis.
  - If the p-value is greater than or equal to α, the null hypothesis is not rejected.
----------------------------
# Example:
### Dataset Overview: [(Dataset Link-1)]() [(Dataset Link-2)](https://www.kaggle.com/datasets/ranitsarkar01/yulu-bike-sharing-data)
The dataset provided contains information on the demand for shared electric cycles in the Indian market, collected by Yulu, India's leading micro-mobility service provider. Yulu aims to understand the factors influencing the demand for their shared electric cycles to address recent revenue dips. The dataset likely includes variables such as "Count" (number of electric cycles rented), "Workingday" (binary variable indicating whether it's a working day or not), "Weather" (weather conditions), "Season" (season of the year), and possibly other relevant factors.
- **Column Profiling:**
- datetime: datetime
- season: season (1: spring, 2: summer, 3: fall, 4: winter)
- holiday: whether day is a holiday liday or not.
- workingday: if day is neither weekend nor holiday is 1, otherwise is 0.
- weather: 1: Clear, Few clouds, partly cloudy, partly cloudy 2: Mist + Cloudy, Mist + Broken clouds, Mist + Few clouds, Mist 3: Light Snow, Light Rain + Thunderstorm + Scattered clouds, Light Rain + Scattered clouds 4: Heavy Rain + Ice Pallets + Thunderstorm + Mist, Snow + Fog
- temp: temperature in Celsius
- atemp: feeling temperature in Celsius
- humidity: humidity
- windspeed: wind speed
- casual: count of casual users
- registered: count of registered users
- count: count of total rental bikes including both casual and registered

## Questions: 
  Which variables are significant in predicting the demand for shared electric cycles in the Indian market?
  How well those variables describe the electric cycle demands?
##
## Task: 
### Working Day Effect on Electric Cycle Demand:
- Null Hypothesis (H0): There is no significant effect of working day on the number of electric cycles rented.
- Alternate Hypothesis (H1): Working day significantly affects the number of electric cycles rented.

### Seasonal Differences in Cycle Demand:
- Null Hypothesis (H0): The number of cycles rented is similar across different seasons.
- Alternate Hypothesis (H1): The number of cycles rented varies across different seasons.
  
### Weather Impact on Cycle Demand:
- Null Hypothesis (H0): The number of cycles rented is similar across different weather conditions.
- Alternate Hypothesis (H1): The number of cycles rented varies across different weather conditions.

### Weather Dependence on Season:
- Null Hypothesis (H0): Weather conditions are independent of the season.
- Alternate Hypothesis (H1): Weather conditions are dependent on the season.

#### Notes:
Test used here are [Mann-Whitney U test](), [kruskal](), [Chi-Square Statistic](), also [KD plot]() have used. 
