

chr(65) A

ord("A") 65

### Table: Letter to digit
|Code|Number|/|Code|Number|
|:----------:|:----------:|:----------:|:----------:|:----------:|
|ord(`string`)|`integer`|/|ord(`string`)|`integer`|
|`ord("A")`|65|/|`ord("a")`|97|
|`ord("B")`|66|/|`ord("b")`|98|
|...|...|/|...|...|
|`ord("Y")`|89|/|`ord("y")`|121|
|`ord("Z")`|90|/|`ord("z")`|122|

### Table: digit to Letter
|Code|Number|/|Code|Number|
|:----------:|:----------:|:----------:|:----------:|:----------:|
|chr(`integer`)|`string`|/|chr(`integer`)|`string`|
|`chr(65)`|"A"|/|`chr(97)`|"a"|
|`chr(66)`|"B"|/|`chr(98)`|"b"|
|...|...|/|...|...|
|`chr(89)`|"Y"|/|`chr(121)`|"y"|
|`chr(90)`|"Z"|/|`chr(122)`|"z"|

### 字母比大小
|Code|Output|Explain|
|:----------:|:----------:|:----------:|
|`66>65`|`True`|trivial|
|`'B'>'A'`|`True`|66 is great than 65, so output is True|
|`'A'>'Z'`|`False`|65 is less than 90, so output is False|
|`'a'>'A'`|`True`|97 is great than 65, so output is True|
