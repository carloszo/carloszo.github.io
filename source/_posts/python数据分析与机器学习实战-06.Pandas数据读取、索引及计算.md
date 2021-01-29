---
title: python数据分析与机器学习实战-06.Pandas数据读取、索引及计算
date: 2018-12-07 
categories: python
permalink: 
tags: 数据分析 
---

```
import pandas
java_list = pandas.read_excel('java_list.xlsx')
print(java_list.dtypes)
```



```
姓名              object
工作经历1公司(可筛选)    object
工作经历1职位（可筛选）    object
手机              object
邮箱              object
工作经历2公司         object
工作经历2职位         object
工作经历3公司         object
工作经历3职位         object
城市              object
教育经历1学校         object
Unnamed: 11     object
Unnamed: 12     object
dtype: object
#head()显示前几条数据，括号中数字表示前几条，为空时默认显示前5条
print(java_list.head(3))
    姓名    工作经历1公司(可筛选) 工作经历1职位（可筛选）           手机                 邮箱  \
0  王文鹏              绿岸      移动前端架构师  18918297081                NaN   
1   徐昱  快钱(南京)信息技术有限公司       iOS工程师  18362957281  3062037039@qq.com   
2  颜建光     十九楼网络股份有限公司    java软件工程师  13388616582                NaN   

        工作经历2公司  工作经历2职位          工作经历3公司      工作经历3职位  城市 教育经历1学校  \
0           NaN      NaN              NaN          NaN  上海     NaN   
1  南京大悦网络科技有限公司  iOS项目主管  南京富士通南大软件技术有限公司  java研发实习工程师  江苏  南京邮电大学   
2    杭州顺网股份有限公司     项目经理    浙江鸿程计算机系统有限公司         项目管理  浙江  浙江工业大学   

  Unnamed: 11 Unnamed: 12  
0      天津工业大学         NaN  
1      浙江万里学院         NaN  
2   在东忠人才培训中心      浙江工业大学  
#tail()表示显示尾几行
print(java_list.tail(2))
      姓名 工作经历1公司(可筛选) 工作经历1职位（可筛选）           手机                      邮箱  \
746   张欣    北京中科软有限公司  java软件开发工程师  15010055938  zhangxinys@outlook.com   
747  刘金鑫  北京今胜昔科技有限公司      java工程师  13521214507          yydljx@126.com   

           工作经历2公司      工作经历2职位 工作经历3公司 工作经历3职位  城市      教育经历1学校 Unnamed: 11  \
746            NaN          NaN     NaN     NaN  北京       华北电力大学         NaN   
747  石家庄优品捷思科技有限公司  JavaEE软件工程师     NaN     NaN  北京  石家庄经济学院华信学院         NaN   

    Unnamed: 12  
746         NaN  
747         NaN  
#columns 列名
print(java_list.columns)
Index(['姓名', '工作经历1公司(可筛选)', '工作经历1职位（可筛选）', '手机', '邮箱', '工作经历2公司', '工作经历2职位',
       '工作经历3公司', '工作经历3职位', '城市', '教育经历1学校', 'Unnamed: 11', 'Unnamed: 12'],
      dtype='object')
#shape类似numpy中,表示多少行和列
print(java_list.shape)
(748, 13)
#索引
#loc[num]
java_list.loc[1]
姓名                             徐昱
工作经历1公司(可筛选)       快钱(南京)信息技术有限公司
工作经历1职位（可筛选）               iOS工程师
手机                    18362957281
邮箱              3062037039@qq.com
工作经历2公司              南京大悦网络科技有限公司
工作经历2职位                   iOS项目主管
工作经历3公司           南京富士通南大软件技术有限公司
工作经历3职位               java研发实习工程师
城市                             江苏
教育经历1学校                    南京邮电大学
Unnamed: 11                浙江万里学院
Unnamed: 12                   NaN
Name: 1, dtype: object
#loc[num1:num2]数据切片
print(java_list.loc[0:2])
    姓名    工作经历1公司(可筛选) 工作经历1职位（可筛选）           手机                 邮箱  \
0  王文鹏              绿岸      移动前端架构师  18918297081                NaN   
1   徐昱  快钱(南京)信息技术有限公司       iOS工程师  18362957281  3062037039@qq.com   
2  颜建光     十九楼网络股份有限公司    java软件工程师  13388616582                NaN   

        工作经历2公司  工作经历2职位          工作经历3公司      工作经历3职位  城市 教育经历1学校  \
0           NaN      NaN              NaN          NaN  上海     NaN   
1  南京大悦网络科技有限公司  iOS项目主管  南京富士通南大软件技术有限公司  java研发实习工程师  江苏  南京邮电大学   
2    杭州顺网股份有限公司     项目经理    浙江鸿程计算机系统有限公司         项目管理  浙江  浙江工业大学   

  Unnamed: 11 Unnamed: 12  
0      天津工业大学         NaN  
1      浙江万里学院         NaN  
2   在东忠人才培训中心      浙江工业大学  
#loc[[num1,num2,...]]取任意值
print(java_list.loc[[2,5]])
    姓名 工作经历1公司(可筛选) 工作经历1职位（可筛选）           手机   邮箱     工作经历2公司 工作经历2职位  \
2  颜建光  十九楼网络股份有限公司    java软件工程师  13388616582  NaN  杭州顺网股份有限公司    项目经理   
5  胡恒超          拉卡拉      java工程师  18601730860  NaN         NaN     NaN   

         工作经历3公司 工作经历3职位  城市 教育经历1学校 Unnamed: 11 Unnamed: 12  
2  浙江鸿程计算机系统有限公司    项目管理  浙江  浙江工业大学   在东忠人才培训中心      浙江工业大学  
5            NaN     NaN  上海     NaN         NaN         NaN  
#按列名索引数据
print(java_list["姓名"])
0       王文鹏
1        徐昱
2       颜建光
3       叶先生
4       高金涛
5       胡恒超
6        吴欣
7        朱建
8       黄首文
9       詹先生
10       谢辉
11      苗向彬
12      张海波
13      荣卫剑
14      张尔宁
15       张茜
16       徐磊
17       程丁
18      李锦华
19       张磊
20      孔先生
21      罗先生
22      李海彬
23       汪斌
24      赵纪亮
25      李佩龙
26       杨超
27      张庆涛
28      候兆森
29      吴明亮
       ... 
718      严岩
719     李金鹏
720      孙博
721      赵阳
722     蒋建军
723     段开元
724      冯威
725      孟超
726    Rose
727      姜哲
728      王东
729     黄生波
730      刘磊
731     张巧军
732     徐晓伟
733     温晓冰
734     汪喜路
735     佟学强
736     刘文超
737     刘银龙
738     马双辉
739     余永刚
740      郑毅
741     汪荣轩
742      王飞
743     钱新刚
744     陈志成
745     张晓强
746      张欣
747     刘金鑫
Name: 姓名, Length: 748, dtype: object
#索引多个列
#print(java_list[["姓名","手机"]])
#获取列名并转化为list
col_names = java_list.columns.tolist()
print(col_names)
new_list = []
for col in col_names:
    if col.endswith("(可筛选)"):
        new_list.append(col)
job_df = java_list[new_list]
print(job_df.head())
['姓名', '工作经历1公司(可筛选)', '工作经历1职位（可筛选）', '手机', '邮箱', '工作经历2公司', '工作经历2职位', '工作经历3公司', '工作经历3职位', '城市', '教育经历1学校', 'Unnamed: 11', 'Unnamed: 12']
     工作经历1公司(可筛选)
0              绿岸
1  快钱(南京)信息技术有限公司
2     十九楼网络股份有限公司
3              软件
4    杉德巍康企业服务有限公司
```