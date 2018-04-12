## 參照 [747 Largest Number At Least Twice of Others](https://github.com/TsaiJeff1209/LeetCode-Problem-Python/blob/master/747%20Largest%20Number%20At%20Least%20Twice%20of%20Others.md)

```python
# i, j are non-negative integers
# if i is at least twice as much as j, return 1, or return 0
```
##### 自己原本寫法，缺點是若 ```j = 0``` ，則判斷式會出現error，在不更改原架構的情況下，還要輸入多餘的判斷式避免 ```j = 0```
```python
if i/j >= 2 :
  return 1
else:
  return 0
```
##### 若將分母的 ```j``` 移向，形成相同結果的等式，就可以避免 ```j = 0``` 的情況，避免輸入更多的判斷式，而且等式還可正常使用
```python
if i >= 2 * j :
  return 1
else:
  return 0
```

