# Types of Hypothesis Test
## 1. Understanding the Mann-Whitney U Test
The Mann-Whitney U test is a statistical method used to compare two independent groups when the data is not normally distributed. It's like comparing two teams in a game where you can't assume that the players' abilities follow a normal bell curve. <br />

**Purpose:** <br />
The main goal of the Mann-Whitney U test is to determine if there's a significant difference between the two groups. For example, you might use it to see if there's a difference in test scores between students who study with flashcards versus those who study with textbooks. <br />

**Assumptions:** <br />
This test doesn't assume that the data follows a specific pattern, like a normal distribution.  <br />
It's also robust to differences in variance between the groups. <br />

**How it Works:** <br />
1. Ranking: First, you rank all the data points together from smallest to largest, regardless of which group they belong to.
2. Summing Ranks: Then, you add up the ranks for each group separately. This gives you a U value for each group.
3. Comparison: You compare the U values to see if there's a significant difference. If one group consistently has higher ranks, it suggests that group tends to have higher values. <br />

**Interpretation:** <br />
If the U value is small, it means one group tends to have smaller values overall. If it's large, one group tends to have larger values. You then use statistical tables or software to find the significance level, usually denoted as p-value, to see if the difference is meaningful or just due to chance. <br />

**Note:** <br />
The Mann-Whitney U test is a handy tool when you can't rely on normal distribution assumptions. It helps researchers determine if there's a real difference between two groups, even when their data doesn't follow the usual statistical rules. <br />

**Formula:** <br />
Let's denote:<br />
- $n_1$ as the number of observations in Group 1
- $n_2$ as the number of observations in Group 2 
- $R_1$ as the sum of ranks in Group 1 
- $U_1$ as the Mann-Whitney U statistic for Group 1 
- $U_2$ as the Mann-Whitney U statistic for Group 2 

The Mann-Whitney U statistic for Group 1 is calculated using the formula: <br/>
$U_1 = n_1 \times n_2 + \frac{n_1 \times (n_1 + 1)}{2} - R_1$

Similarly, the Mann-Whitney U statistic for Group 2 is calculated using the formula:<br/>
$U_2 = n_1 \times n_2 - U_1$

Then, you can use these $U$ values to compare the two groups and determine statistical significance. <br/>

**Determine the p-value:**(ooptional) <br/>
To calculate the minimum of $U_1$ and $U_2$, denoted as $U$, you simply take the smaller of the two values. In this case: <br/>
$U = \min(U_1, U_2)$

Once you have the value of $U$, you can compare it to the critical value from the Mann-Whitney U table or use statistical software to find the p-value directly.<br/>
- Manual Lookup: You can use a Mann-Whitney U table, which provides critical values for different sample sizes and significance levels. Find the critical value for $U$ based on the sample sizes $n_1$ and $n_2$.
- Using Statistical Software: Alternatively, you can use statistical software to find the p-value directly. You would typically perform a Mann-Whitney U test using software such as R, Python (with libraries like scipy), or specialized statistical software packages.

After obtaining the critical value from the table or the p-value from software, you compare $U$ to the critical value from the table or the p-value from software to determine statistical significance. <br/>

**Example:** <br/>

Let's say we have two groups, Group A and Group B, with the following data: <br/>
- Group A: 12, 14, 16, 18 
- Group B: 10, 15, 17

First, rank all the data together:
- Group A: 12(1), 14(2), 16(3), 18(4) 
- Group B: 10(1), 15(2), 17(3)

Now, calculate the sum of ranks for each group: <br/>
- For Group A: 
  - $R_1 = 1 + 2 + 3 + 4 = 10$
- For Group B: 
  - $R_2 = 1 + 2 + 3 = 6$

Using the formula, we find the Mann-Whitney U statistic for Group A: <br/>
$U_1 = (4 \times 3) + \frac{4 \times (4 + 1)}{2} - 10 = 12$

Then, the Mann-Whitney U statistic for Group B: <br/>
$U_2 = (4 \times 3) - 12 = 12$

Group A and Group B had Mann-Whitney U statistics of $U_1 = U_2 = 12$, assuming the sample sizes for both groups are $n_1 = 4$ and $n_2 = 3$, we calculate $U$ as the minimum of $U_1$ and $U_2$, which is $12$.<br/>

Then, we would consult a Mann-Whitney U table or use statistical software to find the p-value associated with $U = 12$ and the given sample sizes. If the p-value is less than the predetermined significance level (usually $0.05$), we reject the null hypothesis and conclude that there is a significant difference between the groups. If it's greater, we fail to reject the null hypothesis. <br/>

______________________________________
_____________________________________

## 2. Understanding the Kruskal-Wallis Test
The Kruskal-Wallis test is a non-parametric method used to compare three or more independent groups. <br/>
It's helpful when the assumptions for ANOVA (Analysis of Variance) aren't met, such as when the data isn't normally distributed.<br/>

**Purpose:** <br />
Main goal: Determine if there's a significant difference in the medians of the groups.  <br />
Example: Comparing the effectiveness of three different teaching methods on student performance. <br />

**Assumptions:** <br />
Does not assume normal distribution.  <br />
Assumes independent samples from each group.<br />

**How it Works:** <br />
1. Ranking: Rank all data points from smallest to largest across all groups. 
2. Calculating Test Statistic (H): Calculate the Kruskal-Wallis test statistic (H) using the ranked data.
3. Comparison: Compare the calculated H value to a critical value from the chi-square distribution to determine significance.

**Interpretation:** <br />
If the calculated H value is greater than the critical value, there's evidence to reject the null hypothesis, indicating that at least one group's median is different. <br />
If the H value is smaller, there's no significant difference between the groups. <br />

**Formula:** <br />
$H = \frac{12}{N(N+1)} \left( \sum_{i=1}^{g} \frac{R_i^2}{n_i} \right) - 3(N+1)$

Where: <br />
- $g$ = number of groups
- $N$ = total number of observations
- $R_i$ = sum of ranks in group $i$
- $n_i$ = number of observations in group $i$

**Example:**
- Suppose we have three groups with the following data:
  - Group 1: 10, 12, 14 
  - Group 2: 8, 9, 11
  - Group 3: 13, 15, 16
- Rank all data together: 8, 9, 10, 11, 12, 13, 14, 15, 16 
- Calculate sum of ranks for each group. 
- Use the formula to calculate the test statistic $H$.
- Compare $H$ to critical value from the chi-square distribution. 

**Determining p-value:** <br />
Once $H$ is calculated, it's compared to a critical value from the chi-square distribution with degrees of freedom equal to $g-1$ (where $g$ is the number of groups). <br />
The p-value is determined by comparing the calculated $H$) value to the chi-square distribution under the null hypothesis. <br />
If the p-value is less than a predetermined significance level (usually 0.05), the null hypothesis is rejected, indicating a significant difference between the groups. <br />

**Conclusion:** <br />
The Kruskal-Wallis test is a valuable tool for comparing multiple independent groups when assumptions of ANOVA are not met. It allows researchers to assess whether there are significant differences in medians across groups, providing insights into potential group effects.<br />
______________________________________
_________________________________
## 3. Understanding the Chi-Square Test
The Chi-Square test is a statistical method used to determine whether there is a significant association between two categorical variables.  <br />
It's commonly used in research to analyze data from surveys, experiments, and observational studies.  <br />

**Purpose:** <br />
Main goal: Assess whether there's a significant difference between the expected frequencies and the observed frequencies.  <br />
Example: Examining the association between smoking habits (smoker/non-smoker) and lung cancer risk (yes/no).  <br />

**Assumptions:** <br />
The variables being compared must be categorical, and the data must be independent.  <br />
The expected frequency for each cell of the contingency table should be at least 5 for the test to be valid.  <br />

**How it Works:** <br />
1. Formulating Hypotheses: Define null and alternative hypotheses regarding the association between the variables.
2. Creating Contingency Table: Organize the data into a contingency table, with rows representing one variable and columns representing the other.
3. Calculating Test Statistic ($\chi^2$): Calculate the Chi-Square test statistic ($\chi^2$) using the observed and expected frequencies from the contingency table.
4. Comparison: Compare the calculated $\chi^2$ value to a critical value from the Chi-Square distribution with appropriate degrees of freedom.

**Interpretation:** <br/>
- If the calculated $\chi^2$ value exceeds the critical value, we reject the null hypothesis, concluding that there is a significant association between the variables.
- If the $\chi^2$ value is smaller, we fail to reject the null hypothesis, suggesting no significant association.

**Formula:** <br/>

The Chi-Square test statistic ($\chi^2$) is calculated as:
$\chi^2 = \sum \frac{(O - E)^2}{E}$

Where:
- $O$ = observed frequency
- $E$ = expected frequency

**Example:** <br/>
- Suppose we have survey data on smoking habits and lung cancer risk: <br/>

|   | Lung Cancer (Yes) |  Lung Cancer (No) | 
| ------- | --------- |  ------- |
| Smoker  | 50  |  30  |
| Non-Smoker  | 20  |  60  |

- Calculate expected frequencies for each cell.
- Use the formula to calculate the Chi-Square test statistic ($\chi^2$).
- Compare the calculated $\chi^2$ value to the critical value from the Chi-Square distribution.

**Determining p-value:** <br/>
- Once $\chi^2$ is calculated, it's compared to a critical value from the Chi-Square distribution with degrees of freedom determined by the contingency table.
- The p-value represents the probability of observing a $\chi^2$ value as extreme as, or more extreme than, the calculated value, assuming the null hypothesis is true.
- If the p-value is less than a predetermined significance level (usually 0.05), the null hypothesis is rejected, indicating a significant association.

**Conclusion:** <br/>
The Chi-Square test is a valuable tool for assessing associations between categorical variables.<br/>
It provides insights into relationships between variables, aiding researchers in understanding patterns in data collected from categorical responses.<br/>

**Example Solution:** <br/>
Step 1: Formulate Hypotheses: <br/>
- Null Hypothesis (H0): There is no association between smoking habits and lung cancer risk.
- Alternative Hypothesis (H1): There is an association between smoking habits and lung cancer risk.

Step 2: Create Contingency Table:
|   | Lung Cancer (Yes) |  Lung Cancer (No) | Total | 
| ------- | --------- |  ------- | ------ |
| Smoker  | 50  |  30  | 80 | 
| Non-Smoker  | 20  |  60  | 80 |
| Total  | 70  |  90  | 160 |

Step 3: Calculate Expected Frequencies: <br/>
- To calculate expected frequencies, we first find the row and column totals and use these to compute the expected frequency for each cell:
  - Row Total for Smokers: 80
  - Row Total for Non-Smokers: 80
  - Column Total for Lung Cancer (Yes): 70
  - Column Total for Lung Cancer (No): 90

The expected frequency for each cell is given by: <br/>
$\text{Expected Frequency} = \frac{\text{Row Total} \times \text{Column Total}}{\text{Grand Total}}$

For example, the expected frequency for the cell corresponding to Smokers with Lung Cancer (Yes) is:  <br/>
$\text{Expected Frequency} = \frac{80 \times 70}{160} = 35$
Similarly, calculate expected frequencies for all cells.

Step 4: Calculate Chi-Square Test Statistic ($\chi^2$):  <br/>
- Use the formula $\chi^2 = \sum \frac{(O - E)^2}{E}$, where $O$ is the observed frequency and $E$ is the expected frequency.  <br/>
Let's calculate:  <br/>
$\chi^2 = \frac{(50 - 35)^2}{35} + \frac{(30 - 35)^2}{35} + \frac{(20 - 35)^2}{35} + \frac{(60 - 35)^2}{35}$
$\chi^2 = \frac{225}{35} + \frac{25}{35} + \frac{225}{35} + \frac{625}{35}$
$\chi^2 = 6.43 + 0.71 + 6.43 + 17.86$
$\chi^2 = 31.43$

Step 5: Compare $\chi^2$ to Critical Value:  <br/>
- The critical value of $\chi^2$ depends on the degrees of freedom (df) which is calculated as $(r - 1) \times (c - 1)$, where $r$ is the number of rows and $c$ is the number of columns.
- Here, $df = (2 - 1) \times (2 - 1) = 1$.
- From the Chi-Square distribution table or software, at $df = 1$ and significance level $\alpha = 0.05$, the critical value is approximately $3.841$.
Since $\chi^2 = 31.43$ is greater than $3.841$, we reject the null hypothesis.  <br/>

Step 6: Determine p-value:  <br/>
- The p-value is the probability of obtaining a $\chi^2$ value as extreme as, or more extreme than, the calculated value, assuming the null hypothesis is true.
- We can use statistical software to find the p-value associated with $\chi^2 = 31.43$.
- Suppose the calculated p-value is $< 0.001$ (very small).
**Since the p-value $< 0.05$, we reject the null hypothesis. There is a significant association between smoking habits and lung cancer risk.**  <br/>
______________
______________
## 4. Understanding theANOVA (Analysis of Variance) Test
ANOVA is a statistical method used to compare means between two or more groups to determine if there are statistically significant differences.<br />
It's commonly used in research to analyze experiments with multiple treatment groups.<br />

**Purpose:** <br />
Main goal: Assess whether there are differences in means among the groups. <br />
Example: Comparing the effectiveness of three different diets on weight loss. <br />

**Assumptions:** <br />
Data within each group should be approximately normally distributed. <br />
Homogeneity of variances: Variances should be approximately equal across groups. <br />
Observations should be independent. <br />

**How it Works:** <br />
1. Formulating Hypotheses: Define null and alternative hypotheses regarding the means of the groups.
2. Calculating Sum of Squares: Calculate the total sum of squares (SST), sum of squares between groups (SSG), and sum of squares within groups (SSW).
3. Degrees of Freedom: Calculate degrees of freedom for between groups (DFG) and within groups (DFW).
4. Calculating F-ratio: Compute the F-ratio by dividing the mean square between groups (MSG) by the mean square within groups (MSW).
5. Comparison: Compare the calculated F-ratio to a critical value from the F-distribution to determine significance.

**Interpretation:** <br/>
- If the calculated F-ratio exceeds the critical value, we reject the null hypothesis, indicating that there are significant differences among the group means.
- If the F-ratio is smaller, we fail to reject the null hypothesis, suggesting no significant differences.
  
**Formula:** <br/>
The F-ratio is calculated as: <br/>
$F = \frac{MSW}{MSG} = \frac{SSW}{DFW} \div \frac{SSG}{DFG}$

**Example:** <br />
- Suppose we have weight loss data from three diet groups: <br />
  - Diet A: 5, 7, 6
  - Diet B: 4, 8, 9
  - Diet C: 3, 5, 4
- Calculate the mean for each group and the overall mean.
- Calculate the total sum of squares (SST), sum of squares between groups (SSG), and sum of squares within groups (SSW).
- Use these values to calculate the F-ratio.

**Determining p-value:** <br />
Once the F-ratio is calculated, it's compared to a critical value from the F-distribution with appropriate degrees of freedom. <br />
The p-value represents the probability of observing an F-ratio as extreme as, or more extreme than, the calculated value, assuming the null hypothesis is true. <br />
If the p-value is less than a predetermined significance level (usually 0.05), the null hypothesis is rejected, indicating significant differences among group means. <br />

**Conclusion:** <br />
ANOVA is a powerful tool for comparing means across multiple groups. <br />
It allows researchers to determine whether there are significant differences in treatment effects, providing insights into the effectiveness of different interventions. <br />

**Example Solution:** <br/>
Step 1:Calculate Mean for Each Group and Overall Mean: <br/>
- For Diet A: Mean = (5 + 7 + 6) / 3 = 6
- For Diet B: Mean = (4 + 8 + 9) / 3 = 7
- For Diet C: Mean = (3 + 5 + 4) / 3 = 4
- Overall Mean = (6 + 7 + 4) / 3 = 17 / 3 ≈ 5.67

Step 2: Calculate Total Sum of Squares (SST), Sum of Squares Between Groups (SSG), and Sum of Squares Within Groups (SSW):  <br/>

i. Calculate Total Sum of Squares (SST): <br />
$\text{SST} = \sum (X_{ij} - \bar{X})^2 = (5 - 5.67)^2 + (7 - 5.67)^2 + (6 - 5.67)^2 + (4 - 5.67)^2 + (8 - 5.67)^2 + (9 - 5.67)^2 + (3 - 5.67)^2 + (5 - 5.67)^2 + (4 - 5.67)^2$
$= 1.89 + 0.89 + 0.12 + 2.56 + 3.61 + 7.42 + 8.12 + 0.12 + 2.56 = 27.29$

ii. Calculate Sum of Squares Between Groups (SSG):<br />
$\text{SSG} = \sum (n_i \times (\bar{X}_i - \bar{X})^2) = (3 \times (6 - 5.67)^2) + (3 \times (7 - 5.67)^2) + (3 \times (4 - 5.67)^2)$
$= (3 \times 0.1089) + (3 \times 1.8489) + (3 \times 3.1489) = 0.3267 + 5.5467 + 9.4467 = 15.32$

iii.Calculate Sum of Squares Within Groups (SSW): <br />
$\text{SSW} = \text{SST} - \text{SSG} = 27.29 - 15.32 = 11.97$

Step 3: Calculate Degrees of Freedom (DFG and DFW):<br />
$DFG = \text{Number of groups} - 1 = 3 - 1 = 2$
$DFW = \text{Total number of observations} - \text{Number of groups} = 9 - 3 = 6$

Step 4: Calculate F-Ratio: <br />
$F = \frac{MSG}{MSW} = \frac{SSG / DFG}{SSW / DFW} = \frac{15.32 / 2}{11.97 / 6} = \frac{7.66}{1.995} \approx 3.84$

Step 5: Determine p-value: <br />
Using statistical software or F-distribution tables, at $DFG = 2$ and $DFW = 6$ and a significance level of $\alpha = 0.05$, the critical F-value is approximately $5.14$. <br />
The p-value associated with an F-ratio of $3.84$ (calculated) is found to be greater than $0.05$. <br />

**Since the calculated F-ratio (3.84) is less than the critical F-value (5.14) and the p-value is greater than 0.05, we fail to reject the null hypothesis. There is insufficient evidence to conclude that there are significant differences in weight loss among the three diet groups.** <br />
____________________
____________________
