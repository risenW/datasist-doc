# catbox

## Description

Makes a side by side bar plot of all categorical features against a categorical target feature.



```python
catbox(data=None, 
        cat_features=None, 
        target=None, 
        fig_size=(10,5), 
        save_fig=False):
   '''
    Parameters
    ------------
        data: DataFrame, array, or list of arrays.

            Dataset for plotting.

        cat_features: Scalar, array, or list. 

            The categorical features in the dataset, if None, 
            we try to infer the categorical columns from the dataframe.

        target: Scalar, array or list.

            Categorical target to plot against.

        fig_size: tuple, Default (12,6)

            The size of the figure object.

        save_fig: bool, Default False.

            If True, saves the plot to the current working directory.
 '''
```

## Examples

We are using the titanic data set and a Jupyter notebook in the following examples. 

catbox can be created for every categorical column in a DataFrame:

```python
import pandas as pd
import datasist.visualizations as vs

df = pd.read_csv('titanic.csv')
vs.catbox(data=df, target='survived')
```

![Image](https://i.imgur.com/2zUgHbv.png)
![Image](https://i.imgur.com/qttwIQt.png)
![Image](https://i.imgur.com/Hfjcvaf.png)

 catbox can be created for specified categorical column only:

```python
vs.catbox(data=df2, cat_features=['who'], target='survived', fig_size=(15,10))
```
![Image](https://i.imgur.com/VTMbscP.png)




