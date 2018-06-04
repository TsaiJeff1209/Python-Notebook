# (一)查找速度上的差異
## 同一套邏輯的函數分別套入 dict 和 list，速度比是 64ms 和 372ms　
### 參照 [LeetCode-Problem-Python](https://github.com/TsaiJeff1209/LeetCode-Problem-Python) 的 [001 Two Sum](https://github.com/TsaiJeff1209/LeetCode-Algorithms-Python/blob/master/001%20Two%20Sum.md)

```python
#　List Method
class Solution:
    def twoSum(self, nums, target):
        """
        :type nums: List[int]
        :type target: int
        :rtype: List[int]
        """
        lst = []
        for i, num in enumerate(nums):
            rem = target - num
            if rem in lst:
                return [nums.index(rem), i]
            lst += [num]
        return None

# Dictionary Method
class Solution:
    def twoSum(self, nums, target):
        """
        :type nums: List[int]
        :type target: int
        :rtype: List[int]
        """
        dic = {}
        for i, num in enumerate(nums):
            rem = target - num
            if rem in dic:
                return [dic[rem], i]
            dic[num] = i
        return None
```
第一次玩LeetCode發現可以參照神手的答案,因此參考解答答出來的，從4332ms降到64ms，非常佩服神人們的邏輯和運算速度，同時我嘗試了使用list和dict兩種作法，沒想到差異可以這麼大，如下：
* List spend 372 ms , beats 45.47 %
* Dict spend  64 ms , beats 57.32 %  

Google Dict特性：
1：查找速度快　2：浪費空間　3：key不可以重複，且不可變　4：資料無序排放
