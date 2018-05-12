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


### Using ```pandas.to_datetime``` to transform DATA_TIME from string type to datetime type.
```python
import pandas as pd
df['DATA_TIME_datetype'] = pd.to_datetime(df['DATA_TIME'])
```
|DATA_TIME|DATA_TIME_datetype|
|:-------:|:-------:|
|`string`|`datetime64[ns]`|
|2018/1/19 00:00|2018-01-19 00:00:00|
|2018/2/6 07:00|2018-02-06 07:00:00|
|2018/3/5 22:00|2018-03-05 22:00:00|
|2018/12/8 05:00|2018-12-08 05:00:00|
|2018/12/15 05:15|2018-12-15 05:15:00|

In the past , ```pd.to_datetime``` need more parameter like ```pd.to_datetime(df['DATA_TIME'],format='%d/%m/%Y']```.  
Now, this function is smart enough to identify the format automatically.  
So, you just need to input the Series into ```pd.to_datetime``` and always don't worry about the format.






