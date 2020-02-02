# get\_model

## Description

Gets the specified model from the outputs/model directory or the specified path. 

```python
def get_model(name=None, path=None, method='jb'):
    '''
    Gets the specified model from the outputs/models directory. Directory structure must have been created using the datasist start_project function.
    
    Parameter:
    ------------------
        name: String
            name of model to retrieve from the models folder. 
        path: String path, Default None
            Absolute path to the dataset
        method: String, Default 'jb'
            Data serialization format. Can be either jb (joblib) or csv.
    Returns:
    -------------------
        model or list of models objects
    '''
```

## Examples

### Get model saved with save\_model

```python
#save a trained model
>>> model = RandomForestClassier()
>>> model.fit(Xtrain, ytrain)
>>> ds.project.save_model(model, name='rf_model')

#retrieve saved model
>>> retrieved_model = ds.project.get_model("rf_model.jbl")
>>> retrived_model.predict(Xtest)

```

### Get a model from path

```python
#retrieve saved model from path
>>> retrieved_model = ds.project.get_model(path="model/rf_model.jbl")
>>> retrived_model.predict(Xtest)
```

To help us improve this documentation, visit the datasist-doc [repository](https://github.com/risenW/datasist-doc) 

