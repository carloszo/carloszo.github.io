---
title: python数据分析与机器学习实战-17.FacetGrid使用方法及绘制多变量
date: 2018-12-07 
categories: python
permalink: 
tags: 数据分析 
---

```
import pandas as pd
import numpy as np
import matplotlib as mpt
import matplotlib.pyplot as plt
import seaborn as sns
```



```
tips=sns.load_dataset("tips")
tips.head()
```





































































|      | total_bill | tip  | sex    | smoker | day  | time   | size |
| :--- | :--------- | :--- | :----- | :----- | :--- | :----- | :--- |
| 0    | 16.99      | 1.01 | Female | No     | Sun  | Dinner | 2    |
| 1    | 10.34      | 1.66 | Male   | No     | Sun  | Dinner | 3    |
| 2    | 21.01      | 3.50 | Male   | No     | Sun  | Dinner | 3    |
| 3    | 23.68      | 3.31 | Male   | No     | Sun  | Dinner | 2    |
| 4    | 24.59      | 3.61 | Female | No     | Sun  | Dinner | 4    |



```
g=sns.FacetGrid(tips,col="time")
<seaborn.axisgrid.FacetGrid at 0x1a1155f0f0>
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-17-FacetGrid%E4%BD%BF%E7%94%A8%E6%96%B9%E6%B3%95%E5%8F%8A%E7%BB%98%E5%88%B6%E5%A4%9A%E5%8F%98%E9%87%8F%E2%80%9D/output_2_1.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-17-FacetGrid使用方法及绘制多变量”/output_2_1.png)

```
g=sns.FacetGrid(tips,col="time")
g.map(plt.hist,"total_bill")
<seaborn.axisgrid.FacetGrid at 0x1a1d6a5748>
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-17-FacetGrid%E4%BD%BF%E7%94%A8%E6%96%B9%E6%B3%95%E5%8F%8A%E7%BB%98%E5%88%B6%E5%A4%9A%E5%8F%98%E9%87%8F%E2%80%9D/output_3_1.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-17-FacetGrid使用方法及绘制多变量”/output_3_1.png)

```
g = sns.FacetGrid(tips,col="sex",hue="smoker")
g.map(plt.scatter,"total_bill","tip",alpha=0.7)
g.add_legend()
<seaborn.axisgrid.FacetGrid at 0x1a1e19c0f0>
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-17-FacetGrid%E4%BD%BF%E7%94%A8%E6%96%B9%E6%B3%95%E5%8F%8A%E7%BB%98%E5%88%B6%E5%A4%9A%E5%8F%98%E9%87%8F%E2%80%9D/output_4_1.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-17-FacetGrid使用方法及绘制多变量”/output_4_1.png)

```
g = sns.FacetGrid(tips,col="time",row="smoker",margin_titles=True)
g.map(sns.regplot,"size","total_bill",color="0.3",fit_reg=False,x_jitter=0.1)
<seaborn.axisgrid.FacetGrid at 0x1a1eb23d68>
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-17-FacetGrid%E4%BD%BF%E7%94%A8%E6%96%B9%E6%B3%95%E5%8F%8A%E7%BB%98%E5%88%B6%E5%A4%9A%E5%8F%98%E9%87%8F%E2%80%9D/output_5_1.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-17-FacetGrid使用方法及绘制多变量”/output_5_1.png)

```
g = sns.FacetGrid(tips,col="day",size=4,aspect=0.5)
g.map(sns.barplot,"sex","total_bill")
/anaconda3/lib/python3.6/site-packages/seaborn/axisgrid.py:703: UserWarning: Using the barplot function without specifying `order` is likely to produce an incorrect plot.
  warnings.warn(warning)





<seaborn.axisgrid.FacetGrid at 0x1a21180d30>
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-17-FacetGrid%E4%BD%BF%E7%94%A8%E6%96%B9%E6%B3%95%E5%8F%8A%E7%BB%98%E5%88%B6%E5%A4%9A%E5%8F%98%E9%87%8F%E2%80%9D/output_6_2.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-17-FacetGrid使用方法及绘制多变量”/output_6_2.png)

```
from pandas import Categorical
order_days = tips.day.value_counts().index
print(order_days)
order_days = Categorical(["Thur","Fri","Sat","Sun"])
g = sns.FacetGrid(tips,row="day",row_order=order_days,size=1.7,aspect=4)
g.map(sns.boxplot,"total_bill")
CategoricalIndex(['Sat', 'Sun', 'Thur', 'Fri'], categories=['Thur', 'Fri', 'Sat', 'Sun'], ordered=False, dtype='category')


/anaconda3/lib/python3.6/site-packages/seaborn/axisgrid.py:703: UserWarning: Using the boxplot function without specifying `order` is likely to produce an incorrect plot.
  warnings.warn(warning)





<seaborn.axisgrid.FacetGrid at 0x1a1e4168d0>
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-17-FacetGrid%E4%BD%BF%E7%94%A8%E6%96%B9%E6%B3%95%E5%8F%8A%E7%BB%98%E5%88%B6%E5%A4%9A%E5%8F%98%E9%87%8F%E2%80%9D/output_7_3.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-17-FacetGrid使用方法及绘制多变量”/output_7_3.png)

```
pal = dict(Lunch="seagreen",Dinner="blue")
g = sns.FacetGrid(tips,hue="time",palette=pal,size=5)
g.map(plt.scatter,"total_bill","tip",s=50,alpha=0.7,linewidth=0.5,edgecolor="white")
g.add_legend()
<seaborn.axisgrid.FacetGrid at 0x1a2201f8d0>
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-17-FacetGrid%E4%BD%BF%E7%94%A8%E6%96%B9%E6%B3%95%E5%8F%8A%E7%BB%98%E5%88%B6%E5%A4%9A%E5%8F%98%E9%87%8F%E2%80%9D/output_8_1.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-17-FacetGrid使用方法及绘制多变量”/output_8_1.png)

```
with sns.axes_style("white"):
    g=sns.FacetGrid(tips,row="sex",col="smoker",margin_titles=True,size=2.5)
g.map(plt.scatter,"total_bill","tip",color="#334488",edgecolor="white",lw=0.5)
g.set_axis_labels("total_bill(Us dollar)","tips")
g.set(xticks=[10,30,50],yticks=[2,6,10])
g.fig.subplots_adjust(wspace=0.02,hspace=0.02)
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-17-FacetGrid%E4%BD%BF%E7%94%A8%E6%96%B9%E6%B3%95%E5%8F%8A%E7%BB%98%E5%88%B6%E5%A4%9A%E5%8F%98%E9%87%8F%E2%80%9D/output_9_0.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-17-FacetGrid使用方法及绘制多变量”/output_9_0.png)

```
iris = sns.load_dataset("iris")
g = sns.PairGrid(iris)
g.map(plt.scatter)
<seaborn.axisgrid.PairGrid at 0x1a21f379e8>
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-17-FacetGrid%E4%BD%BF%E7%94%A8%E6%96%B9%E6%B3%95%E5%8F%8A%E7%BB%98%E5%88%B6%E5%A4%9A%E5%8F%98%E9%87%8F%E2%80%9D/output_10_1.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-17-FacetGrid使用方法及绘制多变量”/output_10_1.png)

```
g = sns.PairGrid(iris)
g.map_diag(plt.hist)
g.map_offdiag(plt.scatter)
<seaborn.axisgrid.PairGrid at 0x1a21a84b00>
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-17-FacetGrid%E4%BD%BF%E7%94%A8%E6%96%B9%E6%B3%95%E5%8F%8A%E7%BB%98%E5%88%B6%E5%A4%9A%E5%8F%98%E9%87%8F%E2%80%9D/output_11_1.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-17-FacetGrid使用方法及绘制多变量”/output_11_1.png)

```
g = sns.PairGrid(iris,hue="species")
g.map_diag(plt.hist)
g.map_offdiag(plt.scatter)
g.add_legend()
<seaborn.axisgrid.PairGrid at 0x1a23793860>
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-17-FacetGrid%E4%BD%BF%E7%94%A8%E6%96%B9%E6%B3%95%E5%8F%8A%E7%BB%98%E5%88%B6%E5%A4%9A%E5%8F%98%E9%87%8F%E2%80%9D/output_12_1.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-17-FacetGrid使用方法及绘制多变量”/output_12_1.png)

```
g = sns.PairGrid(iris,hue="species",vars=["sepal_length","sepal_width"])
g.map(plt.scatter)
<seaborn.axisgrid.PairGrid at 0x1a24382550>
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-17-FacetGrid%E4%BD%BF%E7%94%A8%E6%96%B9%E6%B3%95%E5%8F%8A%E7%BB%98%E5%88%B6%E5%A4%9A%E5%8F%98%E9%87%8F%E2%80%9D/output_13_1.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-17-FacetGrid使用方法及绘制多变量”/output_13_1.png)

```
g = sns.PairGrid(tips,hue="size",palette="GnBu_d")
g.map(plt.scatter,s=50,edgecolor="white")
g.add_legend()
<seaborn.axisgrid.PairGrid at 0x1a26982c88>
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-17-FacetGrid%E4%BD%BF%E7%94%A8%E6%96%B9%E6%B3%95%E5%8F%8A%E7%BB%98%E5%88%B6%E5%A4%9A%E5%8F%98%E9%87%8F%E2%80%9D/output_14_1.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-17-FacetGrid使用方法及绘制多变量”/output_14_1.png)

[# seaborn](https://www.cishao.cn/tags/seaborn/)
