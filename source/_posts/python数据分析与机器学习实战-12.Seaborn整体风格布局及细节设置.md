---
title: python数据分析与机器学习实战-12.Seaborn整体风格布局及细节设置
date: 2018-12-07 
categories: python
permalink: 
tags: 数据分析 
---


```
import seaborn as sns
import numpy as np
import matplotlib as mpl
import matplotlib.pyplot as plt
%matplotlib inline
```



```
def sinplot(flip=1):
    x=np.linspace(0,14,100)
    for i in range(1,7):
        plt.plot(x,np.sin(x+i*0.5)*(7-i)*flip)
sinplot()
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-12-Seaborn%E6%95%B4%E4%BD%93%E9%A3%8E%E6%A0%BC%E5%B8%83%E5%B1%80%E5%8F%8A%E7%BB%86%E8%8A%82%E8%AE%BE%E7%BD%AE%E2%80%9D/output_2_0.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-12-Seaborn整体风格布局及细节设置”/output_2_0.png)

```
sns.set()
sinplot()
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-12-Seaborn%E6%95%B4%E4%BD%93%E9%A3%8E%E6%A0%BC%E5%B8%83%E5%B1%80%E5%8F%8A%E7%BB%86%E8%8A%82%E8%AE%BE%E7%BD%AE%E2%80%9D/output_3_0.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-12-Seaborn整体风格布局及细节设置”/output_3_0.png)

```
sns.set_style("ticks")
data = np.random.normal(size=(20,6))+np.arange(6)/2
sns.boxplot(data=data)
<matplotlib.axes._subplots.AxesSubplot at 0x1a1d097668>
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-12-Seaborn%E6%95%B4%E4%BD%93%E9%A3%8E%E6%A0%BC%E5%B8%83%E5%B1%80%E5%8F%8A%E7%BB%86%E8%8A%82%E8%AE%BE%E7%BD%AE%E2%80%9D/output_4_1.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-12-Seaborn整体风格布局及细节设置”/output_4_1.png)

```
sns.set_style("white")
sinplot()
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-12-Seaborn%E6%95%B4%E4%BD%93%E9%A3%8E%E6%A0%BC%E5%B8%83%E5%B1%80%E5%8F%8A%E7%BB%86%E8%8A%82%E8%AE%BE%E7%BD%AE%E2%80%9D/output_5_0.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-12-Seaborn整体风格布局及细节设置”/output_5_0.png)

```
sinplot()
sns.despine()
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-12-Seaborn%E6%95%B4%E4%BD%93%E9%A3%8E%E6%A0%BC%E5%B8%83%E5%B1%80%E5%8F%8A%E7%BB%86%E8%8A%82%E8%AE%BE%E7%BD%AE%E2%80%9D/output_6_0.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-12-Seaborn整体风格布局及细节设置”/output_6_0.png)

```
sns.violinplot(data)
sns.despine(offset=10)
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-12-Seaborn%E6%95%B4%E4%BD%93%E9%A3%8E%E6%A0%BC%E5%B8%83%E5%B1%80%E5%8F%8A%E7%BB%86%E8%8A%82%E8%AE%BE%E7%BD%AE%E2%80%9D/output_7_0.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-12-Seaborn整体风格布局及细节设置”/output_7_0.png)

```
with sns.axes_style("darkgrid"):
    plt.subplot(2,1,1)
    sinplot()
plt.subplot(2,1,2)
sinplot(-1)
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-12-Seaborn%E6%95%B4%E4%BD%93%E9%A3%8E%E6%A0%BC%E5%B8%83%E5%B1%80%E5%8F%8A%E7%BB%86%E8%8A%82%E8%AE%BE%E7%BD%AE%E2%80%9D/output_8_0.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-12-Seaborn整体风格布局及细节设置”/output_8_0.png)

```
sns.set()
sns.set_context("paper")
plt.figure(figsize=(8,6))
sinplot()
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-12-Seaborn%E6%95%B4%E4%BD%93%E9%A3%8E%E6%A0%BC%E5%B8%83%E5%B1%80%E5%8F%8A%E7%BB%86%E8%8A%82%E8%AE%BE%E7%BD%AE%E2%80%9D/output_10_0.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-12-Seaborn整体风格布局及细节设置”/output_10_0.png)

```
sns.set_context("talk")
plt.figure(figsize=(8,6))
sinplot()
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-12-Seaborn%E6%95%B4%E4%BD%93%E9%A3%8E%E6%A0%BC%E5%B8%83%E5%B1%80%E5%8F%8A%E7%BB%86%E8%8A%82%E8%AE%BE%E7%BD%AE%E2%80%9D/output_11_0.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-12-Seaborn整体风格布局及细节设置”/output_11_0.png)

```
sns.set_context("poster")
plt.figure(figsize=(8,6))
sinplot()
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-12-Seaborn%E6%95%B4%E4%BD%93%E9%A3%8E%E6%A0%BC%E5%B8%83%E5%B1%80%E5%8F%8A%E7%BB%86%E8%8A%82%E8%AE%BE%E7%BD%AE%E2%80%9D/output_12_0.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-12-Seaborn整体风格布局及细节设置”/output_12_0.png)

```
sns.set_context("notebook",font_scale=2.5,rc={'lines.linewidth':4.5})
plt.figure(figsize=(8,6))
sinplot()
```

[![png](https://www.cishao.cn/2018/12/07/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-12-Seaborn%E6%95%B4%E4%BD%93%E9%A3%8E%E6%A0%BC%E5%B8%83%E5%B1%80%E5%8F%8A%E7%BB%86%E8%8A%82%E8%AE%BE%E7%BD%AE%E2%80%9D/output_13_0.png)](https://www.cishao.cn/2018/12/07/“python数据分析与机器学习实战-12-Seaborn整体风格布局及细节设置”/output_13_0.png)

[# seaborn](https://www.cishao.cn/tags/seaborn/)
