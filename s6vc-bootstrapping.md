# Bootstrap
#statistic #method #sampling #math #efficient #noassumption

- Used to calculate the [[h92w-sampling-distribution]]

## Steps
1. Draw a sample value, record it, and then replace it
2. Repeat *n* times
3. Record the man of the n resampled values
4. Repeat steps 1-3 R times
5. Use the R results to:
	1. Calculate their standard deviation (this estimates sample mean standard error)
	2. Produce a histogram or boxplot
	3. Find a confidence interval


- R is the number of the iterations
- It does not need to assume anything about the distribution, neither normality
- The more iterations it does, better is the confidence interval
- Can be named as `resampled` as well
	- Include **permutation** as well
	- It does **without replacement**, while bootstrap is **with replacement**

- Bagging: Bootstrap Aggregation

### References
Bruce, 2017, p61-65
