# fill\_missing\_cats

## Description

Fill missing values using the mode of the categorical features.


```python
fill_missing_cats(data=None, cat_features=None, missing_encoding=None, missing_col=False)

    '''  
    Parameters:
    ------------------
        data: DataFrame or name Series.

          Data set to perform operation on.

        cat_features: List, Series, Array.

            categorical features to perform operation on. If not provided, we automatically infer the categoricals from the dataset.

        missing_encoding: List, Series, Array.

            Values used in place of missing. Popular formats are [-1, -999, -99, '', ' ']

        missin_col: bool, Default True
        
            Creates a new column to capture the missing values. 1 if missing and 0 otherwise. This can sometimes help a machine learning model
    '''
```

## Examples

For the **save\_data** to work properly, a data science directory must have been created with the datasist **startproject** function.

```python

```




