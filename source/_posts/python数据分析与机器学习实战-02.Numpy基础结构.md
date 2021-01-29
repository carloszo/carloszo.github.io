---
title: python数据分析与机器学习实战-02.Numpy基础结构
date: 2018-12-07 
categories: python
permalink: 
tags: 数据分析 
---

```
import numpy
#数据运算
vector = numpy.array([3,6,7,89,90])
vector == 6
```

```
array([False,  True, False, False, False])
```

```
matrix = numpy.array([[12,3,67,9],[34,2,7,9],[3,8,9,6]])matrix == 3
```

```
array([[False,  True, False, False],
       [False, False, False, False],
       [ True, False, False, False]])
```

```
vector = numpy.array([3,6,7,89,90])
equal_to_six = (vector == 6)
print(equal_to_six)
print(vector[equal_to_six])
```

```
[False  True False False False]
[6]
```

```
matrix = numpy.array([[12,3,67,9],[34,2,7,9],[3,8,9,6]])
second_column_three = (matrix[:,1] == 3)
print(second_column_three)
print(matrix[second_column_three,:])
```

```
[ True False False]
[[12  3 67  9]]
```

```
#逻辑运算
vector = numpy.array([3,6,7,89,90])
equal_to_three_and_six = (vector == 3)&(vector == 6)
print(equal_to_three_and_six)
```

```
[False False False False False]
```

```
vector = numpy.array([3,6,7,89,90])
equal_to_three_or_six = (vector == 3)|(vector == 6)
print(equal_to_three_or_six)
```

```
[ True  True False False False]
```

```
#类型转换vector = numpy.array(['3','6','7','89','90'])print(vector.dtype)vector = vector.astype(float)print(vector.dtype)print(vector)
```

```
<U2
float64
[ 3.  6.  7. 89. 90.]
```

```
#最小值
vector = numpy.array([3,6,7,89,90])
print(vector.min())
```

```
#最大值
vector = numpy.array([3,6,7,89,90])
print(vector.max())
```

```
#列求和
matrix = numpy.array([[12,3,67,9],[34,2,7,9],[3,8,9,6]])
print(matrix.sum(axis=0))
```

```
[49 13 83 24]
```

```
#行求和
matrix = numpy.array([[12,3,67,9],[34,2,7,9],[3,8,9,6]])
print(matrix.sum(axis=1))
```

```
[91 52 26]
```