# (一)查找速度上的差異
## 同一套邏輯的函數將 dict 和 list 分別套入，速度比是 64ms 和 596ms　
### 參照[1_Two Sum](https://github.com/TsaiJeff1209/LeetCode-Problem-Python)
```python
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
* List spend 596 ms , beats 37.22 %
* Dict spend  64 ms , beats 57.32 %  

Google Dict特性：
1：查找速度快　2：浪費空間　3：key不可以重複，且不可變　4：資料無序排放
