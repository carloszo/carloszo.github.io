---
title: python数据分析与机器学习实战-15.回归分析绘图
date: 2018-12-07 
categories: python
permalink: 
tags: 数据分析 
---


```
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import matplotlib as mpl
import seaborn as sns

sns.set(color_codes=True)

np.random.seed(sum(map(ord,"regression")))
tips = sns.load_dataset("tips")
tips.head()
```







































































|      | total_bill |  tip |    sex | smoker |  day |   time | size |
| :--- | ---------: | ---: | -----: | -----: | ---: | -----: | ---: |
| 0    |      16.99 | 1.01 | Female |     No |  Sun | Dinner |    2 |
| 1    |      10.34 | 1.66 |   Male |     No |  Sun | Dinner |    3 |
| 2    |      21.01 | 3.50 |   Male |     No |  Sun | Dinner |    3 |
| 3    |      23.68 | 3.31 |   Male |     No |  Sun | Dinner |    2 |
| 4    |      24.59 | 3.61 | Female |     No |  Sun | Dinner |    4 |

regplot()和lmplot()都可以绘制回归关系，推荐使用regplot()

```
sns.regplot(x = "total_bill",y="tip",data=tips)
<matplotlib.axes._subplots.AxesSubplot at 0x1a17cb5668>
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-15-%E5%9B%9E%E5%BD%92%E5%88%86%E6%9E%90%E7%BB%98%E5%9B%BE%E2%80%9D/output_2_1.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-15-回归分析绘图”/output_2_1.png)

```
sns.regplot(data=tips,x="size",y="tip")
<matplotlib.axes._subplots.AxesSubplot at 0x1a17bf8ac8>
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-15-%E5%9B%9E%E5%BD%92%E5%88%86%E6%9E%90%E7%BB%98%E5%9B%BE%E2%80%9D/output_3_1.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-15-回归分析绘图”/output_3_1.png)

```
sns.regplot(data=tips,x="size",y="tip",x_jitter=0.05)
<matplotlib.axes._subplots.AxesSubplot at 0x1a17e29b70>
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-15-%E5%9B%9E%E5%BD%92%E5%88%86%E6%9E%90%E7%BB%98%E5%9B%BE%E2%80%9D/output_4_1.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-15-回归分析绘图”/output_4_1.png)

[# seaborn](https://www.cishao.cn/tags/seaborn/)
