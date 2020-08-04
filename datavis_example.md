# Data Visualization
Below is a boxplot showing the distribution of reaction times for a dataset, grouped by the 'flankers' column.


```python
#import necessary packages
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

#read in data
subjects = 'spid10_2014_06_17_17_44'
in_file = subjects + '/' + subjects + '_data.txt'
df = pd.read_csv(in_file, sep='\t')
```


```python
df.boxplot(column='rt', by='flankers')
```

    /usr/local/lib/python3.6/dist-packages/numpy/core/_asarray.py:83: VisibleDeprecationWarning: Creating an ndarray from ragged nested sequences (which is a list-or-tuple of lists-or-tuples-or ndarrays with different lengths or shapes) is deprecated. If you meant to do this, you must specify 'dtype=object' when creating the ndarray
      return array(a, dtype, copy=False, order=order)





    <matplotlib.axes._subplots.AxesSubplot at 0x7fab86c8e208>






![png](Datavis_example_files/Datavis_example_2_2.png)



The above code places both boxplots on the same axes, however it is alternatively possible to plot them on seperate subplots, as seen below:


```python
fig, ax = plt.subplots(1,2)
df['rt'].where((df['flankers']=='congruent')).plot(kind='box', ax=ax[0])
df['rt'].where((df['flankers']=='incongruent')).plot(kind='box', ax=ax[1])
```




    <matplotlib.axes._subplots.AxesSubplot at 0x7fab89709b70>






![png](Datavis_example_files/Datavis_example_4_1.png)



Both are vaild options; I have learned that the visualization you choose will change depending on the dataset, and what information you are trying to highlight.


