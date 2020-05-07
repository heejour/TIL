# value_counts()

categorical 한 Series의 각 값의 갯수를 알려줍니다 

- The value_counts() function is used to get a Series containing counts of unique values.
- The resulting object will be in descending order so that the first element is the most frequently-occurring element. Excludes NA values by default.

```python
Series.value_counts(self, normalize=False, sort=True, ascending=False, bins=None, dropna=True)
```

ex) Pandas dataframe 과 사용할 때 
```python
df["column_name"].value_counts()
```

### resource

- https://www.w3resource.com/pandas/series/series-value_counts.php
