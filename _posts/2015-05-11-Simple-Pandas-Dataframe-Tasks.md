

```python
import pandas as pd

#initialize a list
data = [['Pritam',10,100,'a'],['Madhu',20,200,'b'],['Rio',5,50,'c'],['Ron',4,40,'d'],['Piyali',7,70,'e'],['Arunabha',11,110,'f']]
```


```python
print(data)
```

    [['Pritam', 10, 100, 'a'], ['Madhu', 20, 200, 'b'], ['Rio', 5, 50, 'c'], ['Ron', 4, 40, 'd'], ['Piyali', 7, 70, 'e'], ['Arunabha', 11, 110, 'f']]
    


```python
type(data)
```




    list




```python
#create dataframe from a list
df = pd.DataFrame(data,columns=['Name','value1','value2','type'])
print(df)
```

           Name  value1  value2 type
    0    Pritam      10     100    a
    1     Madhu      20     200    b
    2       Rio       5      50    c
    3       Ron       4      40    d
    4    Piyali       7      70    e
    5  Arunabha      11     110    f
    


```python
print(df.dtypes)
```

    Name      object
    value1     int64
    value2     int64
    type      object
    dtype: object
    


```python
print(df['value1'])  #access a column and just print it
```

    0    10
    1    20
    2     5
    3     4
    4     7
    5    11
    Name: value1, dtype: int64
    


```python
print(list(df['type']))  #access a column and print is as a list
```

    ['a', 'b', 'c', 'd', 'e', 'f']
    


```python
df['new'] = [1,2,3,4,5,6] #add a new column
df
```




<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Name</th>
      <th>value1</th>
      <th>value2</th>
      <th>type</th>
      <th>new</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Pritam</td>
      <td>10</td>
      <td>100</td>
      <td>a</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Madhu</td>
      <td>20</td>
      <td>200</td>
      <td>b</td>
      <td>2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Rio</td>
      <td>5</td>
      <td>50</td>
      <td>c</td>
      <td>3</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Ron</td>
      <td>4</td>
      <td>40</td>
      <td>d</td>
      <td>4</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Piyali</td>
      <td>7</td>
      <td>70</td>
      <td>e</td>
      <td>5</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Arunabha</td>
      <td>11</td>
      <td>110</td>
      <td>f</td>
      <td>6</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.pop('new') #delete a column by its name 
df
```




<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Name</th>
      <th>value1</th>
      <th>value2</th>
      <th>type</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Pritam</td>
      <td>10</td>
      <td>100</td>
      <td>a</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Madhu</td>
      <td>20</td>
      <td>200</td>
      <td>b</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Rio</td>
      <td>5</td>
      <td>50</td>
      <td>c</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Ron</td>
      <td>4</td>
      <td>40</td>
      <td>d</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Piyali</td>
      <td>7</td>
      <td>70</td>
      <td>e</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Arunabha</td>
      <td>11</td>
      <td>110</td>
      <td>f</td>
    </tr>
  </tbody>
</table>
</div>




```python
list(df.loc[4]) #select a row by using 'loc'
```




    ['Piyali', 7, 70, 'e']




```python
list(df.iloc[2]) #select a row by using 'iloc'
```




    ['Rio', 5, 50, 'c']




```python
df.loc[1:4] #subset some rows using 'loc'
```




<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Name</th>
      <th>value1</th>
      <th>value2</th>
      <th>type</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>Madhu</td>
      <td>20</td>
      <td>200</td>
      <td>b</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Rio</td>
      <td>5</td>
      <td>50</td>
      <td>c</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Ron</td>
      <td>4</td>
      <td>40</td>
      <td>d</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Piyali</td>
      <td>7</td>
      <td>70</td>
      <td>e</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.iloc[1:4] #subset some rows using iloc, note the difference
```




<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Name</th>
      <th>value1</th>
      <th>value2</th>
      <th>type</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>Madhu</td>
      <td>20</td>
      <td>200</td>
      <td>b</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Rio</td>
      <td>5</td>
      <td>50</td>
      <td>c</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Ron</td>
      <td>4</td>
      <td>40</td>
      <td>d</td>
    </tr>
  </tbody>
</table>
</div>




```python
# add row to the data frame. Create a temporary data frame with exactly the same column names and data types.
df_temp = pd.DataFrame([['Hello',1,2,'x']],columns=['Name','value1','value2','type'])
df_temp
```




<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Name</th>
      <th>value1</th>
      <th>value2</th>
      <th>type</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Hello</td>
      <td>1</td>
      <td>2</td>
      <td>x</td>
    </tr>
  </tbody>
</table>
</div>




```python
# add row to the data frame. Create a temporary data frame with exactly the same column names and data types. 
# this time use a specific index to act as the row index or row label
df_temp_with_index = pd.DataFrame([['Hello',1,2,'x']],columns=['Name','value1','value2','type'],index=[6])
df_temp_with_index
```




<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Name</th>
      <th>value1</th>
      <th>value2</th>
      <th>type</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>6</th>
      <td>Hello</td>
      <td>1</td>
      <td>2</td>
      <td>x</td>
    </tr>
  </tbody>
</table>
</div>




```python
df_org = df.copy() # save the df by copying it.
df_1 = df.append(df_temp) # then append
df_2 = df.append(df_temp_with_index)
```


```python
print(df_org,'\n')
print(df_1,'\n') # note row got added with index = 0 , so multiple rows with same index 0
print(df_2) # note tow got added with new index = 6
```

           Name  value1  value2 type
    0    Pritam      10     100    a
    1     Madhu      20     200    b
    2       Rio       5      50    c
    3       Ron       4      40    d
    4    Piyali       7      70    e
    5  Arunabha      11     110    f 
    
           Name  value1  value2 type
    0    Pritam      10     100    a
    1     Madhu      20     200    b
    2       Rio       5      50    c
    3       Ron       4      40    d
    4    Piyali       7      70    e
    5  Arunabha      11     110    f
    0     Hello       1       2    x 
    
           Name  value1  value2 type
    0    Pritam      10     100    a
    1     Madhu      20     200    b
    2       Rio       5      50    c
    3       Ron       4      40    d
    4    Piyali       7      70    e
    5  Arunabha      11     110    f
    6     Hello       1       2    x
    


```python
print(df_1.drop(0))  # will drop 2 rows having same index = 0
```

           Name  value1  value2 type
    1     Madhu      20     200    b
    2       Rio       5      50    c
    3       Ron       4      40    d
    4    Piyali       7      70    e
    5  Arunabha      11     110    f
    


```python
print(df_2.drop(0)) # will drop only a single row with index = 0
```

           Name  value1  value2 type
    1     Madhu      20     200    b
    2       Rio       5      50    c
    3       Ron       4      40    d
    4    Piyali       7      70    e
    5  Arunabha      11     110    f
    6     Hello       1       2    x
    


```python
# now lets get back to the original data frame
df = df_org.copy()

# add a couple of rows 
df_temp = pd.DataFrame(data=[['Pritam',11,110,'a',],['Madhu',21,210,'b']],columns=['Name','value1','value2','type'],index=[6,7])
df = df.append(df_temp)
print('unsorted\n',df)
df_sorted = df.sort_values(by=['Name','value2'],ascending=[True,False])
print('\nsorted\n',df_sorted)
```

    unsorted
            Name  value1  value2 type
    0    Pritam      10     100    a
    1     Madhu      20     200    b
    2       Rio       5      50    c
    3       Ron       4      40    d
    4    Piyali       7      70    e
    5  Arunabha      11     110    f
    6    Pritam      11     110    a
    7     Madhu      21     210    b
    
    sorted
            Name  value1  value2 type
    5  Arunabha      11     110    f
    7     Madhu      21     210    b
    1     Madhu      20     200    b
    4    Piyali       7      70    e
    6    Pritam      11     110    a
    0    Pritam      10     100    a
    2       Rio       5      50    c
    3       Ron       4      40    d
    


```python

```
