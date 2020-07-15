# bin\_age

## bin\_age

### Description

Categorize continous data into separate bins. this is a way of turning continous feature into categorical feature.

```python
Signature:
ds.feature_engineering.bin_age(data,
                                feature,
                                bins,
                                labels,
                                fill_missing=None,
                                drop_original=False,
                                )
Docstring:
Categorize age data into separate bins

Parameter:
-----------------------------------------
data: DataFrame, Series.

    Data for which feature to be binned exist.

feature: List, Series

    Columns to be binned

Bins: List, numpy.ndarray

    Specifies the different categories. Bins must be one greater labels.

labels: List, Series

    Name identified to the various categories

fill_missing(default = None): int

    mean : feature average.
    mode : most occuring data in the feature.
    median : middle point in the feature.

drop_original: bool

    Drops original feature after beaning.

Returns:
    Returns a binned dataframe.
```

## Examples

```python
>>> import datasist as ds
>>> import pandas as pd
df = pd.DataFrame(data =[list(np.random.randint(5,30,4)),
                         list(np.random.randint(7,30,4)),
                         list(np.random.randint(5,30,4)),
                         list(np.random.randint(5,30,4)),
                         list(np.random.randint(5,30,4)),
                         list(np.random.randint(5,30,4))],
             columns = ['A','B','C','D'])
>>> df

       A    B    C    D
0    27    7    8    17
1    27    25    29    21
2    17    19    24    19
3    28    8    21    12
4    10    25    21    15
5    15    12    19    9


>>> ds.feature_engineering.bin_age(df,['A'],3,['A1','A2','A3'])
    A    B    C    D    A_binned
0    27    7    8    17    A3
1    27    25    29    21    A3
2    17    19    24    19    A2
3    28    8    21    12    A3
4    10    25    21    15    A1
5    15    12    19    9    A1
```

### Setting drop\_original: bool to True

```python
>>> ds.feature_engineering.bin_age(df,['A'],3,['A1','A2','A3'],drop_original = True)
B    C    D    A_binned
0    7    8    17    A3
1    25    29    21    A3
2    19    24    19    A2
3    8    21    12    A3
4    25    21    15    A1
5    12    19    9    A1
```

