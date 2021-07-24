# plot\_scatter\_shape

## Description

Makes a scatter plot of data using shape\_col as seperation.

```python
plot_scatter_shape(data=None, 
                    cols=None, 
                    shape_col='', 
                    col_y='', 
                    alpha=0.2):
   '''
    Parameters
    ------------
        data: Dataframe 
            The data that is being imported using pandas.

        cols: list 
            The chosen number of columns in the DataFrame.

        shape_col: 
            The categorical column you want it to show as legend.

        col_y: The y axis of the plot
 '''
```

## Examples

We are using the classic iris data set and a Jupyter notebook in the following examples.

plot\_scatter\_shape can be created for every column in a DataFrame:

```python
import pandas as pd
import datasist.visualizations as vs

df = pd.read_csv('iris.csv')
vs.plot_scatter_shape(data = df, cols = ['sepal_length','sepal_width','petal_length','petal_width'], shape_col = 'species', col_y = 'sepal_length', alpha = 0.2)
```

![Image](https://i.imgur.com/mv3VEyV.png) ![Image](https://i.imgur.com/S9SGneY.png) ![Image](https://i.imgur.com/LHW4CRU.png) ![Image](https://i.imgur.com/7i9Iogf.png)

plot\_scatter\_shape can be created for specified columns only:

```python
vs.plot_scatter_shape(data = df, cols = ['sepal_width'], shape_col = 'species', col_y = 'sepal_length')
```

![Image](https://i.imgur.com/sQyaJMx.png)

