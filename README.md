# Sample sizing in clinical studies

In clinical trial or epidemiological study, one of the critical point is the estimation of the good sample size which will help to grant detection of significant difference and then get a good power for statistical test in our study.

It is important to have the good sample size for many reason. Firstly, for ethic aspect. Small sample will not allow to detect significant effect or can conduct to wrong conclusion and large sample will include patients or individual that we would not need. Then we can loose human, financial and logistic resources.

Determination of sample size is based on power of statistical test. Power of statistical test is the probability to reject null hypothesis knowing that alternative hypothesis is right. It means that power is the complementary of type II risk denoted $\beta$ :  $P= 1-\beta$.

In other words, power of statistical test is the probability to conclude to a true significative difference on the priincipal outcome. In this work, we will only focus on the case of one simple principal outcome with a statistical test to attend the primary endpoint. We will provide another work in case of composite principal outcome.

Power of statistical test depends on some factors such as:
- Sample size
- Difference to be detected
- Test significance level or type I risk denoted $\alpha$
- Variability of observations ( for example correlation between observations, variance, lost to follow up)

Thus a value of sample size determine a value of power. And a value of power define of value of sample size. Usually, to compute sample size we should:
- define the primary endpoint and the statistical test to be used 
- define the expected difference or value of principal endpoint of the study (for instance difference and standard deviation of mean height between treatment group, proportion of an event in the exposition group, survival duration without disease progression between exposition group)
- define the ratio between exposition group (case control study)
- define lost to follow up percentage if needed
- define the risks $\alpha$ and $\beta$. Usually $\alpha=0.05$ and $\beta=0.8$.

Once all previous parameters defined, there are different ways to compute sample size in different situation or design of study.

- Using formula of sample size: Formula to compute sample size depends on principal outcome (proportion comparison, mean comparison, Odds ratio or relative risk, time-to-event analysis).
 - Proportion comparison: $N=\frac{2 \times \pi (1-\pi) (z_{1-\alpha /2} + z_{1-\beta})^2}{(p_1 - p_2)^2}$ where $p_1$ is the proportion of event in group of exposed patients, $p_2$ is the proportion of event in group of non exposed patients, $\pi = \frac{p_1+p_2}{2}$, $z_{\alpha/2}$ the quantile associated to level $\alpha/2$ and $z_{\beta}$ the quantile associated to level $\beta$. We can notice that N increase when difference between proportion is small.
 - Mean comparison: $N=\frac{2 \times \sigma^2 (z_{1-\alpha /2} + z_{1-\beta})^2}{(\bar{x}_1 - \bar{x}_2)^2}$ where $\bar{x}_1$ is the mean of outcome is group 1, $\bar{x}_2$ is the mean of outcome is group 2, $\sigma$ the standard deviation of outcome, $z_{\alpha/2}$ the quantile associated to level $\alpha/2$ and $z_{\beta}$ the quantile associated to level $\beta$
 - OR of intervention parameter: same formula for proportion comparison with $p_1=\frac{1}{1+\frac{1-p_2}{OR \times p_2}}$. This supposed to know also the baseline value of proportion of event in the control group in addition of all others parameters enumerated in estimation of sample size in case of proportion comparison.
 - RR in longitudinal analysis: same formula for proportion comparison with $p_1$ incidence in exposed group, $p_2$ incidence in non exposed group, $p_1= RR \times p_2$. This supposed to know also the baseline value of proportion of event in the non exposed group in addition of all others parameters enumerated in estimation of sample size in case of proportion comparison.

Note that all these formula do not take into account the ratio of patient distribution (1 case for 4 control for example) or rate of lost to follow up. These two factors can impact size of sample and need to be taken into account. In case of ratio, we introduce a factor $\gamma = \frac{n_2}{n_1}$ which represent the ratio in the previous formula. For example for proportion comparison we have:
- Proportion comparison: $N=\frac{(z_{1-\alpha /2 } \sqrt{(1+\gamma).\pi.(1-\pi)} + z_{1-\beta} \sqrt{\gamma . p_1(1-p_1)+p_2(1-p_2)})^2}{\gamma \times (p_1 - p_2)^2}$


- Using statistical software such as R (package epiDisplay or epiR), SAS (PROC POWER),or PASS: There are many software and webapp which offer sample size calculation. We focus on R with package epiDisplay. With this package we can estimate sample size and power of a study. There are many functions in this package to estimate either sample size, or power in different design of study and for different test of primary outcome.

- Using empirical simulation: The process of this method is simple but you must define a size for your sample in advance, then estimate the power based on many different sample simulate and then select the good sample size with the best power or the sample size from which we have not a significant gain of power. In this method we consider the power as the proportion of significant p-value. It means that we test the primary endpoint on each sample simulated and calculate the proportion of times that we have a significant p-value (p-value < $\alpha$) over all p-values computed.

