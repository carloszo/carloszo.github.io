---
title: python数据分析与机器学习实战-13.调色板及颜色设置
date: 2018-12-07 
categories: python
permalink: 
tags: 数据分析 
---

```
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
import numpy as np
%matplotlib inline
sns.set(rc={'figure.figsize':(6,6)})
```



```
current_palette = sns.color_palette()
sns.palplot(current_palette)
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-13-%E8%B0%83%E8%89%B2%E6%9D%BF%E5%8F%8A%E9%A2%9C%E8%89%B2%E8%AE%BE%E7%BD%AE%E2%80%9D/output_1_0.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-13-调色板及颜色设置”/output_1_0.png)

```
sns.palplot(sns.color_palette("hls",8))
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-13-%E8%B0%83%E8%89%B2%E6%9D%BF%E5%8F%8A%E9%A2%9C%E8%89%B2%E8%AE%BE%E7%BD%AE%E2%80%9D/output_2_0.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-13-调色板及颜色设置”/output_2_0.png)

```
data = np.random.normal(size=(20,6))+np.arange(6)/2
sns.boxplot(data=data,palette=sns.color_palette("hls",8))
<matplotlib.axes._subplots.AxesSubplot at 0x1a2397bc18>
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-13-%E8%B0%83%E8%89%B2%E6%9D%BF%E5%8F%8A%E9%A2%9C%E8%89%B2%E8%AE%BE%E7%BD%AE%E2%80%9D/output_3_1.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-13-调色板及颜色设置”/output_3_1.png)

```
#sns.palplot(sns.hls_palette(8,l=5,s=9))
```

sns.palplot(sns.color_palette(“Paired”,20))

```
sns.palplot(sns.color_palette("Blues"))
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-13-%E8%B0%83%E8%89%B2%E6%9D%BF%E5%8F%8A%E9%A2%9C%E8%89%B2%E8%AE%BE%E7%BD%AE%E2%80%9D/output_6_0.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-13-调色板及颜色设置”/output_6_0.png)

```
sns.palplot(sns.color_palette("BuGn_r"))
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-13-%E8%B0%83%E8%89%B2%E6%9D%BF%E5%8F%8A%E9%A2%9C%E8%89%B2%E8%AE%BE%E7%BD%AE%E2%80%9D/output_7_0.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-13-调色板及颜色设置”/output_7_0.png)

```
#线性调色板
sns.palplot(sns.color_palette("cubehelix",8))
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-13-%E8%B0%83%E8%89%B2%E6%9D%BF%E5%8F%8A%E9%A2%9C%E8%89%B2%E8%AE%BE%E7%BD%AE%E2%80%9D/output_8_0.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-13-调色板及颜色设置”/output_8_0.png)

```
sns.palplot(sns.light_palette("green"))
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-13-%E8%B0%83%E8%89%B2%E6%9D%BF%E5%8F%8A%E9%A2%9C%E8%89%B2%E8%AE%BE%E7%BD%AE%E2%80%9D/output_9_0.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-13-调色板及颜色设置”/output_9_0.png)

```
sns.palplot(sns.dark_palette("green"))
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-13-%E8%B0%83%E8%89%B2%E6%9D%BF%E5%8F%8A%E9%A2%9C%E8%89%B2%E8%AE%BE%E7%BD%AE%E2%80%9D/output_10_0.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-13-调色板及颜色设置”/output_10_0.png)

```
#由深到浅
sns.palplot(sns.light_palette("green",reverse=True))
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-13-%E8%B0%83%E8%89%B2%E6%9D%BF%E5%8F%8A%E9%A2%9C%E8%89%B2%E8%AE%BE%E7%BD%AE%E2%80%9D/output_11_0.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-13-调色板及颜色设置”/output_11_0.png)

```
x,y=np.random.multivariate_normal([0,0],[[1,-0.5],[-0.5,1]],size=300).T
pal = sns.dark_palette("green",as_cmap=True)
sns.kdeplot(x,y,cmap=pal)
<matplotlib.axes._subplots.AxesSubplot at 0x1a25409eb8>
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-13-%E8%B0%83%E8%89%B2%E6%9D%BF%E5%8F%8A%E9%A2%9C%E8%89%B2%E8%AE%BE%E7%BD%AE%E2%80%9D/output_12_1.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-13-调色板及颜色设置”/output_12_1.png)

[# seaborn](https://www.cishao.cn/tags/seaborn/)
