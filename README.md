# A-B-Testing-Analysis-Marketing-Campaign-Effectiveness


**Project Overview**
Designed and conducted an A/B testing analysis to evaluate the effectiveness of two marketing campaign variants in driving customer signups for an e-commerce business. The objective was to determine whether differences in conversion performance were statistically significant and could support a wider campaign rollout.ny.

**Business Problem**
Marketing stakeholders sought to identify the most effective campaign variant for customer acquisition while ensuring that any observed improvement in conversion rates was supported by statistical evidence before committing additional marketing resources.
**Tools & Technologies**
-	Python
- Pandas
-	NumPy
-	SciPy
-	Matplotlib
-	A/B Testing
-	Statistical Hypothesis Testing
-	Chi-Square Test of Independence
-	Marketing Analytics
-	Data Analysis

**Data Preparation**
-	Imported and cleaned customer interaction data using Python and Pandas.
-	Excluded the control group to focus on the comparison between the two active campaign variants.
-	Constructed a contingency table to analyse the relationship between campaign type and signup outcomes.
-	Calculated conversion rates for each campaign group.


**Conversion Rates**
- Marketing campaign1	32.8%
- Marketing campaign2	37.8%

Initial analysis showed that Marketing campaign 2 achieved a 5-percentage-point higher signup rate than Marketing campaign 1

**Statistical Methodology**
A Chi-Square Test of Independence was conducted to determine whether the observed difference in conversion rates was statistically significant.

**Hypotheses**
- Null Hypothesis (H₀):
There is no relationship between mailer type and signup rate.
- Alternative Hypothesis (H₁):
There is a relationship between mailer type and signup rate.
- Significance Level
α = 0.05

**Results**
-	Chi-Square Statistic: 1.94
-	Critical Value: 3.84
- P-Value: 0.164

Since:
- χ² (1.94) < Critical Value (3.84)
- P-Value (0.164) > 0.05
The null hypothesis could not be rejected.

**Interpretation**
Since the Chi-Square statistic (1.94) was lower than the critical value (3.84) and the p-value (0.164) exceeded the significance threshold of 0.05, the null hypothesis could not be rejected. The observed difference in conversion rates was therefore not statistically significant.

**Key Insights**
Although Campaign 2 outperformed Campaign 1 in terms of observed conversion rate, the statistical analysis indicated insufficient evidence to conclude that the uplift was driven by the campaign itself rather than random variation. This highlights the importance of validating performance improvements through hypothesis testing before making strategic business decisions.

**Recommendation**
- Conduct additional testing with a larger sample size to increase statistical power.
- Explore alternative campaign creatives, messaging approaches, and customer segments.
- Continue monitoring conversion performance to identify statistically significant opportunities for optimisation.


**Business Impact**
-	Evaluated the effectiveness of marketing campaigns using a rigorous experimental framework.
-	Identified a potential 15.2% uplift in customer conversions between campaign variants.
-	Applied statistical testing to distinguish genuine performance improvements from random variation.
-	Enabled evidence-based decision-making and reduced the risk of allocating marketing budget to an unproven campaign strategy.
-		Demonstrated the value of data-driven experimentation in marketing optimisation and customer acquisition initiatives.
.
