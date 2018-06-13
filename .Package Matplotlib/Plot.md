123

### Table: Letter to digit
|Item|Image|Code|
|:-:|:--:|:-|
|...|...|...|
|...|...|...|
|Error Bar|...|...|
|...|...|...|
|Fill Between|![Fill_Between](https://github.com/TsaiJeff1209/Python-Notebook/blob/master/.Package%20Matplotlib/image/fill_between.png)|`x_values = range(10)`<br>`y_values = [10,12,13,13,15,19,20,22,23,29]`<br>`y_lower = [8,10,11,11,13,17,18,20,21,27]`<br>`y_upper = [12,14,15,15,17,21,22,24,25,31]`<br>#this is the shaded error<br>`plt.fill_between(x_values, y_lower, y_upper, alpha=0.2)`<br>#this is the line itself<br>`plt.plot(x_values, y_values)`<br>`plt.show()`|
|Pie<br>Legend<br>Label<br>Percent|![pie](https://github.com/TsaiJeff1209/Python-Notebook/blob/master/.Package%20Matplotlib/image/pie.png)|`from matplotlib import pyplot as plt`<br>`payment_method_names = ["Card Swipe", "Cash", "Apple Pay", "Other"]`<br>`payment_method_freqs = [270, 77, 32, 11]`<br>`# label and percent`<br>`plt.pie(payment_method_freqs, labels=payment_method_names,autopct='%0.1f%%')`<br>`# legend`<br>`plt.legend(payment_method_names)`<br>`plt.axis('equal')`<br>`plt.show()`|
|...|...|...|


### Plot Structure
```python
from matplotlib import pyplot as plt
# set the window and axis of image
plt.figure(figsize=(width,height))
plt.axis([x_start, x_end, y_start, y_end])

# Plot
    # line plot
plt.plot(x_values,y_values)
    # bar plot (categorical data)
plt.bar(x_category, y_value)
    # histogram plot
plt.hist(values)
    # pie plot
plt.pie(values)

# title and label
plt.legend(["variable A","variable B"])
plt.title("Title")
plt.xlabel("xlabel")
plt.ylabel("ylabel")

# more detial about xlabel, ylabel
ax = plt.subplot()
ax.set_xticks(x_values)
ax.set_xticklabels(x_labels)
ax.set_yticks(y_values)
ax.set_yticklabels(y_labels)

# end of plot
plt.savefig('save_a_image.png')
plt.show()
```


```python
from matplotlib import pyplot as plt
# line plot
    # basic
plt.plot(x_values,y_values)
    # two line in one figure
plt.plot(x1_values,y1_values)
plt.plot(x2_values,y2_values)
    # Line with Shaded Error
plt.plot(x_values,y_values)
plt.fill_between(x_values,y_lower_bound,y_upper_bound,alpha=0.2) # alpha: This sets the transparency of the histogram

# bar plot (categorical data)
    # basic
plt.bar(x_category, y_value)
    # basic add error
plt.bar(x_category, y_value, yerr = error_list, capsize=3)
    # Side By Side Bars
t = 2 # Number of datasets (example: sales1,sales2, there ara 2 sales)
d = 10 # Number of sets of bars (example: )
w = 0.8 # Width of each bar
n = 1  # This is our second dataset (out of 2)
n = 1 ; x1_category = [t*element + w*n for element in range(d)]
n = 2 ; x2_category = [t*element + w*n for element in range(d)]
plt.bar(x1_category,y1_value)
plt.bar(x2_category,y2_value)
    # Stacked Bars
import numpy as np
plt.bar(x,As)
plt.bar(x,Bs,bottom=As)
c_bottom = np.add(As, Bs)
plt.bar(x,Cs,bottom=c_bottom)

# histogram plot
    # basic
plt.hist(values,bins=10) # default of bins is 10
    # normalized
plt.hist(values,normed=True)
    # other parameters
plt.hist(values, linewidth=2)
plt.hist(values, alpha=0.4) # alpha: This sets the transparency of the histogram
plt.hist(values, histtype = 'step') # histtype='step': draw just the outline of a histogram
    # Two Histograms on a Plot
plt.hist(values_1,normed=True) # normalized is optional, and it's always useful when compare.
plt.hist(values_2,normed=True)

# pie plot
    # basic
plt.pie(values)
plt.axis('equal') # make it overlook
    # other parameter
plt.pie(values, labels = value_labels) # add labels
plt.pie(values, autopct='%0.2f') # example 4.08 , add percentage for every item
plt.pie(values, autopct='%0.2f%%') # example 4.08% , add percentage for every item
plt.pie(values, autopct='%d%%') # example 4 , add percentage for every item

```
