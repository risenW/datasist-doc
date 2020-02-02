# save\_outputs

## Description

Saves files like vocabulary, class labels, mappings, encoding, images etc. in the outputs folder.

```python
datasist.project.save_outputs(data=None, name='proc_outputs', method='joblib')
    '''
    Parameters:
    -----------------
    data: binary strings, CSV, txt
        Data to save in the folder
    
    name: string, Default proc_outputs
        Name of the data file to save.
    
    method: string, Default joblib
        Format to use in saving the data. It can be one of [csv, joblib, pickle].
    
    Returns:
        None
    '''
```

## Examples

For the **save\_outputs** to work properly, a data science directory must have been created with the datasist **startproject** function.

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
>>> ds.project.save_outputs(data=df, name='my_df', method='csv')

```

```python
>>> import datasist as ds
>>> enc = joblib.dumps("my_encodings")
>>> ds.project.save_outputs(data=enc, name='my_enc', method='joblib')

```

To help us improve this documentation, visit the datasist-doc [repository](https://github.com/risenW/datasist-doc) 

