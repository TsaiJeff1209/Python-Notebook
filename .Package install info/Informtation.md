

## Package: `lzma`、`backports.lzma`
### Satisfied version : `Python2.7`
```
# what packages you probability need before install lzma
  # Returns the red text like 'distributed 1.21.8 requires msgpack, which is not installed.'
  pip install msgpack
  # Returns the red text like 'mkl-fft 1.0.0 requires cython, which is not installed.'
  pip install cython

# install lzma
pip install -i https://pypi.anaconda.org/carlkl/simple backports.lzma
```
Link  
1. [Backport of Python 3.3's 'lzma' module for XZ/LZMA compressed files.](https://anaconda.org/carlkl/backports.lzma)

---

### xgboost
參照 [windows下安装xgboost教程](https://blog.csdn.net/zhili8866/article/details/69788570)

1. [Python Extension Packages for Windows](https://www.lfd.uci.edu/~gohlke/pythonlibs/#xgboost)下載對應版本的安裝檔，以我為例，我的是64位，python3.6，下載的檔案為：xgboost-0.6-cp36-cp36m-win_amd64.whl。(cp36對應python3.6)  
2. 記下安裝檔位置，我是放在`D:\Download\xgboost-0.6-cp36-cp36m-win_amd64.whl`。  
3. 開啟 `Anaconda Prompt` ，直接輸入指令加上檔案位置 `pip install D:\Download\xgboost-0.6-cp36-cp36m-win_amd64.whl`。  
4. 等待完成。  


### MySQLdb
try `pip install mysqlclient`

