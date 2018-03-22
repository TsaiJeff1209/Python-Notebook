
# 關於Python中 `*` 和 `**` 的使用


## 舉例(一) 套用在資料上
假設有個 Function `Intro`：
```python
def Intro(name, age, country, food, habit):
  print('I am {}. I am {}. I live in {}. My favorite food is {}. I love {}'.format(
          name, age, country, food, habit))
```
而現在有兩種型態的資料，分別是 List 的 `lst` 和 dict 的 `dic`：
```python
lst = ['Jeff',25,'Taipei','Apple','hiking']
dic = {'name':'Jeff', 'age':25, 'country':'Taipei', 'food':'apple', 'habit':'hiking'}
```
套入函數時，不使用 `*` 和 `**` 的情況下，你可能會這麼做：
```python
Intro(lst[0], lst[1], lst[2], lst[3], lst[4])
Intro(dic['name'], dic['age'], dic['country'], dic['food'], dic['habit'])
```
而使用 `*` 和 `**` 的情況下：
```python
Intro(*lst)
Intro(**dic)
```

## 舉例(二) 定義 Function 時，套用在 Parameters
假設自己寫一個兩數字相加的 Function `add2`：
```python
def add2(a,b):
  return sum(a,b)
```
進一步延伸到三個數字相加的 Function `add3`：
```python
def add3(a,b,c):
  return sum(a,b,c)
```
你可能已經想到，若要再更進一步相加更多的數字呢？ 這樣的函數設計方式會遇到兩個缺點和一個現象
### 缺點
* 大量的數字相加，函數的參數列會很長一串
* 針對不同數量的數字，皆需要重新定義一個新的函數並使用新的 function name
### 現象
* 過長的參數列和函數功能的高重複性，皆會造成coding時版面混亂，且需要修正函數時也不易操作

而 `*` 恰好能解決此現象：
```python
def add(*n):
  return sum(n)
```
此時的 `*n` 可以輸入不同數量的數字，非常彈性，例如：
```pythoh
add(1,2,3,4)
add(1,2,3,4,5,6,7,8,9,10)
```

## 結論
說不上是大工具，但可以看的出它的彈性之大，若有好的舉例待日後補充

## 個人心得
對於還是初學階段的我來說，在做模型參數選擇的時候，第一次碰到 `*` 和 `**` ，順便做個筆記，附上當時正在看的連結

[sklearn.ensemble.BaggingClassifier](http://scikit-learn.org/stable/modules/generated/sklearn.ensemble.BaggingClassifier.html)  
[sklearn.model_selection.GridSearchCV](http://scikit-learn.org/stable/modules/generated/sklearn.model_selection.GridSearchCV.html)  
[ParameterGrid() Examples](https://www.programcreek.com/python/example/91157/sklearn.model_selection.ParameterGrid) ← 在此看到 `**`



