123

### Table: Letter to digit
|Item|Image|Code|
|:----------:|:----------:|:----------|
|...|...|...|
|...|...|...|
|Error Bar|...|...|
|...|...|...|
|Fill Between||import codecademylib<br>from matplotlib import pyplot as plt<br>months = range(12)<br>month_names = ["Jan", "Feb", "Mar", "Apr", "May", "Jun", "Jul", "Aug", "Sep", "Oct", "Nov", "Dec"]<br>revenue = [160, 140, 175, 195, 215, 215, 220, 230, 200, 195, 180, 165]<br>#your work here<br>y_lower = [i*0.9 for i in revenue]<br>y_upper = [i*1.1 for i in revenue]<br>plt.fill_between(months,y_lower,y_upper,alpha=0.2)<br>plt.plot(months,revenue)<br>ax = plt.subplot()<br>ax.set_xticks(months)<br>ax.set_xticklabels(month_names)<br>plt.show()|

