## Probability and Statistics

26 Dec 2022

---

#### Chapter 1

**Population**: Some unknown parameters `population size: N`
**Sample**: Observations after calculating some statistics `sample size: n`

Let `X1,X2,...,XN` be the population values (which are unknown); while `x1,x2,...,xn` be the sample values (which are known).

Calculated statistics obtained from the sample are used to estimate (approximate) the parameters of the population.

**Measures of Location** (Central Tendency)
The data (observations or samples) often tend to be concentrated around the center of the data.

Some measures of location:
- Mean
- Mode
- Median

These measures are considered as the *representatives* of the data.
They are designed to give some *quantitative* measures of where the center of the data is in the sample.

**Sample Mean**:
If `x1,x2,..,xn` are the sample values, then the sample *mean* is

![[Introduction to Statistics-1672031398658.jpeg|350]]

<span style='color:pink'>Example</span>

```txt
Suppose that the following sample
represents the ages (in year) of a sample of 3 men:
x1 = 30, x2 = 35, x3 = 27

Then, the sample mean is:
X' = (30+35+27)/3 = 30.67 (years)
```

<span style='color:lightgreen'>Note</span>

![[Introduction to Statistics-1672032312997.jpeg|350]]

```
Verifing the above expression
(30-30.67) + (35-30.67) + (27-30.67)
(-0.67) + (4.33) + (-3.67) = 0
```

---

**Measures of Variability**

*Dispresion* or *Variation* in a set of data refers to how spread out the observations/samples are from each other.

*Variation* is small when the observations are close together
No *variation* IF the observations are the same

Some measures of dispresion:
- Range
- Variance
- Standard Deviation

These measures are designed to give some *quantitative* measures of the variability in the data.

**The Sample Variance (S^2)**

```
Let x1,x2,...,xn be the observation of the sample.
The sample variance is defined by:
```

![[Introduction to Statistics-1672039257857.jpeg|500]]

![[Introduction to Statistics-1672039307813.jpeg|500]]

<span style='color:lightgreen'>Note</span>

`n-1` is called the **degrees of freedom** (df) associated with the sample variance (S^2).

---

**The Standard Deviation (S)**

Is is the square root of the sample variance.

![[Introduction to Statistics-1672039547814.jpeg|375]]

<span style='color:pink'>Example</span>

```
Compute the sample variance and the
standard variance of the following 
observations (ages in year): 10, 21, 33, 53, 54
```

<span style='color:lightgreen'>Note</span>

Another formula for calculating S^2 (*Sample Variance*)

![[Introduction to Statistics-1672040241470.jpeg|400]]

So to calculate it, we need:
- n = sample size
- The sum of the values (to calculate the *mean*)
- The sum of the squared values

