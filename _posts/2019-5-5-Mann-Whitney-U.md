---
title: "Mann Whitney U Test Tool"
excerpt_separator: "<!--more-->"
categories:
  - Stat
tags:
  - Tool
  - Web App
author_profile: true
mathjax: true
comments: true
---

Use of Mann-Whitney test
----------------------------

The Mann–Whitney U test is a non-parametric alternative test to the independent sample t-test. It is a test of both location and shape. Given two independent samples, it tests whether one variable tends to have values higher than the other (test on sample means). Theoretically, in large samples the Mann-Whitney test can also detect differences in spread even when the medians are very similar. 

This test does not assume that the samples is normally distributed, that the variances of the two populations are equal or that the two sample sizes are equal.

Hence, in summary:
  - The Mann-Whitney U test is used as an alternative to a t test when the data are not normally distributed;
  - The Mann-Whitney U test is usually used in cases that data sample size is small;
  - The test can detect differences in shape and spread as well as just differences in medians.
  

Test Statistic and Calculation Example
----------------------
Consider a test designed to investigate the effectiveness of a new drug. A total of n=10 participants are randomized to receive either the new drug or a placebo. Participants are asked to record the significance of discomfort (the higher the value, the more uncomfortable). The data are shown below.

| Placebo     | 7 | 5 | 6 | 4 | 12 |
| :---        | :---:  |  :---:  | :---:  | :---:  |  ---: |
| New Drug    | 3 | 6 | 4 | 2 | 1  |

The hypothesis is given below and and the test is supposed to run at the 5% level of significance (i.e., $$\alpha=0.05$$).: 

$$
H_{0}: The \ two \ populations \ are \ equal \ versus
\\
H_{1}: The \ two \ populations \ are \ not \ equal.
$$

The sample size is small ($$n_{1}=n_{2}=5$$), so a nonparametric test is appropriate. We are going to use Mann Whitney U test to solve this problem. 

The test statistic for the Mann Whitney U Test is denoted $$U$$, whose whose distribution under the null hypothesis is known. In the case of small samples, the distribution is tabulated, but for sample sizes above ~20, approximation using the normal distribution is fairly good. 

### Calculation
The statistic, $$U$$, could be easily calculated by hand, especially for small samples. 

1. Assign ranks 

   The first step is to rank all the data. To do so we order the data from smallest to largest. This is done on the combined or total sample (i.e., pooling the data from the two treatment groups (n=10)), and assigning ranks from 1 to 10, as follows.
   
   | Sample Value (Ordered)  ||            Ranks   ||
   Placebo    |   New Drugs   | Placebo | New Drugs |
   |:---------| :-----------: | :-----: |---------: |
   |          |  1            |         |1          |
   |          |  2            |         | 2         |
   |          |  3            |         | 3         |
   |          |  2            |         | 2         |
   4          |  4            |  4.5    | 4.5       |
   5          |               | 6       |           |
   6          |  6            | 7.5     | 7.5       |
   7          |               | 9       |           |
   12         |               | 10      |           |
   
   For the tie values, we use their mean of ranks. 
   
2. Sum the ranks for each group
   
   The second step is to calculate the sum of ranks, $$R$$, of each group.  
   
   In the placebo group, 
   
   $$
   R_{1} = 4.5 + 6 + 7.5 + 9 + 10 = 37
   $$
   
   In the new drugs group,
   
   $$
   R_{2} = 1 + 2 + 3 + 2 + 4.5 + 7.5 = 18
   $$
   
3. Compute $$U$$
   
   Given,
   
   $$
   U_{i} = n_{1}n_{2} + \frac{n_{i}(n_{i}+1)}{2} - R_{i}
   
   U =  min( U_{1}, ..., U_{i})
   $$
   
   For this example,
   
   $$
   U_{1} = 5(5) + \frac{5(6)}{2} - 37 = 3
   \\
   U_{1} = 5(5) + \frac{5(6)}{2} - 18 = 22
   $$
  
   Thus, the test statistic is  $$U=3$$.
   
4. Compare $$U$$ with critical $$U$$
   
   In every test, we must determine whether the observed $$U$$ supports the null hypothesis. This is done following the same approach used in parametric testing. Specifically, we determine a critical value of $$U$$ such that,
   
   {: style="text-align:center"}
   If $$U \leq critical \ U$$, we reject $$H_{0}$$ in favor of $$H_{1}$$ and,
   if $$U > critical \ U$$ we do not reject $$H_{0}$$.
   
   <embed src="https://github.com/Hatchin/hatchin.github.io/blob/master/assets/images/Mann-Whitney-Table-CriticalValues.pdf" type="application/pdf" />