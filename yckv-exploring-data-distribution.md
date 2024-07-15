# Exploring Data Distribution
#statistics #data #exploring #apply #plot

## Boxplots

- Could be use the Boxplots plots, it is the visual percentiles: [[3kb7-dispersion]]
- Percentiles are good to summarize data and see extreme values with 95th percentile, 99th percentile
- In the Boxplots, the last whisker does not go more than 1.5 IQR ([[3kb7-dispersion]]). The rest are outliers

## Frequency Table (Histogram)

- `value_counts()`
- Divided by bins
- Could be used histogram plots
- Large bins can hide features important for the models. Too small bin make hard to see the big pictures
- Bins have equal distance between them
- The bars are continuous

## Skewness and Kurtosis

- They are the third and fourth momentum of the data. [[r0sy-central-tendendcy]] with mean is the first momentum, and [[3kb7-dispersion]] with variance is the second momentum
- They are more see in the graph than a number to represent them.
- Kurtosis: Propensity to have extreme values
- Skewness: Has an extensively tail on the plot

## Density plots and Estimates

- Histograms are plots of densities and estimations with lines can be generated using **kernel density estimate**
- Y scale is different, but a proportion
- The area below the curve sum to 1
- You can calculate the area between two points to know the proportion

## Exploring Binary and Categorical

- Binary, proportion of 0 and 1
- Categorical, proportion of categorical variables
- You could use Bar charts, a little bit different from histograms where x-axis represents a category and y-axis is the
  count
- [[r0sy-central-tendendcy]]: Mode can be used to count the most common values
- Transform categorical variables into discretized ones
	- Expected Value: Discretized Values * Probability

## Exploring two or more Variables

- Scatter plots are good for small values
- Hexagonal binning for millions of rows
- Two categorical variables: Contingency Table
	- Divided category and proportion
- Categorical and numerical
	- Multiple Boxplots
	- Multiple Violin plots
		- Show the distribution as well

### References
- Bruce, 2017, p19-30
- Bruce, 2017, p36-45
