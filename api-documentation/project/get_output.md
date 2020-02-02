# get\_output

## Description

Gets an object from the outputs directory or a specified path.

```python
datasist.project.get_output(name=None, path=None, method='jb'):
    '''
    Parameter:
    ------------------
        name: String
            name of object to retrieve from the output folder. 
        path: String path, Default None
            Absolute path to the object
        method: String, Default 'jb'
            Object serialization format. Can either be jb (joblib) or csv.
    Returns:
    -------------------
        model or list of models objects
    '''
```

## Examples

### Get object saved with save\_outputs

```python
>>> import datasist as ds
#save a dictionary of mappings
>>> my_mapping = {"USA" : 10, "Canada": 20, "Germany": 30, "Nigeria": 70}
>>> ds.project.save_outputs(my_mapping, name='my_mapping')

#retrieve saved mapping
>>> retrieved_map = ds.project.get_output("my_mapping.jbl")
>>> retrived_map
{"USA" : 10, "Canada": 20, "Germany": 30, "Nigeria": 70}

```

### Get object from path

```python
>>> import datasist as ds
>>> retrieved_map = ds.project.get_output(path="output/mapping/my_mapping.jbl")
>>> retrived_map
{"USA" : 10, "Canada": 20, "Germany": 30, "Nigeria": 70}

```

To help us improve this documentation, visit the datasist-doc [repository](https://github.com/risenW/datasist-doc) 

