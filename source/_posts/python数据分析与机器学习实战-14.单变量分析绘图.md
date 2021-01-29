---
title: python数据分析与机器学习实战-14.单变量分析绘图
date: 2018-12-07 
categories: python
permalink: 
tags: 数据分析 
---


```
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
from scipy import stats,integrate
%matplotlib inline
```



```
sns.set(color_codes = True)
x = np.random.normal(size=100)
sns.distplot(x,kde=False)
/anaconda3/lib/python3.6/site-packages/matplotlib/axes/_axes.py:6462: UserWarning: The 'normed' kwarg is deprecated, and has been replaced by the 'density' kwarg.
  warnings.warn("The 'normed' kwarg is deprecated, and has been "





<matplotlib.axes._subplots.AxesSubplot at 0x1a1510af28>
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-14-%E5%8D%95%E5%8F%98%E9%87%8F%E5%88%86%E6%9E%90%E7%BB%98%E5%9B%BE%E2%80%9D/output_1_2.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-14-单变量分析绘图”/output_1_2.png)

```
sns.distplot(x,bins=20,kde=False)
/anaconda3/lib/python3.6/site-packages/matplotlib/axes/_axes.py:6462: UserWarning: The 'normed' kwarg is deprecated, and has been replaced by the 'density' kwarg.
  warnings.warn("The 'normed' kwarg is deprecated, and has been "





<matplotlib.axes._subplots.AxesSubplot at 0x1a1505f860>
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-14-%E5%8D%95%E5%8F%98%E9%87%8F%E5%88%86%E6%9E%90%E7%BB%98%E5%9B%BE%E2%80%9D/output_2_2.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-14-单变量分析绘图”/output_2_2.png)

```
x = np.random.gamma(6,size=200)
sns.distplot(x,kde=False,fit=stats.gamma)
/anaconda3/lib/python3.6/site-packages/matplotlib/axes/_axes.py:6462: UserWarning: The 'normed' kwarg is deprecated, and has been replaced by the 'density' kwarg.
  warnings.warn("The 'normed' kwarg is deprecated, and has been "





<matplotlib.axes._subplots.AxesSubplot at 0x1a153a0240>
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-14-%E5%8D%95%E5%8F%98%E9%87%8F%E5%88%86%E6%9E%90%E7%BB%98%E5%9B%BE%E2%80%9D/output_3_2.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-14-单变量分析绘图”/output_3_2.png)

```
mean,cov = [0,1],[(1,.5),(.5,1)]
data = np.random.multivariate_normal(mean,cov,200)
df = pd.DataFrame(data,columns=["x","y"])
df
```































































































































































































































































































































|      | x         | y         |
| :--- | :-------- | :-------- |
| 0    | -0.174087 | 1.795256  |
| 1    | -0.416757 | 0.638361  |
| 2    | -1.188138 | -0.331589 |
| 3    | -0.609992 | 0.435072  |
| 4    | -1.839588 | 1.710629  |
| 5    | -0.636881 | 0.890326  |
| 6    | -0.833977 | 0.792370  |
| 7    | 1.789158  | 2.060371  |
| 8    | 1.156777  | 0.663219  |
| 9    | 0.423476  | 0.673290  |
| 10   | -0.412169 | 0.751990  |
| 11   | -1.126475 | 0.535133  |
| 12   | 1.323243  | 1.533676  |
| 13   | -0.023044 | -0.599542 |
| 14   | 0.691180  | 0.879479  |
| 15   | 1.478605  | 2.477569  |
| 16   | -1.637043 | -0.499630 |
| 17   | -0.094884 | 2.142044  |
| 18   | -0.989239 | 1.218270  |
| 19   | 1.420987  | 1.013807  |
| 20   | 0.360396  | 2.465208  |
| 21   | 1.358501  | 1.184887  |
| 22   | 2.339145  | 1.285469  |
| 23   | 1.282484  | 2.062299  |
| 24   | 0.854708  | 0.706735  |
| 25   | -0.223393 | -0.172632 |
| 26   | -0.513652 | 0.535946  |
| 27   | 1.207449  | 1.181039  |
| 28   | -1.219564 | -1.178302 |
| 29   | -0.855500 | 0.167194  |
| …    | …         | …         |
| 170  | 1.022425  | 1.816807  |
| 171  | 0.344980  | 0.766577  |
| 172  | 1.043292  | 0.955718  |
| 173  | 0.765037  | 2.321773  |
| 174  | 0.683540  | 0.501221  |
| 175  | 1.188854  | 0.022803  |
| 176  | -0.287907 | -0.166137 |
| 177  | -0.778977 | 0.036364  |
| 178  | -1.875389 | 0.689938  |
| 179  | 0.183550  | 1.683339  |
| 180  | 0.220839  | 1.396213  |
| 181  | 0.660952  | 1.921363  |
| 182  | -2.357542 | 1.145418  |
| 183  | 0.521454  | 0.304456  |
| 184  | -0.321098 | -1.072025 |
| 185  | -0.265391 | 1.166742  |
| 186  | 1.182235  | 2.652254  |
| 187  | 0.920143  | 1.772478  |
| 188  | 0.620841  | 1.806727  |
| 189  | -0.892951 | 0.177710  |
| 190  | -0.463518 | 2.034266  |
| 191  | -0.031959 | 0.967620  |
| 192  | -0.412957 | 0.324511  |
| 193  | -0.021698 | 0.949692  |
| 194  | 1.897446  | 2.806375  |
| 195  | -0.346429 | 0.899780  |
| 196  | -0.320803 | -0.144683 |
| 197  | -0.332870 | 0.751261  |
| 198  | -0.579072 | 0.318083  |
| 199  | -0.889261 | 0.091241  |



200 rows × 2 columns



观察两个变量之间的分布关系最好用散点图

```
sns.jointplot(x="x",y="y",data=df)
/anaconda3/lib/python3.6/site-packages/matplotlib/axes/_axes.py:6462: UserWarning: The 'normed' kwarg is deprecated, and has been replaced by the 'density' kwarg.
  warnings.warn("The 'normed' kwarg is deprecated, and has been "
/anaconda3/lib/python3.6/site-packages/matplotlib/axes/_axes.py:6462: UserWarning: The 'normed' kwarg is deprecated, and has been replaced by the 'density' kwarg.
  warnings.warn("The 'normed' kwarg is deprecated, and has been "





<seaborn.axisgrid.JointGrid at 0x1a22fb1cf8>
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-14-%E5%8D%95%E5%8F%98%E9%87%8F%E5%88%86%E6%9E%90%E7%BB%98%E5%9B%BE%E2%80%9D/output_6_2.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-14-单变量分析绘图”/output_6_2.png)

```
x,y = np.random.multivariate_normal(mean,cov,1000).T
with sns.axes_style("white"):
    sns.jointplot(x=x,y=y,data=df,kind="hex",color='k')
/anaconda3/lib/python3.6/site-packages/matplotlib/axes/_axes.py:6462: UserWarning: The 'normed' kwarg is deprecated, and has been replaced by the 'density' kwarg.
  warnings.warn("The 'normed' kwarg is deprecated, and has been "
/anaconda3/lib/python3.6/site-packages/matplotlib/axes/_axes.py:6462: UserWarning: The 'normed' kwarg is deprecated, and has been replaced by the 'density' kwarg.
  warnings.warn("The 'normed' kwarg is deprecated, and has been "
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-14-%E5%8D%95%E5%8F%98%E9%87%8F%E5%88%86%E6%9E%90%E7%BB%98%E5%9B%BE%E2%80%9D/output_7_1.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-14-单变量分析绘图”/output_7_1.png)

```
iris = sns.load_dataset("iris")
sns.pairplot(iris)
<seaborn.axisgrid.PairGrid at 0x1a23d144e0>
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-14-%E5%8D%95%E5%8F%98%E9%87%8F%E5%88%86%E6%9E%90%E7%BB%98%E5%9B%BE%E2%80%9D/output_8_1.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-14-单变量分析绘图”/output_8_1.png)

[# seaborn](https://www.cishao.cn/tags/seaborn/)
