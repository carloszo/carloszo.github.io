---
title: Count and say 
date: 
categories: python
permalink: 
tags: leetcode 
---


The count-and-say sequence is the sequence of integers with the first five terms as following:

1. 1
2. 11
3. 21
4. 1211
5. 111221
   1 is read off as “one 1” or 11.
   11 is read off as “two 1s” or 21.
   21 is read off as “one 2, then one 1” or 1211. Given an integer n where 1 ≤ n ≤ 30, generate the nth term of the count-and-say sequence.

Note: Each term of the sequence of integers will be represented as a string.

```python
def countAndSay(n):
        """
        :type n: int
        :rtype: str
        """
        oldstr='1'
        for i in range(n-1):
            tmp=''
            count=1
            for j in range(1,len(oldstr)+1):
                if j< len(oldstr) and oldstr[j]==oldstr[j-1]:
                    count+=1
                else:
                    tmp += str(count)+oldstr[j-1]
                    count = 1
            oldstr = tmp   
        return oldstr
```
