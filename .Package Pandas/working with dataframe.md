### Create a dataframe called ```df```
```python
import pandas as pd
df = pd.DataFrame({'DATA_TIME' : ['2018/1/19 00:00','2018/2/6 07:00','2018/3/5 22:00','2018/12/8 05:00','2018/12/15 05:15'],
                   'DISTRICT_ID' : ['D327','D327','D327','D327','D327'],
                   'REGION_ID' : ['R451','R451','R451','R451','R451']})
```
|DATA_TIME|DISTRICT_ID|REGION_ID|
|:-------:|:-------:|:-------:|
|`string`|`string`|`string`|
|2018/1/19 00:00|D327|R451|
|2018/2/6 07:00|D327|R451|
|2018/3/5 22:00|D327|R451|
|2018/12/8 05:00|D327|R451|
|2018/12/15 05:15|D327|R451|

---

### Method : ```DataFrame[column].str.Slice```
```python
df['Len of DATA_TIME'] = [len(i) for i in df['DATA_TIME']]
df['date'] = df['DATA_TIME'].str.slice(0,-5)
df['hour'] = df['DATA_TIME'].str.slice(-5)
```
|DATA_TIME|Len of DATA_TIME|date|hour|
|:-------:|:-------:|:-------:|:-------:|
|`string`|`int64`|`string`|`string`|
|2018/1/19 00:00|15|2018/1/19|00:00|
|2018/2/6 07:00|14|2018/2/6|00:00|
|2018/3/5 22:00|14|2018/3/5|22:00|
|2018/12/8 05:00|15|2018/12/8|05:00|
|2018/12/15 05:15|16|2018/12/15|05:15|

在有一次要切割```DATA_TIME```分為日期和小時區間的時候，發現到在python語法指定位置時，```slice(0,-5)```在這時候很好用，因為每個日期字串的長度不一，
不像是如果要切割固定長度的```DISTRICT_ID```的後三碼，可以有兩種輸入法```slice(1,4)```、```slice(-3)```，兩者所裁切的長度是一樣的，但前者裁切的位置是固定的```(1,4)```，但後者的裁切位置則是不固定的從後面往前數```3```個，這個小眉角在切割```DATA_TIME```前段時，剛好可以使用。

---

### Method : ```pandas.to_datetime```
In the past , `pd.to_datetime` need more parameter like `pd.to_datetime(df['DATA_TIME'],format='%d/%m/%Y']`.  
Now, this function is smart enough to identify the format automatically.  
So, you just need to input the Series into `pd.to_datetime` and always don't worry about the format.

```python
import pandas as pd
df = pd.DataFrame()
df['date_string'] = ['20190315','2019/03/15','2019/3/15',
                     '2019/March/15','2019/Mar/15','2019/mar/15',
                     '2019-March-15','2019-Mar-15','2019-mar-15',
                     '2019 03 15','2019 March 15',
                     '2019 15 March','2019 15 Mar','Mar 15 2019',
                     'Mar 15 2019 15:30:45','Mar 15 2019 153045']
df['date_datetime'] = pd.to_datetime(df['date_string'])
```
|date_string|date_datetime|
|:-------:|:-------:|
|`string`|`datetime64[ns]`|
|20190315|2019-03-15 00:00:00|
|2019/03/15|2019-03-15 00:00:00|
|2019/3/15|2019-03-15 00:00:00|
|2019/March/15|2019-03-15 00:00:00|
|2019/Mar/15|2019-03-15 00:00:00|
|2019/mar/15|2019-03-15 00:00:00|
|2019-March-15|2019-03-15 00:00:00|
|2019-Mar-15|2019-03-15 00:00:00|
|2019-mar-15|2019-03-15 00:00:00|
|2019 03 15|2019-03-15 00:00:00|
|2019 March 15|2019-03-15 00:00:00|
|2019 15 March|2019-03-15 00:00:00|
|2019 15 Mar|2019-03-15 00:00:00|
|Mar 15 2019|2019-03-15 00:00:00|
|Mar 15 2019 15:30:45|2019-03-15 15:30:45|
|Mar 15 2019 153045|2019-03-15 15:30:45|

Get datetime by using ```Unix timestamp``` (or called```Unix time```,```POSIX time```)
```python
import time
import pandas as pd
t = time.time() + 3600 * 8 # UTC + 8 hours
t1 = pd.to_datetime(t)
t2 = pd.to_datetime(t,unit='s')
t3 = pd.to_datetime(int(t),unit='s')
print('t1 =', t1)
print('t2 =', t2)
print('t3 =', t3)
print('str(t3)[:10] =', str(t3)[:10])
```
```
# print
t1 = 1970-01-01 00:00:01.553783525
t2 = 2019-03-28 14:32:05.705245256
t3 = 2019-03-28 14:32:05
str(t3)[:10] = 2019-03-28
```

---
