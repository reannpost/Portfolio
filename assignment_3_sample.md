# Extracting Relevant Information
The following code uses the pandas groupby method to extract only the relevant information from a large dataset. This is very useful when analyzing data concerning just a specific part of a study.


```python
#import pandas package
import pandas as pd

#read in data
subjects = 'spid10_2014_06_17_17_44'
in_file = subjects + '/' + subjects + '_data.txt'
df = pd.read_csv(in_file, sep='\t')
```


```python
#group data by 'flankers' column
df.groupby('flankers').count()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>id</th>
      <th>year</th>
      <th>month</th>
      <th>day</th>
      <th>hour</th>
      <th>minute</th>
      <th>mapping</th>
      <th>messageViewingTime</th>
      <th>block</th>
      <th>trialNum</th>
      <th>targetLocation</th>
      <th>target</th>
      <th>rt</th>
      <th>response</th>
      <th>error</th>
      <th>anticipation</th>
      <th>feedbackResponse</th>
      <th>targetOnError</th>
    </tr>
    <tr>
      <th>flankers</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>congruent</th>
      <td>432</td>
      <td>432</td>
      <td>432</td>
      <td>432</td>
      <td>432</td>
      <td>432</td>
      <td>432</td>
      <td>432</td>
      <td>432</td>
      <td>432</td>
      <td>432</td>
      <td>432</td>
      <td>432</td>
      <td>432</td>
      <td>432</td>
      <td>432</td>
      <td>432</td>
      <td>432</td>
    </tr>
    <tr>
      <th>incongruent</th>
      <td>432</td>
      <td>432</td>
      <td>432</td>
      <td>432</td>
      <td>432</td>
      <td>432</td>
      <td>432</td>
      <td>432</td>
      <td>432</td>
      <td>432</td>
      <td>432</td>
      <td>432</td>
      <td>429</td>
      <td>429</td>
      <td>429</td>
      <td>432</td>
      <td>432</td>
      <td>432</td>
    </tr>
  </tbody>
</table>
</div>




```python
#this is still more information than I need, so I can use groupby again to isolate a smaller chunk of the dataset
df.groupby('flankers')[['rt', 'error']].count()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>rt</th>
      <th>error</th>
    </tr>
    <tr>
      <th>flankers</th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>congruent</th>
      <td>432</td>
      <td>432</td>
    </tr>
    <tr>
      <th>incongruent</th>
      <td>429</td>
      <td>429</td>
    </tr>
  </tbody>
</table>
</div>




```python

```
