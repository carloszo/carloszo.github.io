---
title: python数据分析与机器学习实战-18.热力图绘制
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
%matplotlib inline
```



```
data = np.random.rand(3,3)
print(data)
heatmap = sns.heatmap(data)
[[0.79738421 0.16230573 0.06197724]
 [0.79989397 0.73146068 0.17731879]
 [0.26202278 0.78645707 0.26536331]]





<matplotlib.axes._subplots.AxesSubplot at 0x10d042a90>
```

[![png](https://www.cishao.cn/2018/12/08/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-18-%E7%83%AD%E5%8A%9B%E5%9B%BE%E7%BB%98%E5%88%B6%E2%80%9D/output_1_2.png)](https://www.cishao.cn/2018/12/08/“python数据分析与机器学习实战-18-热力图绘制”/output_1_2.png)

```
#设置数据最小值到最大值界限
ax =  sns.heatmap(data,vmin=0.1,vmax=0.5)
```

[![png](https://www.cishao.cn/2018/12/08/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-18-%E7%83%AD%E5%8A%9B%E5%9B%BE%E7%BB%98%E5%88%B6%E2%80%9D/output_2_0.png)](https://www.cishao.cn/2018/12/08/“python数据分析与机器学习实战-18-热力图绘制”/output_2_0.png)

```
#当数据有正负时，可以指定以0为中心
data = np.random.randn(3,3)
print(data)
ax = sns.heatmap(data,center=0)
[[ 0.65257565 -0.38550847  0.55620784]
 [ 0.28429021 -1.68905002 -0.29115511]
 [-1.09649997 -0.81622564  0.47706824]]
```

[![png](https://www.cishao.cn/2018/12/08/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-18-%E7%83%AD%E5%8A%9B%E5%9B%BE%E7%BB%98%E5%88%B6%E2%80%9D/output_3_1.png)](https://www.cishao.cn/2018/12/08/“python数据分析与机器学习实战-18-热力图绘制”/output_3_1.png)

```
flights = sns.load_dataset("flights")
flights.head()
```













































|      | year | month    | passengers |
| :--- | :--- | :------- | :--------- |
| 0    | 1949 | January  | 112        |
| 1    | 1949 | February | 118        |
| 2    | 1949 | March    | 132        |
| 3    | 1949 | April    | 129        |
| 4    | 1949 | May      | 121        |



```
#数据转换
flights = flights.pivot("month","year","passengers")
#热力图
sns.heatmap(flights)
<matplotlib.axes._subplots.AxesSubplot at 0x1a1a0a5ac8>
```

[![png](https://www.cishao.cn/2018/12/08/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-18-%E7%83%AD%E5%8A%9B%E5%9B%BE%E7%BB%98%E5%88%B6%E2%80%9D/output_5_1.png)](https://www.cishao.cn/2018/12/08/“python数据分析与机器学习实战-18-热力图绘制”/output_5_1.png)

```
#将数据显示在heatmap中，annot=True,将fmt的值设置为'd',否则数据会出现乱码。
ax = sns.heatmap(flights,annot=True,fmt='d')
```

[![png](https://www.cishao.cn/2018/12/08/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-18-%E7%83%AD%E5%8A%9B%E5%9B%BE%E7%BB%98%E5%88%B6%E2%80%9D/output_6_0.png)](https://www.cishao.cn/2018/12/08/“python数据分析与机器学习实战-18-热力图绘制”/output_6_0.png)

```
#heatmap格与格之间增加间隙
ax = sns.heatmap(flights,linewidth=0.5)
```

[![png](https://www.cishao.cn/2018/12/08/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-18-%E7%83%AD%E5%8A%9B%E5%9B%BE%E7%BB%98%E5%88%B6%E2%80%9D/output_7_0.png)](https://www.cishao.cn/2018/12/08/“python数据分析与机器学习实战-18-热力图绘制”/output_7_0.png)

```
#设置自定义颜色
ax = sns.heatmap(flights,linewidth=0.5,cmap="YlGnBu")
```

[![png](https://www.cishao.cn/2018/12/08/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-18-%E7%83%AD%E5%8A%9B%E5%9B%BE%E7%BB%98%E5%88%B6%E2%80%9D/output_8_0.png)](https://www.cishao.cn/2018/12/08/“python数据分析与机器学习实战-18-热力图绘制”/output_8_0.png)

[# seaborn](https://www.cishao.cn/tags/seaborn/) [# heatmap](https://www.cishao.cn/tags/heatmap/)
