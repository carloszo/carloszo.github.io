---
title: python数据分析与机器学习实战-05.矩阵常用操作
date: 2018-12-07 
categories: python
permalink: 
tags: 数据分析 
---

```
import numpy as np
data = np.random.random((5,4))
print(data)
#求列最大数索引位置，axis=0表示列，为1表示行
ind = data.argmax(axis=0)
print(ind)
#获得最大数
data_max = data[ind,range(data.shape[1])]
print(data_max)
```



```
[[0.66992313 0.38898046 0.85090475 0.75138018]
 [0.5712647  0.34303314 0.45904951 0.35832093]
 [0.64563436 0.55838443 0.82634614 0.99323808]
 [0.67713092 0.64573979 0.26588219 0.73057923]
 [0.43273003 0.84170913 0.98372659 0.22579551]]
[3 4 4 2]
[0.67713092 0.84170913 0.98372659 0.99323808]
#扩展矩阵
a = np.arange(0,40,10)
print(a)
b = np.tile(a,(2,2))
print(b)
[ 0 10 20 30]
[[ 0 10 20 30  0 10 20 30]
 [ 0 10 20 30  0 10 20 30]]
#排序
a = np.array([[3,5,1],[9,2,5]])
print(a)
b = np.sort(a,axis=1)
print(b)
[[3 5 1]
 [9 2 5]]
[[1 3 5]
 [2 5 9]]
a = np.array([4,2,1,3])
print(a)
#argsort可获取向量从小到大对应的指数
c = np.argsort(a)
print("------")
print(c)
print("------")
#获取排序
print(a[c])
[4 2 1 3]
------
[2 1 3 0]
------
[1 2 3 4]
0
```