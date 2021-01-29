---
title: python数据分析与机器学习实战-16.多变量分析绘图
date: 2018-12-07 
categories: python
permalink: 
tags: 数据分析 
---


```
import pandas as pd
import numpy as np
import matplotlib as mpl
import matplotlib.pyplot as plt
import seaborn as sns
sns.set(style = "whitegrid",color_codes=True)
```



```
tips = sns.load_dataset("tips")
iris = sns.load_dataset("iris")
titanic = sns.load_dataset("titanic")
sns.stripplot(x="day",y="total_bill",data=tips)
<matplotlib.axes._subplots.AxesSubplot at 0x10de58518>
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-16-%E5%A4%9A%E5%8F%98%E9%87%8F%E5%88%86%E6%9E%90%E7%BB%98%E5%9B%BE%E2%80%9D/output_1_1.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-16-多变量分析绘图”/output_1_1.png)

重叠很正常，但是影响观察数据量。

```
sns.stripplot(x="day",y="total_bill",data=tips,jitter=True)
<matplotlib.axes._subplots.AxesSubplot at 0x108208b00>
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-16-%E5%A4%9A%E5%8F%98%E9%87%8F%E5%88%86%E6%9E%90%E7%BB%98%E5%9B%BE%E2%80%9D/output_3_1.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-16-多变量分析绘图”/output_3_1.png)

```
sns.swarmplot(x="day",y="total_bill",data=tips)
<matplotlib.axes._subplots.AxesSubplot at 0x1a1ac1a7b8>
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-16-%E5%A4%9A%E5%8F%98%E9%87%8F%E5%88%86%E6%9E%90%E7%BB%98%E5%9B%BE%E2%80%9D/output_4_1.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-16-多变量分析绘图”/output_4_1.png)

```
sns.swarmplot(x="day",y="total_bill",hue="sex",data=tips)
<matplotlib.axes._subplots.AxesSubplot at 0x1a1ac68d30>
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-16-%E5%A4%9A%E5%8F%98%E9%87%8F%E5%88%86%E6%9E%90%E7%BB%98%E5%9B%BE%E2%80%9D/output_5_1.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-16-多变量分析绘图”/output_5_1.png)

```
sns.violinplot(x="total_bill",y="day",hue="time",data=tips)
<matplotlib.axes._subplots.AxesSubplot at 0x1a1ad26390>
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-16-%E5%A4%9A%E5%8F%98%E9%87%8F%E5%88%86%E6%9E%90%E7%BB%98%E5%9B%BE%E2%80%9D/output_6_1.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-16-多变量分析绘图”/output_6_1.png)

```
sns.violinplot(x="total_bill",y="day",hue="sex",data=tips,split=True)
<matplotlib.axes._subplots.AxesSubplot at 0x1a1af157b8>
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-16-%E5%A4%9A%E5%8F%98%E9%87%8F%E5%88%86%E6%9E%90%E7%BB%98%E5%9B%BE%E2%80%9D/output_7_1.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-16-多变量分析绘图”/output_7_1.png)

```
sns.violinplot(x="day",y="total_bill",data=tips,inner=None)
sns.swarmplot(x="day",y="total_bill",data=tips,color='w',alpha=0.5)
<matplotlib.axes._subplots.AxesSubplot at 0x1a1b4a4f60>
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-16-%E5%A4%9A%E5%8F%98%E9%87%8F%E5%88%86%E6%9E%90%E7%BB%98%E5%9B%BE%E2%80%9D/output_8_1.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-16-多变量分析绘图”/output_8_1.png)

```
titanic
sns.barplot(x="sex",y="survived",data=titanic,hue="class")
<matplotlib.axes._subplots.AxesSubplot at 0x1a1b7ba0b8>
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-16-%E5%A4%9A%E5%8F%98%E9%87%8F%E5%88%86%E6%9E%90%E7%BB%98%E5%9B%BE%E2%80%9D/output_9_1.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-16-多变量分析绘图”/output_9_1.png)

点图可以很好的描绘数据的差异

```
sns.pointplot(x="sex",y="survived",hue = "class",data=titanic)
<matplotlib.axes._subplots.AxesSubplot at 0x1a1b9f2860>
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-16-%E5%A4%9A%E5%8F%98%E9%87%8F%E5%88%86%E6%9E%90%E7%BB%98%E5%9B%BE%E2%80%9D/output_11_1.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-16-多变量分析绘图”/output_11_1.png)

```
#多层面板分类图
sns.factorplot(x="day",y="total_bill",hue="smoker",data=tips)
<seaborn.axisgrid.FacetGrid at 0x1a1b884d30>
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-16-%E5%A4%9A%E5%8F%98%E9%87%8F%E5%88%86%E6%9E%90%E7%BB%98%E5%9B%BE%E2%80%9D/output_12_1.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-16-多变量分析绘图”/output_12_1.png)

```
sns.factorplot(x="day",y="total_bill",hue="smoker",data=tips,kind="bar")
<seaborn.axisgrid.FacetGrid at 0x1a1bb5b710>
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-16-%E5%A4%9A%E5%8F%98%E9%87%8F%E5%88%86%E6%9E%90%E7%BB%98%E5%9B%BE%E2%80%9D/output_13_1.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-16-多变量分析绘图”/output_13_1.png)

```
sns.factorplot(x="day",y="total_bill",hue="smoker",data=tips,kind="swarm",col="time")
<seaborn.axisgrid.FacetGrid at 0x1a1be4dac8>
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-16-%E5%A4%9A%E5%8F%98%E9%87%8F%E5%88%86%E6%9E%90%E7%BB%98%E5%9B%BE%E2%80%9D/output_14_1.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-16-多变量分析绘图”/output_14_1.png)

```
sns.factorplot(x="day",y="total_bill",hue="smoker",data=tips,kind="box",col="day",size=4,aspect=0.5)
<seaborn.axisgrid.FacetGrid at 0x1a1c0a5588>
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-16-%E5%A4%9A%E5%8F%98%E9%87%8F%E5%88%86%E6%9E%90%E7%BB%98%E5%9B%BE%E2%80%9D/output_15_1.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-16-多变量分析绘图”/output_15_1.png)

[# seaborn](https://www.cishao.cn/tags/seaborn/)
