---
title: Python - Pandas notes
date: '2025-01-16'
slug: python-pandas-notes
categories:
  - Dev
tags:
  - pandas
  - python
draft: false
summary: " "
---

### Count the consecutive positive elements in an array
E.g., Count the consecutive positive change in an array of price changes


```python
import pandas as pd
```


```python
df = pd.DataFrame.from_dict({
    "price_change": [-0.1, 0.2, 0.3, -0.1, -0.2, 0.4, 0.5, 0.6, -0.9]
})
```


```python
df
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
      <th>price_change</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>-0.1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>0.2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>0.3</td>
    </tr>
    <tr>
      <th>3</th>
      <td>-0.1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>-0.2</td>
    </tr>
    <tr>
      <th>5</th>
      <td>0.4</td>
    </tr>
    <tr>
      <th>6</th>
      <td>0.5</td>
    </tr>
    <tr>
      <th>7</th>
      <td>0.6</td>
    </tr>
    <tr>
      <th>8</th>
      <td>-0.9</td>
    </tr>
  </tbody>
</table>
</div>




```python
(df['price_change'] > 0).astype(int).groupby(
    (df['price_change'] > 0).astype(int).diff().ne(0).cumsum()
).cumsum()
```




    0    0
    1    1
    2    2
    3    0
    4    0
    5    1
    6    2
    7    3
    8    0
    Name: price_change, dtype: int64




```python
positive_change = (df['price_change'] > 0).astype(int)
positive_change
```




    0    0
    1    1
    2    1
    3    0
    4    0
    5    1
    6    1
    7    1
    8    0
    Name: price_change, dtype: int64




```python
positive_change.diff()
```




    0    NaN
    1    1.0
    2    0.0
    3   -1.0
    4    0.0
    5    1.0
    6    0.0
    7    0.0
    8   -1.0
    Name: price_change, dtype: float64




```python
positive_change.diff().ne(0)
```




    0     True
    1     True
    2    False
    3     True
    4    False
    5     True
    6    False
    7    False
    8     True
    Name: price_change, dtype: bool




```python
positive_change_levels = positive_change.diff().ne(0).cumsum()
positive_change_levels
```




    0    1
    1    2
    2    2
    3    3
    4    3
    5    4
    6    4
    7    4
    8    5
    Name: price_change, dtype: int64




```python
grouped = positive_change.groupby(positive_change_levels)

for x, y in grouped:
    print("\ngroup", x)
    print(f"contain {y.count()} items: \n{y}")
        
```

    
    group 1
    contain 1 items: 
    0    0
    Name: price_change, dtype: int64
    
    group 2
    contain 2 items: 
    1    1
    2    1
    Name: price_change, dtype: int64
    
    group 3
    contain 2 items: 
    3    0
    4    0
    Name: price_change, dtype: int64
    
    group 4
    contain 3 items: 
    5    1
    6    1
    7    1
    Name: price_change, dtype: int64
    
    group 5
    contain 1 items: 
    8    0
    Name: price_change, dtype: int64
    


```python
grouped.cumsum()
```




    0    0
    1    1
    2    2
    3    0
    4    0
    5    1
    6    2
    7    3
    8    0
    Name: price_change, dtype: int64



