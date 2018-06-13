123

### Table: Letter to digit
|Item|Image|Code|
|:-:|:--:|:-|
|...|...|...|
|...|...|...|
|Error Bar|...|...|
|...|...|...|
|Fill Between|![Fill_Between](https://github.com/TsaiJeff1209/Python-Notebook/blob/master/.Package%20Matplotlib/fill_between.png)|`x_values = range(10)`<br>`y_values = [10, 12, 13, 13, 15, 19, 20, 22, 23, 29]`<br>`y_lower = [8, 10, 11, 11, 13, 17, 18, 20, 21, 27]`<br>`y_upper = [12, 14, 15, 15, 17, 21, 22, 24, 25, 31]`<br>#this is the shaded error<br>`plt.fill_between(x_values, y_lower, y_upper, alpha=0.2)`<br>#this is the line itself<br>`plt.plot(x_values, y_values)`<br>`plt.show()`|
|...|...|...|
|...|...|...|
|...|...|...|
|...|...|...|

