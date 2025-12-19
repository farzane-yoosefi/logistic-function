This is a basic machine learning model
>> These notes serve to demonstrate my machine learning knowledge to potential employers while also helping beginners learn complex concepts in simple terms.

```python
#in this code I want to plot a logistic function on different sets of data an compare them 
import numpy as np
import matplotlib.pyplot as plt

def logistic_function (x):
    log_fun = 1/(1+np.exp(-x))
    return log_fun
x1 = np.array([-3,-2,-1,0,1,2,3])
x2 = np.array([-5,-4,-3,-2,-1,0,1,2,3,4,5])
x3 = np.array([-1,0,1])
x4 = np.array([1,2,3,4,5])
x_values = [x1,x2,x3,x4]
x_titles = ['-3 to +3','-5 to +5','-1 to +1','1 to 5']

y1 = logistic_function(x1)
y2 = logistic_function(x2)
y3 = logistic_function(x3)
y4 =logistic_function(x4)

fig,axis = plt.subplots(2,2)
axis = axis.flatten()

#now we plot the first result
for i,(data,title) in enumerate(zip(x_values,x_titles)):
    axis[i].plot(data,logistic_function(data),'o-')
    axis[i].set_title(title)
    axis[i].grid(True,alpha= 0.3)
    plt.tight_layout()
plt.show()
```
