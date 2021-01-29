---
title: python数据分析与机器学习实战-10.子图
date: 2018-12-07 
categories: python
permalink: 
tags: 数据分析 
---

```
import pandas as pd
import matplotlib.pyplot as plt
fig = plt.figure()
ax1 = fig.add_subplot(2,2,1)
ax2 = fig.add_subplot(2,2,2)
ax3 = fig.add_subplot(2,2,4)
plt.show()
```



[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-10-%E5%AD%90%E5%9B%BE%E2%80%9D/output_0_0.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-10-子图”/output_0_0.png)

```
import numpy as np
fig = plt.figure(figsize=(10,10))
ax1 = fig.add_subplot(2,2,1)
ax2 = fig.add_subplot(2,2,2)
fig.show()
/anaconda3/lib/python3.6/site-packages/matplotlib/figure.py:459: UserWarning: matplotlib is currently using a non-GUI backend, so cannot show the figure
  "matplotlib is currently using a non-GUI backend, "
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-10-%E5%AD%90%E5%9B%BE%E2%80%9D/output_1_1.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-10-子图”/output_1_1.png)

[# matplotlib](https://www.cishao.cn/tags/matplotlib/)