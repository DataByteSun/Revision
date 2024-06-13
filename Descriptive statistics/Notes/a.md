# Types of Hypothesis Test
## 1. Understanding the Mann-Whitney U Test
The Mann-Whitney U test is a statistical method used to compare two independent groups when the data is not normally distributed. It's like comparing two teams in a game where you can't assume that the players' abilities follow a normal bell curve. <br />

**Purpose:** <br />
The main goal of the Mann-Whitney U test is to determine if there's a significant difference between the two groups. For example, you might use it to see if there's a difference in test scores between students who study with flashcards versus those who study with textbooks. <br />

**Assumptions:** <br />
This test doesn't assume that the data follows a specific pattern, like a normal distribution. It's also robust to differences in variance between the groups. <br />

**How it Works:** <br />
- Ranking: First, you rank all the data points together from smallest to largest, regardless of which group they belong to.
- Summing Ranks: Then, you add up the ranks for each group separately. This gives you a U value for each group.
- Comparison: You compare the U values to see if there's a significant difference. If one group consistently has higher ranks, it suggests that group tends to have higher values. <br />

**Interpretation:** <br />
If the U value is small, it means one group tends to have smaller values overall. If it's large, one group tends to have larger values. You then use statistical tables or software to find the significance level, usually denoted as p-value, to see if the difference is meaningful or just due to chance. <br />

**Note:** <br />
The Mann-Whitney U test is a handy tool when you can't rely on normal distribution assumptions. It helps researchers determine if there's a real difference between two groups, even when their data doesn't follow the usual statistical rules. <br />

-----------------------------------
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


