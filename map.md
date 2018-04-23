# [66. Plus One](https://leetcode.com/problems/plus-one/description/)

```pythom
class Solution:
    def plusOne(self, digits):
        """
        :type digits: List[int]
        :rtype: List[int]
        """
        return [int(i) for i in str(int("".join(map(str,digits)))+1)]
        
```
