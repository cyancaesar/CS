What is it all about?

1. Sampling Dist. of the sample mean $\bar{X}$ (*One Sample*)
2. Sampling Dist. of the difference between two means $\bar{X_1}-\bar{X_2}$ (*Two Samples*)
3. Sampling Dist. of the sample proportion $\hat{p}$ (*One Sample*)
4. Sampling Dist. of the difference between two proportions $\hat{p_1}-\hat{p_2}$ (*Two Samples*)

What is the problem?

The above sampling distributions are an estimation of the mean and the proportion for the true population. These are called *point estimators* for either one sample or two samples.

Confidence Interval is introduced to give an interval for a population mean and proportion that resides in between the interval.

**Confidence Intervals**
1. Confidence Interval of the mean $\micro$ (if $\sigma^2$ is known)
	1. Point estimate $\bar X$
	2. Error will not exceed $Z_{\frac{a}{2}}\frac{\sigma}{\sqrt{n}}$ represented by $e$
2. Confidence Interval of $\micro_1-\micro_2$
	1. Point estimate $\bar{X_1}-\bar{X_2}$
3. Confidence Interval of the proportion $p$
	1. Point estimate $\hat{p}=\frac{X}{n}$
4. Confidence Interval of $\hat{p_1}-\hat{p_2}$
	1. Point estimate $\hat{p_1}-\hat{p_2} = \frac{X_1}{n_1}-\frac{X_2}{n_2}$

---

#### Sampling Distribution of a Sample Mean $\bar{X}$

If $X_1,X_2,...,X_n$ is a sample of size $n$ taken from the $N(\micro, \sigma)$.
Then, $\bar{X}\sim N(\micro, \frac{\sigma}{\sqrt n})$
$E(\bar{X})= \micro$
$Var(\bar X) = \frac{\sigma^2}{n}$

$$
\bar{X}\sim N(\micro, \frac{\sigma}{\sqrt n}) \iff Z=\frac{\bar X -\micro}{\frac{\sigma}{\sqrt n}} \sim N(0,1)
$$

#### Sampling Distribution of Samples Difference Between Two Means $\bar{X_1}-\bar{X_2}$

$\bar X_1$ is the sample mean of population A
$\bar X_2$ is the sample mean of population B

$E(\bar{X_1}-\bar{X_2})= \micro_1 - \micro_2$
$Var(\bar{X_1}-\bar{X_2})= \frac{\sigma_1^2}{n_1}+\frac{\sigma_2^2}{n_2}$

$$
\bar{X_1}-\bar{X_2} \sim N( \micro_1 - \micro_2,  \sqrt{\frac{\sigma_1^2}{n_1}+\frac{\sigma_2^2}{n_2}})
\iff Z = \frac{(\bar{X_1}-\bar{X_2})-(\micro_1 - \micro_2)}{\sqrt{\frac{\sigma_1^2}{n_1}+\frac{\sigma_2^2}{n_2}}} \sim N(0,1)
$$



#### Sampling Distribution of a Sample Proportion $\hat{p}$

$\hat{p}= \frac{X}{n}$ is the proportion in the sample
- $X \sim b(n, p)$
- $E(\hat p) = p$
- $Var(\hat p) = \frac{pq}{n}$

$$
\hat{p} \sim N(p, \sqrt{\frac{pq}{n}}) \iff Z=\frac{\hat p -p}{\sqrt \frac{pq}{n}} \sim N(0,1)
$$


#### Sampling Distribution of Samples Difference Between Two Proportions $\hat{p_1}-\hat{p_2}$

$\hat{p_1}= \frac{X_1}{n_1}$ is the proportion in the sample of population A
$\hat{p_2}= \frac{X_2}{n_2}$ is the proportion in the sample of population B

- $E(\hat{p_1}-\hat{p_2}) = p_1-p_2$
- $Var(\hat{p_1}-\hat{p_2})= \frac{p_1q_1}{n_1} + \frac{p_2q_2}{n_2}$

$$
\hat{p_1}-\hat{p_2} \sim N(p_1-p_2, \sqrt{ \frac{p_1q_1}{n_1} + \frac{p_2q_2}{n_2} }) \iff Z = \frac{ (\hat{p_1}-\hat{p_2})-(p_1-p_2) }{\sqrt{\frac{p_1q_1}{n_1} + \frac{p_2q_2}{n_2}}} \sim N(0,1)
$$

---

#### Confidence Interval of the Mean $\micro$

$(1-\alpha)100\%$:

$$
\bar{X}\pm Z_{\frac{\alpha}{2}}\frac{\sigma}{\sqrt n}
\iff \bar{X} - Z_{\frac{\alpha}{2}}\frac{\sigma}{\sqrt n} < \micro < \bar{X} + Z_{\frac{\alpha}{2}}\frac{\sigma}{\sqrt n}
$$

#### Confidence Interval of $\micro_1-\micro_2$

Point estimation: $\bar{X_1}-\bar{X_2}$

$$
(\bar{X_1}-\bar{X_2})\pm Z_{\frac{\alpha}{2}} \sqrt{ \frac{\sigma_1^2}{n_1}+\frac{\sigma_2^2}{n_2} }
$$

#### Confidence Interval of the Proportion $\hat p$

Point estimation: $\hat{p} = \frac{X}{n}$
$(1-\alpha)100\%$:

$$
\hat{p} \pm Z_{\frac{\alpha}{2}} \sqrt{ \frac{\hat p\hat q}{n} }
$$

The outcome will be the interval of $p$.

#### Confidence Interval of $\hat{p_1}-\hat{p_2}$

Point estimation: $\hat{p_1}-\hat{p_2} = \frac{X_1}{n_1}-\frac{X_2}{n_2}$

$$
(\hat{p_1}-\hat{p_2}) \pm Z_{\frac{\alpha}{2}} \sqrt{ \frac{\hat p_1\hat q_1}{n_1} + \frac{\hat p_2\hat q_2}{n_2} }
$$
