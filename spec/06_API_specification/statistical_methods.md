# Statistical Methods

> Dataframe API specification for statistical methods.

A conforming implementation of the dataframe API standard must provide and support the following methods adhering to the following conventions.

-   Positional parameters must be [positional-only](https://www.python.org/dev/peps/pep-0570/) parameters. Positional-only parameters have no externally-usable name. When a method accepting positional-only parameters is called, positional arguments are mapped to these parameters based solely on their order.
-   Optional parameters must be [keyword-only](https://www.python.org/dev/peps/pep-3102/) arguments.

## Methods

<!-- NOTE: please keep the methods in alphabetical order -->

(method-cummax)=
### cummax(x, /, *, skipna=True)

Calculates the cumulative maximum value.

#### Parameters

-   **x**: _&lt;dataframe&gt;_

    -   dataframe instance.

-   **skipna**: _Optional\[ bool ]_

    -   Exclude `NA` and `null` values. If an entire column is `NA`, the result must be `NA`. Default: `True`.

#### Returns

-   **out**: _&lt;dataframe&gt;_

    -   dataframe containing cumulative maximum values. The returned dataframe must have the same size as `x`.

(method-cummin)=
### cummin(x, /, *, skipna=True)

Calculates the cumulative minimum value.

#### Parameters

-   **x**: _&lt;dataframe&gt;_

    -   dataframe instance.

-   **skipna**: _Optional\[ bool ]_

    -   Exclude `NA` and `null` values. If an entire column is `NA`, the result must be `NA`. Default: `True`.

#### Returns

-   **out**: _&lt;dataframe&gt;_

    -   dataframe containing cumulative minimum values. The returned dataframe must have the same size as `x`.

(method-cumsum)=
### cummax(x, /, *, skipna=True)

Calculates the cumulative sum.

#### Parameters

-   **x**: _&lt;dataframe&gt;_

    -   dataframe instance.

-   **skipna**: _Optional\[ bool ]_

    -   Exclude `NA` and `null` values. If an entire column is `NA`, the result must be `NA`. Default: `True`.

#### Returns

-   **out**: _&lt;dataframe&gt;_

    -   dataframe containing cumulative sums. The returned dataframe must have the same size as `x`.

(method-cumprod)=
### cumprod(x, /, *, skipna=True)

Calculates the cumulative product.

#### Parameters

-   **x**: _&lt;dataframe&gt;_

    -   dataframe instance.

-   **skipna**: _Optional\[ bool ]_

    -   Exclude `NA` and `null` values. If an entire column is `NA`, the result must be `NA`. Default: `True`.

#### Returns

-   **out**: _&lt;dataframe&gt;_

    -   dataframe containing cumulative products. The returned dataframe must have the same size as `x`.

(method-max)=
### max(x, /, *, axis=None)

Calculates the maximum value.

#### Parameters

-   **x**: _&lt;dataframe&gt;_

    -   dataframe instance.

-   **axis**: _Optional\[ int ]_

    -   axis along which maximum values must be computed. If equal to `0`, the maximum values must be computed over the index. If equal to `1`, the maximum values must be computed over the columns. By default, maximum values must be computed over the index. Default: `None`.

#### Returns

-   **out**: _&lt;dataframe&gt;_

    -   dataframe containing the maximum values.

(method-mean)=
### mean(x, /, *, axis=None)

Calculates the arithmetic mean.

#### Parameters

-   **x**: _&lt;dataframe&gt;_

    -   dataframe instance.

-   **axis**: _Optional\[ int ]_

    -   axis along which arithmetic means must be computed. If equal to `0`, arithmetic means must be computed over the index. If equal to `1`, arithmetic means must be computed over the columns. By default, arithmetic means must be computed over the index. Default: `None`.

#### Returns

-   **out**: _&lt;dataframe&gt;_

    -   dataframe containing the arithmetic means.

(method-min)=
### min(x, /, *, axis=None)

Calculates the minimum value.

#### Parameters

-   **x**: _&lt;dataframe&gt;_

    -   dataframe instance.

-   **axis**: _Optional\[ int ]_

    -   axis along which minimum values must be computed. If equal to `0`, the minimum values must be computed over the index. If equal to `1`, the minimum values must be computed over the columns. By default, minimum values must be computed over the index. Default: `None`.

#### Returns

-   **out**: _&lt;dataframe&gt;_

    -   dataframe containing the minimum values.

(method-nlargest)=
### nlargest(x, n, columns, /)

Returns the first `n` rows having the largest values in `columns` and sorted in descending order.

#### Parameters

-   **x**: _&lt;dataframe&gt;_

    -   dataframe instance.

-   **n**: _int_

    -   Number of rows.

-   **columns**: _Any_

    -   Column label(s) to order by. If provided a list of column labels, the first list element (label) determines the first `n` rows, the second label orders the `n` rows, the third label orders ties for the first two labels, and so on and so forth. In other words, ordering by label is applied sequentially.

#### Returns

-   **out**: _&lt;dataframe&gt;_

    -   dataframe containing the first `n` rows.

(method-nsmallest)=
### nsmallest(x, n, columns, /)

Returns the first `n` rows having the smallest values in `columns` and sorted in ascending order.

#### Parameters

-   **x**: _&lt;dataframe&gt;_

    -   dataframe instance.

-   **n**: _int_

    -   Number of rows.

-   **columns**: _Any_

    -   Column label(s) to order by. If provided a list of column labels, the first list element (label) determines the first `n` rows, the second label orders the `n` rows, the third label orders ties for the first two labels, and so on and so forth. In other words, ordering by label is applied sequentially.

#### Returns

-   **out**: _&lt;dataframe&gt;_

    -   dataframe containing the first `n` rows.

(method-prod)=
### prod(x, /, *, axis=None)

Calculates the product.

#### Parameters

-   **x**: _&lt;dataframe&gt;_

    -   dataframe instance.

-   **axis**: _Optional\[ int ]_

    -   axis along which products must be computed. If equal to `0`, the products must be computed over the index. If equal to `1`, the products must be computed over the columns. By default, products must be computed over the index. Default: `None`.

#### Returns

-   **out**: _&lt;dataframe&gt;_

    -   dataframe containing the products.

(method-std)=
### std(x, /, *, axis=None, correction=1.0)

Calculates the standard deviation.

#### Parameters

-   **x**: _&lt;dataframe&gt;_

    -   dataframe instance.

-   **axis**: _Optional\[ int ]_

    -   axis along which standard deviations must be computed. If equal to `0`, standard deviations must be computed over the index. If equal to `1`, standard deviations must be computed over the columns. By default, standard deviations must be computed over the index. Default: `None`.

-   **correction**: _Union\[ int, float ]_

    -   degrees of freedom adjustment. Setting this parameter to a value other than `0` has the effect of adjusting the divisor during the calculation of the standard deviation according to `N-c` where `N` corresponds to the total number of elements over which the standard deviation is computed and `c` corresponds to the provided degrees of freedom adjustment. When computing the standard deviation of a population, setting this parameter to `0` is the standard choice (i.e., the provided array contains data constituting an entire population). When computing the corrected sample standard deviation, setting this parameter to `1` is the standard choice (i.e., the provided array contains data sampled from a larger population; this is commonly referred to as Bessel's correction). Default: `1.0`.

#### Returns

-   **out**: _&lt;dataframe&gt;_

    -   dataframe containing the standard deviations.

(method-sum)=
### sum(x, /, *, axis=None)

Calculates the sum.

#### Parameters

-   **x**: _&lt;dataframe&gt;_

    -   dataframe instance.

-   **axis**: _Optional\[ int ]_

    -   axis along which sums must be computed. If equal to `0`, the sums must be computed over the index. If equal to `1`, the sums must be computed over the columns. By default, sums must be computed over the index. Default: `None`.

#### Returns

-   **out**: _&lt;dataframe&gt;_

    -   dataframe containing the sums.

(method-var)=
### var(x, /, *, axis=None, correction=1.0)

Calculates the variance.

#### Parameters

-   **x**: _&lt;dataframe&gt;_

    -   dataframe instance.

-   **axis**: _Optional\[ int ]_

    -   axis along which variances must be computed. If equal to `0`, variances must be computed over the index. If equal to `1`, variances must be computed over the columns. By default, variances must be computed over the index. Default: `None`.

-   **correction**: _Union\[ int, float ]_

    -   degrees of freedom adjustment. Setting this parameter to a value other than `0` has the effect of adjusting the divisor during the calculation of the variance according to `N-c` where `N` corresponds to the total number of elements over which the variance is computed and `c` corresponds to the provided degrees of freedom adjustment. When computing the variance of a population, setting this parameter to `0` is the standard choice (i.e., the provided array contains data constituting an entire population). When computing the unbiased sample variance, setting this parameter to `1` is the standard choice (i.e., the provided array contains data sampled from a larger population; this is commonly referred to as Bessel's correction). Default: `1.0`.

#### Returns

-   **out**: _&lt;dataframe&gt;_

    -   dataframe containing the variances.