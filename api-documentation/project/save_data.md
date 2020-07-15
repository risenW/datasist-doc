# save\_data

## Description

Saves data in the data folder. The data folder contains the processed and raw sub folders. 

The processed sub folder holds data that have been processed by some methods and can be used for later computation. Files like feature matrices, clean data files etc. 

The raw sub folder contains data in the raw format. This can be in the form of SQL tables, CSV files raw texts etc. Folders must be initialized using the datasist start\_project function.



```python
save_data(data, name='processed_data', method='joblib', loc='processed')
    '''  
    Parameters:
    ------------------
    data: binary strings, CSV, txt
        Data to save in the specified folder
    
    name: string, Default proc_data
        Name of the data file to save.
    
    method: string, Default None
    
        Format to use in saving the data. It can be empty string, and we assume it is a
        Pandas DataFrame, and we use the to_csv function, else we serialize with joblib.
    
    loc: string, Default processed.
        subfolder to save the data file to. Can be one of [processed, raw ]
    
    Returns:
    
        None
    '''
```

## Examples

For the **save\_data** to work properly, a data science directory must have been created with the datasist **startproject** function.

```python
>>> import datasist as ds
>>> df = pd.DataFrame({"size": range(5), "amount": range(5, 10)})
>>> df
   size  amount
0    0    5
1    1    6
2    2    7
3    3    8
4    4    9
>>> ds.project.save_data(data=df, name='my_df', method='csv')

```

To help us improve this documentation, visit the datasist-doc [repository](https://github.com/risenW/datasist-doc) 

