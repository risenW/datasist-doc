# cat\_summarizer

## Description

Helper function that gives a quick summary of a given column of categorical data

```python
cat_summarizer(data, x=None, y=None, hue=None, palette='Set1', verbose=True)
    '''
    Helper function that gives a quick summary of a given column of categorical data

    Parameters:
    ---------------------------
        dataframe: pandas dataframe

        x: str.
            horizontal axis to plot the labels of categorical data, y would be the count.

        y: str. 
            vertical axis to plot the labels of categorical data, x would be the count.

        hue: str. i
            if you want to compare it another variable (usually the target variable)

        palette: array, list.

            Colour of the plot

    Returns:
    ----------------------
        Quick Stats of the data and also the count plot
    '''    
   
```
## Examples

We are using the titanic data set and a Jupyter notebook in the following examples. 

```python
import pandas as pd
import datasist as ds

df = pd.read_csv('titanic.csv')
ds.structdata.cat_summarizer(df, x='Sex',  hue='Survived', palette='Set1', verbose=True)
```
![Image](https://i.imgur.com/zL1IeEj.png) !