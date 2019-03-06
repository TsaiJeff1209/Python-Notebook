#### [MySQL - Query](https://github.com/TsaiJeff1209/Python-Notebook/new/master#mysql---query-1)
#### [MySQL - Upload](https://github.com/TsaiJeff1209/Python-Notebook/new/master#mysql---upload-1)
#### [MsSQL - Query](https://github.com/TsaiJeff1209/Python-Notebook/new/master#mssql---query-1)
#### [MsSQL - Execute](https://github.com/TsaiJeff1209/Python-Notebook/new/master#mssql---execute-1)
#### [MsSQL - Upload](https://github.com/TsaiJeff1209/Python-Notebook/new/master#mssql---upload-1)


## MySQL - Query
```python
import pandas as pd
import MySQLdb
def cto_basic_query(db_name, sql):
    HOST = "192.168.7.65"
    USER = "CTO_OFFICE"
    PASS = "Welcome1"
    DBNAME = db_name
    conn = MySQLdb.connect(HOST, USER, PASS, DBNAME, charset='utf8')
    df = pd.read_sql(sql, conn)
    conn.close()
    return df
```

## MySQL - Upload
```python
import pandas as pd
from sqlalchemy import create_engine
def cto_upload(db_name, table_name, df):
    HOST = "192.168.7.65"
    USER = "CTO_OFFICE"
    PASS = "Welcome1"
    PROT = 3306
    DBNAME = db_name
    connect_info = 'mysql+pymysql://{}:{}@{}:{}/{}?charset=utf8'.format(USER, PASS, HOST, PROT, DBNAME)
    engine = create_engine(connect_info)
    df.to_sql(name = table_name, 
              con = engine, 
              if_exists = 'append',
              index = False)
    return None
```

## MsSQL - Query
```python
import pandas as pd
import pymssql
def mssql_query(sql):
    HOST = "your_ip"
    USER = "your_user"
    PASS = "your_password"
    DBNAME = "your_dbname"
    conn = pymssql.connect(server = HOST, user = USER, password = PASS, database = DBNAME)
    df = pd.read_sql(sql, conn)
    conn.close()
    return df
```

## MsSQL - Execute
```python
import pandas as pd
import pymssql
def mssql_execute(sql):
    HOST = "your_ip"
    USER = "your_user"
    PASS = "your_password"
    DBNAME = "your_dbname"
    conn = pymssql.connect(server = HOST, user = USER, password = PASS, database = DBNAME)
    cursor = conn.cursor()
    cursor.execute(sql)
    conn.commit()
    conn.close()
    return None
```
## MsSQL - Upload
```python
import pandas as pd
import pymssql
from sqlalchemy import create_engine
from sqlalchemy.types import Integer, Float, DateTime
def mssql_upload(df, method, col_types):
    HOST = "your_ip"
    USER = "your_user"
    PASS = "your_password"
    DBNAME = "your_dbname"
    connect_info = 'mssql+pymssql://{}:{}@{}/{}'.format(USER,PASS,HOST,DBNAME)
    engine = create_engine(connect_info)
    df.to_sql(name = "your_table_name", 
              con = engine, 
              if_exists = method, # ["append","replace","fail"]
              index = False,
              dtype = col_types)
    engine.dispose()
    return None
```

