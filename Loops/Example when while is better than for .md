# Example when while is better than for in Python
## 啟發來源是leetcode的 [387. First Unique Character in a String](https://leetcode.com/problems/first-unique-character-in-a-string)

### 2018/3/25 beats 86.46 % of python3
### Spend 88 ms


```python
def firstUniqChar(s):
  if len(s) == 0:
    return -1
  s1 = s
  while len(s1) > 0:
    if s1.count(s1[0]) == 1:
      return s.find(s1[0])
    s1 = s1.replace(s1[0],"")
  return -1
```

初始的樣子,

