# Keeping it simple with loops
Below is a for loop I used during project 1 to read in 'subjects', a list of 21 data files from an experiment. I created an empty list 'df_list', and appended each data frame to it. This then allowed me to use `pd.concat` to concatenate all of the dataframes in df_list into a single dataframe called 'df_error'.


```python
# Write loop to read in each file in subjects
df_list = []
for file in subjects:
    in_file = file +'/'+file+'_data.txt'
    df = pd.read_csv(in_file, sep='\t')
    df_list.append(df)

# Error dataframe: concat df_list into 1 dataframe (error)
df_error = pd.concat(df_list)
```
