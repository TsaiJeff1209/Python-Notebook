Reference ： [Add Binary](https://leetcode.com/problems/add-binary/description/)

Given two binary strings, return their sum (also a binary string).
For example,
a = "11"
b = "111"
Return "1010".

```python
a = '11'
b = '111'

print(int(a,2)) # output : 3
print(int(b,2)) # output : 7

my_sum = int(b,2) + int(b,2) # my_sum = 10

print(bin(my_sum))     # output : '0b1010'
print(bin(my_sum)[2:]) # output : '1010'
```
