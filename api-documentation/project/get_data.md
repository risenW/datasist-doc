# get\_data

## Description

Gets data from the data directory or a specified path. 

```python
get_data(name=None, path=None, loc='processed', method='jb'):
    '''
    Gets the specified data from the data directory. Directory structure must have been created using the datasist start_project function.
    
    Parameter:
    ------------------
        name: String, List
            name or list of dataset to retrieve from the data folder. 
        path: String path, Default None
            Absolute path to the dataset
        loc: String, Default "processed"
            One of [processed, raw]. Location of the dataset in the data folder. Defaults to the 'processed'.
        method: String, Default 'jb'
            Data serialization format. Can be either jb (joblib) or csv.
    Returns:
    -------------------
        data or list of data objects
    '''
```

## Examples

### Get data saved with save\_data

```python
>>> import datasist as ds
#save a dataset
>>> df = pd.DataFrame({"age": range(5), "amount": range(5, 10)})
>>> df
age  amount
0    0    5
1    1    6
2    2    7
3    3    8
4    4    9
>>> ds.project.save_data(df, name='my_df', method='csv')

#retrieve saved data
>>> retrieved_df = ds.project.get_data("my_df.csv")
>>> retrived_df
age  amount
0    0    5
1    1    6
2    2    7
3    3    8
4    4    9

```

### Get a data from path

```python
>>> import datasist as ds
#retrieve saved model from path
>>> new_df = ds.project.get_data(path="data/df.csv")
>>> new_df
age  amount
0    0    5
1    1    6
2    2    7
3    3    8
4    4    9
```

To help us improve this documentation, visit the datasist-doc [repository](https://github.com/risenW/datasist-doc) 

