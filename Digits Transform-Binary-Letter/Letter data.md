

chr(65) A

ord("A") 65

### Table: Letter to digit
|Code|Number|
|:----------:|:----------:|
|ord(`string`)|`integer`|
|`ord("A")`|65|
|`ord("B")`|66|
|...|...|
|`ord("Y")`|89|
|`ord("Z")`|90|

### Table: digit to Letter
|Code|Number|
|:----------:|:----------:|
|chr(`integer`)|`string`|
|`chr(65)`|"A"|
|`chr(66)`|"B"|
|...|...|
|`chr(89)`|"Y"|
|`chr(90)`|"Z"|

### 字母比大小
|Code|Output|Explain|
|:----------:|:----------:|:----------:|
|`66>65`|`True`||
|`'B'>'A'`|`True`|66 is great than 65, so output is True|
|`'A'>'Z'`|`False`|65 is less than 90, so output is False|
|`'a'>'A'`|`True`|97 is great than 65, so output is True|
