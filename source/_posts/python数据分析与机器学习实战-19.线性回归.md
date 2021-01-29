---
title: python数据分析与机器学习实战-19.线性回归
date: 2018-12-07 
categories: python
permalink: 
tags: 数据分析 
---

```
import matplotlib.pyplot as plt
import numpy as np
from sklearn import datasets
```



```
class LinearRegression():
    def __init__(self):
        self.w=None
    
    def fit(self,X,y):
        print(X.shape)
        X=np.insert(X,0,1,axis=1)
        print(X.shape)
        X_=np.linalg.inv(X.T.dot(X))
        self.w = X_.dot(X.T).dot(y)
    
    def predict(self,X):
        X=np.insert(X,0,1,axis=1)
        y_pred = X.dot(self.w)
        return y_pred

    def mean_squared_error(y_true,y_pred):
        mse = np.mean(np.power(y_true-y_pred,2))
        return mse
    
def main():
    diabetes = datasets.load_diabetes()
    X = diabetes.data[:,np.newaxis,2]
    print(X.shape)
    x_train,x_test = X[:-20],X[-20:]
    y_train,y_test = diabetes.target[:-20],diabetes.target[-20:]
        
    clf = LinearRegression()
    clf.fit(x_train,y_train)
    y_pred = clf.predict(x_test)
        
    plt.scatter(x_test[:,0],y_test,color='black')
    plt.plot(x_test[:,0],y_pred,color='blue',linewidth=3)
    plt.show()
main()
(442, 1)
(422, 1)
(422, 2)
```

[![png](https://www.cishao.cn/2018/12/11/%E2%80%9Cpython%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E4%B8%8E%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E5%AE%9E%E6%88%98-19-%E7%BA%BF%E6%80%A7%E5%9B%9E%E5%BD%92%E2%80%9D/output_2_1.png)](https://www.cishao.cn/2018/12/11/“python数据分析与机器学习实战-19-线性回归”/output_2_1.png)

[# 线性回归](https://www.cishao.cn/tags/线性回归/)
