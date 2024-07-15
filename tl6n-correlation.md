# Correlation
#statistics #math #theory

- Is it between -1 and 1
- Formula $r = \frac{\sum_{i=1}^{n} (x_i - \overline{x})(y_i - \overline{y})}{\sqrt{\left(\frac{\sum_{i=1}^{n} (x_i - \overline{x})^2}{n-1}\right) \left(\frac{\sum_{i=1}^{n} (y_i - \overline{y})^2}{n-1}\right)}}$
- The formula has the standard deviation ([[3kb7-dispersion]]) for `y` and `x` and the [[mj9x-degrees-of-freedom]] to make it **unbiased**
- On the correlation matrix, the diagonal == 1
- We can use `corrplot/heatmaps`
- Correlation is sensitive to **outliers**

> [!tip] Spearman/Kendalls
> They are based on ranks e are robust to outliers<br>
> In addition, they can deal with some non-linearity as well<br>
> It is suitable for small datasets

### References
- Bruce, 2017, p30-45
