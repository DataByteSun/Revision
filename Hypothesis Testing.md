# Hypothesis Testing
## Introduction:
Hypothesis testing is a fundamental statistical method used to draw conclusions about population parameters based on sample data. It provides a structured framework for making decisions and drawing inferences in scientific research, business analytics, and various other fields. By systematically evaluating hypotheses, researchers can assess the validity of their assumptions and make informed decisions.
- Formulating Hypotheses: 
The first step in hypothesis testing is to formulate hypotheses. There are two main hypotheses:
  - Null Hypothesis (H0): This is the default assumption or status quo. It typically represents no effect, no difference, or no relationship in the population.
  - Alternative Hypothesis (H1): This hypothesis represents what the researcher hopes to demonstrate or prove. It contradicts the null hypothesis and suggests the presence of an effect, difference, or relationship in the population.
For example, if a researcher wants to test whether a new drug is effective in treating a particular condition, the null hypothesis might be that the drug has no effect, while the alternative hypothesis would assert that the drug does have an effect.
- Choosing a Test Statistic and Significance Level:
After formulating hypotheses, the next step is to select an appropriate test statistic and significance level (α). The test statistic is a numerical summary of the sample data that is used to assess the plausibility of the null hypothesis. The choice of test statistic depends on factors such as the research question, type of data, and assumptions about the population distribution.
The significance level (α) determines the threshold for rejecting the null hypothesis. Commonly used significance levels include 0.05 and 0.01, which correspond to 5% and 1% probability of Type I error, respectively. Researchers must carefully consider the significance level based on the consequences of Type I and Type II errors in their specific context.
- Collecting Data and Calculating the Test Statistic
Once hypotheses are formulated and the test statistic and significance level are chosen, researchers collect data from a sample that is representative of the population of interest. They then calculate the test statistic using appropriate formulas or statistical software.
For example, if conducting a t-test to compare means between two groups, the test statistic would be the t-value calculated from sample means, standard deviations, and sample sizes.
- Determining the p-value
The p-value is a crucial measure in hypothesis testing that quantifies the strength of evidence against the null hypothesis. It represents the probability of observing the test statistic (or one more extreme) if the null hypothesis is true. A smaller p-value indicates stronger evidence against the null hypothesis.
- Making a Decision
Based on the calculated p-value and chosen significance level, researchers make a decision to either reject or fail to reject the null hypothesis:
  - If the p-value is less than the significance level (α), the null hypothesis is rejected. This suggests that the observed results are unlikely to occur if the null hypothesis is true, providing evidence in favor of the alternative hypothesis.
  - If the p-value is greater than or equal to the significance level, the null hypothesis is not rejected. This indicates that the observed results are consistent with what would be expected under the null hypothesis.
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

## Weather Dependence on Season:
- Null Hypothesis (H0): Weather conditions are independent of the season.
- Alternate Hypothesis (H1): Weather conditions are dependent on the season.

#### Notes:
Test used here are [Mann-Whitney U test](), [kruskal](), [Chi-Square Statistic](), also [KD plot]() have used. 
