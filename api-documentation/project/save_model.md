# save\_model

## Description

Saves a trained machine learning model in the models folder. Folders must be initialized using the datasist start\_project function. Creates a folder _models_ if datasist's standard directory is not available.

```python
def save_model(model, name='model', method='joblib')
'''
    Parameters:
    --------------------
    model: binary file, Python object
        Trained model file to save in the models folder.
        
    name: string
        Name of the model to save it with.
    
    method: string
        Format to use in saving the model. It can be one of [joblib, pickle or keras].
    
    Returns:
        None  
''' 
```

## Examples

### Save Scikit-learn model

```python
>>> model = RandomForestClassifier(n_estimators=10)
>>> model.fit(Xtrain, Xtest)
>>> ds.project.save_model(model, name='rf_model')
```

### Save Keras model

```python
>>> model.fit(Xtrain, Xtest)
>>> ds.project.save_model(model, name='keras_model', method='keras')
```

To help us improve this documentation, visit the datasist-doc [repository](https://github.com/risenW/datasist-doc) 

