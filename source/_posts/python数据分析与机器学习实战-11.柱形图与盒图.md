---
title: python数据分析与机器学习实战-11.柱形图与盒图
date: 2018-12-07 
categories: python
permalink: 
tags: 数据分析 
---


```
import pandas as pd
import numpy as np
data =  pd.read_excel("12sales.xlsx")
sales = data["TC12月销售目标"].head(46)
print(sales)
```



```
0      135000.0
1       70000.0
2      140000.0
3      121176.0
4     2100000.0
5      390000.0
6       30000.0
7      130000.0
8       83000.0
9      100000.0
10     120000.0
11      80000.0
12      90000.0
13     195000.0
14     315000.0
15     140000.0
16      20000.0
17     440940.0
18     310000.0
19     108666.0
20     183206.0
21     240000.0
22     270000.0
23      85000.0
24     357628.0
25     350000.0
26      75000.0
27     147600.0
28     133676.0
29     160000.0
30     280000.0
31      40000.0
32     170000.0
33     160000.0
34     180000.0
35     110000.0
36      50000.0
37     185000.0
38    1700000.0
39     410000.0
40     120000.0
41      90000.0
42     225000.0
43     180000.0
44     115000.0
45      65000.0
Name: TC12月销售目标, dtype: float64
import matplotlib.pyplot as plt
bar_height = sales.values
bar_weight = np.arange(46)
fig,ax = plt.subplots()
ax.bar(bar_weight,sales,0.75)
plt.title("target sales")
plt.show()
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-11-%E6%9F%B1%E5%BD%A2%E5%9B%BE%E4%B8%8E%E7%9B%92%E5%9B%BE%E2%80%9D/output_1_0.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-11-柱形图与盒图”/output_1_0.png)

```
#横着的树状图
bar_height = sales.values
bar_weight = np.arange(46)
fig,ax = plt.subplots()
ax.barh(bar_weight,bar_height,0.75)
plt.title("target sales")
plt.show()
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-11-%E6%9F%B1%E5%BD%A2%E5%9B%BE%E4%B8%8E%E7%9B%92%E5%9B%BE%E2%80%9D/output_2_0.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-11-柱形图与盒图”/output_2_0.png)

```
#散点图
bar_height = sales.values
bar_weight = np.arange(46)
fig,ax = plt.subplots()
ax.scatter(bar_weight,bar_height)
plt.title("target sales")
plt.show()
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-11-%E6%9F%B1%E5%BD%A2%E5%9B%BE%E4%B8%8E%E7%9B%92%E5%9B%BE%E2%80%9D/output_3_0.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-11-柱形图与盒图”/output_3_0.png)

```
import matplotlib.pyplot as plt
bar_height = sales.values
bar_weight = np.arange(46)
fig,ax = plt.subplots()
#ax.hist(sales)
ax.hist(bar_height,bins=20)
plt.title("target sales")
plt.show()
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-11-%E6%9F%B1%E5%BD%A2%E5%9B%BE%E4%B8%8E%E7%9B%92%E5%9B%BE%E2%80%9D/output_4_0.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-11-柱形图与盒图”/output_4_0.png)

```
fig,ax = plt.subplots()
ax.boxplot(sales)
ax.set_ylim(20000,100000)
plt.show()
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-11-%E6%9F%B1%E5%BD%A2%E5%9B%BE%E4%B8%8E%E7%9B%92%E5%9B%BE%E2%80%9D/output_5_0.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-11-柱形图与盒图”/output_5_0.png)

[# matplotlib](https://www.cishao.cn/tags/matplotlib/)
