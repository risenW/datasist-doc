# bearing

### Description 
Calculates the Bearing between two points.
The bearing is the compass direction to travel from a starting point, and must be within the range 0 to 360. 

```python

Signature: ds.feature_engineering.bearing(lat1, long1, lat2, long2)
Docstring:
Calculates the Bearing  between two points.
The bearing is the compass direction to travel from a starting point, and must be within the range 0 to 360. 

Parameter:
-------------------------
    lat1: scalar,float

        Start point latitude of the location.

    lat2: scalar,float 

        End point latitude of the location.

    long1: scalar,float

        Start point longitude of the location.

    long2: scalar,float 

        End point longitude of the location.

Returns: Series

```


# Examples
```python
>>> import datasist as ds
>>> import numpy as np 
>>> import pandas as pd
df = pd.DataFrame(data =[[8.6753,9.0820,9.4281,6.4281],
                         [9.6753,8.0820,8.4281,7.4281],
                         [4.6753,3.0820,1.4281,3.4281]],
             columns = ['lat1','long1','lat2','long2'])
df

    lat1    long1   lat2    long2
0  8.6753  9.0820  9.4281  6.4281
1  9.6753  8.0820  8.4281  7.4281
2  4.6753  3.0820  1.4281  3.4281

>>> ds.feature_engineering.bearing(lat1=df.lat1,long1=df.long1,lat2=df.lat2,long2=df.long2)
0    -73.768105
1   -152.574291
2    173.914669
dtype: float64
