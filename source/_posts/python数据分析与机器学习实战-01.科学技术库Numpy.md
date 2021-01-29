---
title: python数据分析与机器学习实战-01.科学技术库Numpy
date: 2018-12-07 
categories: python
permalink: 
tags: 数据分析 
---

```python
import numpy
#从文件中读取数据到numpy
data = numpy.genfromtxt('/Users/apple/PycharmProjects/Carlos_python/data_science/downloadlist.txt',delimiter='',dtype='str')
print(type(data))
#print(help(numpy.genfromtxt))
#一维
vector = numpy.array([3,6,7,89,90])
#多维
matrix = numpy.array([[12,3,67,9],[34,2,7,9],[3,8,9,6]])
print(vector)
print(matrix)
#矩阵的结构
print(vector.shape)
print(matrix.shape)
```



```python
<class 'numpy.ndarray'>
[ 3  6  7 89 90]
[[12  3 67  9]
 [34  2  7  9]
 [ 3  8  9  6]]
(5,)
(3, 4)
#数据结构
numbers = numpy.array([1,2,3,4,5,6,7,8])
print(numbers)
print(numbers.dtype)
[1 2 3 4 5 6 7 8]
int64
#数据索引
matrix = numpy.array([[12,3,67,9],[34,2,7,9],[3,8,9,6]])
#第一行第一个数
print(matrix[0,0])
12
matrix = numpy.array([[12,3,67,9],[34,2,7,9],[3,8,9,6]])
#第三行最后一个数
print(matrix[2,-1])
6
#切片
vector = numpy.array([3,6,7,89,90])
print(vector[0:3])
[3 6 7]
matrix = numpy.array([[12,3,67,9],[34,2,7,9],[3,8,9,6]])
#所有行的第二个数
print(matrix[:,1])
[3 2 8]
# matrix = numpy.array([[12,3,67,9],[34,2,7,9],[3,8,9,6]])
#所有行的第一到二个数
print(matrix[:,0:2])
```