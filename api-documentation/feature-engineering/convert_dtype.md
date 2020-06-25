# convert\_dtype

### Description 
Converts datatype of a feature to its original datatype.
If the datatype of a feature is being represented as a string while the initial datatype
is an integer or a float
or even a datetime dtype. The convert_dtype() function iterates over the feature(s) in a
pandas dataframe and convert the features to their appropriate datatype

```python

Signature: ds.feature_engineering.convert_dtype(df)


Parameter:
---------------------------
df: DataFrame, Series

    Dataset to convert data type

Returns:
-----------------
    DataFrame or Series.
```
# Example: 
```python
df = pd.DataFrame({'Name':['Tom', 'nick', 'jack'], 
        'Age':['20', '21', '19'],
        'Date of Birth': ['1999-11-17','20 Sept 1998','Wed Sep 19 14:55:02 2000']})
df
>>> 
	Name	Age	Date of Birth
0	Tom	    20	1999-11-17
1	nick	21	20 Sept 1998
2	jack	19	Wed Sep 19 14:55:02 2000

df.info()
>>> 
<class 'pandas.core.frame.DataFrame'>
    RangeIndex: 3 entries, 0 to 2
    Data columns (total 3 columns):
    Name             3 non-null object
    Age              3 non-null object
    Date of Birth    3 non-null object
    dtypes: object(3)
    memory usage: 76.0+ bytes

conv = convert_dtype(df)
conv.info()
>>> 
<class 'pandas.core.frame.DataFrame'>
    RangeIndex: 3 entries, 0 to 2
    Data columns (total 3 columns):
    Name             3 non-null object
    Age              3 non-null int32
    Date of Birth    3 non-null datetime64[ns]
    dtypes: datetime64[ns](1), int32(1), object(1)
    memory usage: 88.0+ bytes

Type:      function
