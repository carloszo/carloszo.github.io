---
title: python数据分析与机器学习实战-08.Pandas自定义函数
date: 2018-12-07 
categories: python
permalink: 
tags: 数据分析 
---


```
import pandas as pd
import numpy as np
data =  pd.read_csv("train.csv")
age = data['Age']
#print(data.head())
#print(data['Age'])
#isnull()判断值是否为NaN
age_is_null = pd.isnull(age)
age_null_true = age[age_is_null]
#print(age_is_null)
#print(age_null_true)
print(len(age_null_true))
```



```
177
#缺失值处理
#求年龄平均值
good_ages = age[age_is_null==False]
#print(good_ages)
mean_age = sum(good_ages)/len(good_ages)
print(mean_age)

#另外一种求平均值方法
print(good_ages.mean())
29.69911764705882
29.69911764705882
#求不同船舱等级的票价平均值
fares_for_class = {}
Pclass = [1,2,3]
for unit in Pclass:
    pclass_rows = data[data['Pclass'] == unit]
    pclass_fares = pclass_rows['Fare']
    fare_for_class = pclass_fares.mean()
    fares_for_class[unit] = fare_for_class
    
print(fares_for_class)
{1: 84.15468749999992, 2: 20.66218315217391, 3: 13.675550101832997}
#用pivot_table求不同船舱获救平均比例
passager_survival = data.pivot_table(index="Pclass",values = "Survived",aggfunc = np.mean)
print(passager_survival)
        Survived
Pclass          
1       0.629630
2       0.472826
3       0.242363
#用pivot_table求不同船舱平均票价
mean_fares = data.pivot_table(index = "Pclass",values = "Fare",aggfunc = np.mean)
print(mean_fares)
             Fare
Pclass           
1       84.154687
2       20.662183
3       13.675550
#用pivot_table求不同等级船舱平均年龄
mean_ages = data.pivot_table(index = "Pclass",values = "Age",aggfunc = np.mean)
print(mean_ages.sort_values("Age"))
              Age
Pclass           
3       25.140620
2       29.877630
1       38.233441
#用pivot_table求不同登船点与船票和获救人数的关系
port_stat = data.pivot_table(index="Embarked",values = ["Fare","Survived"],aggfunc = np.sum)
print(port_stat)
                Fare  Survived
Embarked                      
C         10072.2962        93
Q          1022.2543        30
S         17439.3988       217
#dropna()
dropna_columns = data.dropna(axis=1)
new_data = data.dropna(axis=0,subset=["Age","Sex"])
new_data
```











































































































































































































































































































































































































































































































































































































































































































































































































































































































































































|      | PassengerId | Survived | Pclass | Name                                              | Sex    | Age  | SibSp | Parch | Ticket           | Fare     | Cabin       | Embarked |
| :--- | :---------- | :------- | :----- | :------------------------------------------------ | :----- | :--- | :---- | :---- | :--------------- | :------- | :---------- | :------- |
| 0    | 1           | 0        | 3      | Braund, Mr. Owen Harris                           | male   | 22.0 | 1     | 0     | A/5 21171        | 7.2500   | NaN         | S        |
| 1    | 2           | 1        | 1      | Cumings, Mrs. John Bradley (Florence Briggs Th…   | female | 38.0 | 1     | 0     | PC 17599         | 71.2833  | C85         | C        |
| 2    | 3           | 1        | 3      | Heikkinen, Miss. Laina                            | female | 26.0 | 0     | 0     | STON/O2. 3101282 | 7.9250   | NaN         | S        |
| 3    | 4           | 1        | 1      | Futrelle, Mrs. Jacques Heath (Lily May Peel)      | female | 35.0 | 1     | 0     | 113803           | 53.1000  | C123        | S        |
| 4    | 5           | 0        | 3      | Allen, Mr. William Henry                          | male   | 35.0 | 0     | 0     | 373450           | 8.0500   | NaN         | S        |
| 6    | 7           | 0        | 1      | McCarthy, Mr. Timothy J                           | male   | 54.0 | 0     | 0     | 17463            | 51.8625  | E46         | S        |
| 7    | 8           | 0        | 3      | Palsson, Master. Gosta Leonard                    | male   | 2.0  | 3     | 1     | 349909           | 21.0750  | NaN         | S        |
| 8    | 9           | 1        | 3      | Johnson, Mrs. Oscar W (Elisabeth Vilhelmina Berg) | female | 27.0 | 0     | 2     | 347742           | 11.1333  | NaN         | S        |
| 9    | 10          | 1        | 2      | Nasser, Mrs. Nicholas (Adele Achem)               | female | 14.0 | 1     | 0     | 237736           | 30.0708  | NaN         | C        |
| 10   | 11          | 1        | 3      | Sandstrom, Miss. Marguerite Rut                   | female | 4.0  | 1     | 1     | PP 9549          | 16.7000  | G6          | S        |
| 11   | 12          | 1        | 1      | Bonnell, Miss. Elizabeth                          | female | 58.0 | 0     | 0     | 113783           | 26.5500  | C103        | S        |
| 12   | 13          | 0        | 3      | Saundercock, Mr. William Henry                    | male   | 20.0 | 0     | 0     | A/5. 2151        | 8.0500   | NaN         | S        |
| 13   | 14          | 0        | 3      | Andersson, Mr. Anders Johan                       | male   | 39.0 | 1     | 5     | 347082           | 31.2750  | NaN         | S        |
| 14   | 15          | 0        | 3      | Vestrom, Miss. Hulda Amanda Adolfina              | female | 14.0 | 0     | 0     | 350406           | 7.8542   | NaN         | S        |
| 15   | 16          | 1        | 2      | Hewlett, Mrs. (Mary D Kingcome)                   | female | 55.0 | 0     | 0     | 248706           | 16.0000  | NaN         | S        |
| 16   | 17          | 0        | 3      | Rice, Master. Eugene                              | male   | 2.0  | 4     | 1     | 382652           | 29.1250  | NaN         | Q        |
| 18   | 19          | 0        | 3      | Vander Planke, Mrs. Julius (Emelia Maria Vande…   | female | 31.0 | 1     | 0     | 345763           | 18.0000  | NaN         | S        |
| 20   | 21          | 0        | 2      | Fynney, Mr. Joseph J                              | male   | 35.0 | 0     | 0     | 239865           | 26.0000  | NaN         | S        |
| 21   | 22          | 1        | 2      | Beesley, Mr. Lawrence                             | male   | 34.0 | 0     | 0     | 248698           | 13.0000  | D56         | S        |
| 22   | 23          | 1        | 3      | McGowan, Miss. Anna “Annie”                       | female | 15.0 | 0     | 0     | 330923           | 8.0292   | NaN         | Q        |
| 23   | 24          | 1        | 1      | Sloper, Mr. William Thompson                      | male   | 28.0 | 0     | 0     | 113788           | 35.5000  | A6          | S        |
| 24   | 25          | 0        | 3      | Palsson, Miss. Torborg Danira                     | female | 8.0  | 3     | 1     | 349909           | 21.0750  | NaN         | S        |
| 25   | 26          | 1        | 3      | Asplund, Mrs. Carl Oscar (Selma Augusta Emilia…   | female | 38.0 | 1     | 5     | 347077           | 31.3875  | NaN         | S        |
| 27   | 28          | 0        | 1      | Fortune, Mr. Charles Alexander                    | male   | 19.0 | 3     | 2     | 19950            | 263.0000 | C23 C25 C27 | S        |
| 30   | 31          | 0        | 1      | Uruchurtu, Don. Manuel E                          | male   | 40.0 | 0     | 0     | PC 17601         | 27.7208  | NaN         | C        |
| 33   | 34          | 0        | 2      | Wheadon, Mr. Edward H                             | male   | 66.0 | 0     | 0     | C.A. 24579       | 10.5000  | NaN         | S        |
| 34   | 35          | 0        | 1      | Meyer, Mr. Edgar Joseph                           | male   | 28.0 | 1     | 0     | PC 17604         | 82.1708  | NaN         | C        |
| 35   | 36          | 0        | 1      | Holverson, Mr. Alexander Oskar                    | male   | 42.0 | 1     | 0     | 113789           | 52.0000  | NaN         | S        |
| 37   | 38          | 0        | 3      | Cann, Mr. Ernest Charles                          | male   | 21.0 | 0     | 0     | A./5. 2152       | 8.0500   | NaN         | S        |
| 38   | 39          | 0        | 3      | Vander Planke, Miss. Augusta Maria                | female | 18.0 | 2     | 0     | 345764           | 18.0000  | NaN         | S        |
| …    | …           | …        | …      | …                                                 | …      | …    | …     | …     | …                | …        | …           | …        |
| 856  | 857         | 1        | 1      | Wick, Mrs. George Dennick (Mary Hitchcock)        | female | 45.0 | 1     | 1     | 36928            | 164.8667 | NaN         | S        |
| 857  | 858         | 1        | 1      | Daly, Mr. Peter Denis                             | male   | 51.0 | 0     | 0     | 113055           | 26.5500  | E17         | S        |
| 858  | 859         | 1        | 3      | Baclini, Mrs. Solomon (Latifa Qurban)             | female | 24.0 | 0     | 3     | 2666             | 19.2583  | NaN         | C        |
| 860  | 861         | 0        | 3      | Hansen, Mr. Claus Peter                           | male   | 41.0 | 2     | 0     | 350026           | 14.1083  | NaN         | S        |
| 861  | 862         | 0        | 2      | Giles, Mr. Frederick Edward                       | male   | 21.0 | 1     | 0     | 28134            | 11.5000  | NaN         | S        |
| 862  | 863         | 1        | 1      | Swift, Mrs. Frederick Joel (Margaret Welles Ba…   | female | 48.0 | 0     | 0     | 17466            | 25.9292  | D17         | S        |
| 864  | 865         | 0        | 2      | Gill, Mr. John William                            | male   | 24.0 | 0     | 0     | 233866           | 13.0000  | NaN         | S        |
| 865  | 866         | 1        | 2      | Bystrom, Mrs. (Karolina)                          | female | 42.0 | 0     | 0     | 236852           | 13.0000  | NaN         | S        |
| 866  | 867         | 1        | 2      | Duran y More, Miss. Asuncion                      | female | 27.0 | 1     | 0     | SC/PARIS 2149    | 13.8583  | NaN         | C        |
| 867  | 868         | 0        | 1      | Roebling, Mr. Washington Augustus II              | male   | 31.0 | 0     | 0     | PC 17590         | 50.4958  | A24         | S        |
| 869  | 870         | 1        | 3      | Johnson, Master. Harold Theodor                   | male   | 4.0  | 1     | 1     | 347742           | 11.1333  | NaN         | S        |
| 870  | 871         | 0        | 3      | Balkic, Mr. Cerin                                 | male   | 26.0 | 0     | 0     | 349248           | 7.8958   | NaN         | S        |
| 871  | 872         | 1        | 1      | Beckwith, Mrs. Richard Leonard (Sallie Monypeny)  | female | 47.0 | 1     | 1     | 11751            | 52.5542  | D35         | S        |
| 872  | 873         | 0        | 1      | Carlsson, Mr. Frans Olof                          | male   | 33.0 | 0     | 0     | 695              | 5.0000   | B51 B53 B55 | S        |
| 873  | 874         | 0        | 3      | Vander Cruyssen, Mr. Victor                       | male   | 47.0 | 0     | 0     | 345765           | 9.0000   | NaN         | S        |
| 874  | 875         | 1        | 2      | Abelson, Mrs. Samuel (Hannah Wizosky)             | female | 28.0 | 1     | 0     | P/PP 3381        | 24.0000  | NaN         | C        |
| 875  | 876         | 1        | 3      | Najib, Miss. Adele Kiamie “Jane”                  | female | 15.0 | 0     | 0     | 2667             | 7.2250   | NaN         | C        |
| 876  | 877         | 0        | 3      | Gustafsson, Mr. Alfred Ossian                     | male   | 20.0 | 0     | 0     | 7534             | 9.8458   | NaN         | S        |
| 877  | 878         | 0        | 3      | Petroff, Mr. Nedelio                              | male   | 19.0 | 0     | 0     | 349212           | 7.8958   | NaN         | S        |
| 879  | 880         | 1        | 1      | Potter, Mrs. Thomas Jr (Lily Alexenia Wilson)     | female | 56.0 | 0     | 1     | 11767            | 83.1583  | C50         | C        |
| 880  | 881         | 1        | 2      | Shelley, Mrs. William (Imanita Parrish Hall)      | female | 25.0 | 0     | 1     | 230433           | 26.0000  | NaN         | S        |
| 881  | 882         | 0        | 3      | Markun, Mr. Johann                                | male   | 33.0 | 0     | 0     | 349257           | 7.8958   | NaN         | S        |
| 882  | 883         | 0        | 3      | Dahlberg, Miss. Gerda Ulrika                      | female | 22.0 | 0     | 0     | 7552             | 10.5167  | NaN         | S        |
| 883  | 884         | 0        | 2      | Banfield, Mr. Frederick James                     | male   | 28.0 | 0     | 0     | C.A./SOTON 34068 | 10.5000  | NaN         | S        |
| 884  | 885         | 0        | 3      | Sutehall, Mr. Henry Jr                            | male   | 25.0 | 0     | 0     | SOTON/OQ 392076  | 7.0500   | NaN         | S        |
| 885  | 886         | 0        | 3      | Rice, Mrs. William (Margaret Norton)              | female | 39.0 | 0     | 5     | 382652           | 29.1250  | NaN         | Q        |
| 886  | 887         | 0        | 2      | Montvila, Rev. Juozas                             | male   | 27.0 | 0     | 0     | 211536           | 13.0000  | NaN         | S        |
| 887  | 888         | 1        | 1      | Graham, Miss. Margaret Edith                      | female | 19.0 | 0     | 0     | 112053           | 30.0000  | B42         | S        |
| 889  | 890         | 1        | 1      | Behr, Mr. Karl Howell                             | male   | 26.0 | 0     | 0     | 111369           | 30.0000  | C148        | C        |
| 890  | 891         | 0        | 3      | Dooley, Mr. Patrick                               | male   | 32.0 | 0     | 0     | 370376           | 7.7500   | NaN         | Q        |



714 rows × 12 columns



```
#通过行和列定位
data.loc[83,"Name"]
'Carrau, Mr. Francisco M'
#sort_values排序
new_data = data.sort_values('Age',ascending=False)
print(new_data[0:10])
print("------")
#对序号重新生成
new_reindexed = new_data.reset_index(drop=True)
print(new_reindexed[0:10])
     PassengerId  Survived  Pclass                                  Name  \
630          631         1       1  Barkworth, Mr. Algernon Henry Wilson   
851          852         0       3                   Svensson, Mr. Johan   
493          494         0       1               Artagaveytia, Mr. Ramon   
96            97         0       1             Goldschmidt, Mr. George B   
116          117         0       3                  Connors, Mr. Patrick   
672          673         0       2           Mitchell, Mr. Henry Michael   
745          746         0       1          Crosby, Capt. Edward Gifford   
33            34         0       2                 Wheadon, Mr. Edward H   
54            55         0       1        Ostby, Mr. Engelhart Cornelius   
280          281         0       3                      Duane, Mr. Frank   

      Sex   Age  SibSp  Parch      Ticket     Fare Cabin Embarked  
630  male  80.0      0      0       27042  30.0000   A23        S  
851  male  74.0      0      0      347060   7.7750   NaN        S  
493  male  71.0      0      0    PC 17609  49.5042   NaN        C  
96   male  71.0      0      0    PC 17754  34.6542    A5        C  
116  male  70.5      0      0      370369   7.7500   NaN        Q  
672  male  70.0      0      0  C.A. 24580  10.5000   NaN        S  
745  male  70.0      1      1   WE/P 5735  71.0000   B22        S  
33   male  66.0      0      0  C.A. 24579  10.5000   NaN        S  
54   male  65.0      0      1      113509  61.9792   B30        C  
280  male  65.0      0      0      336439   7.7500   NaN        Q  
------
   PassengerId  Survived  Pclass                                  Name   Sex  \
0          631         1       1  Barkworth, Mr. Algernon Henry Wilson  male   
1          852         0       3                   Svensson, Mr. Johan  male   
2          494         0       1               Artagaveytia, Mr. Ramon  male   
3           97         0       1             Goldschmidt, Mr. George B  male   
4          117         0       3                  Connors, Mr. Patrick  male   
5          673         0       2           Mitchell, Mr. Henry Michael  male   
6          746         0       1          Crosby, Capt. Edward Gifford  male   
7           34         0       2                 Wheadon, Mr. Edward H  male   
8           55         0       1        Ostby, Mr. Engelhart Cornelius  male   
9          281         0       3                      Duane, Mr. Frank  male   

    Age  SibSp  Parch      Ticket     Fare Cabin Embarked  
0  80.0      0      0       27042  30.0000   A23        S  
1  74.0      0      0      347060   7.7750   NaN        S  
2  71.0      0      0    PC 17609  49.5042   NaN        C  
3  71.0      0      0    PC 17754  34.6542    A5        C  
4  70.5      0      0      370369   7.7500   NaN        Q  
5  70.0      0      0  C.A. 24580  10.5000   NaN        S  
6  70.0      1      1   WE/P 5735  71.0000   B22        S  
7  66.0      0      0  C.A. 24579  10.5000   NaN        S  
8  65.0      0      1      113509  61.9792   B30        C  
9  65.0      0      0      336439   7.7500   NaN        Q  
# 结合apply()使用自定义函数
def hundredth_row(column):
    hundredth_item = column.loc[99]
    return hundredth_item

hundredth_row = data.apply(hundredth_row)
print(hundredth_row)
PassengerId                  100
Survived                       0
Pclass                         2
Name           Kantor, Mr. Sinai
Sex                         male
Age                           34
SibSp                          1
Parch                          0
Ticket                    244367
Fare                          26
Cabin                        NaN
Embarked                       S
dtype: object
def not_null_count(column):
    column_null = pd.isnull(column)
    null = column[column_null]
    return len(null)
not_null_counts = data.apply(not_null_count)
print(not_null_counts)
PassengerId      0
Survived         0
Pclass           0
Name             0
Sex              0
Age            177
SibSp            0
Parch            0
Ticket           0
Fare             0
Cabin          687
Embarked         2
dtype: int64
def which_class(row):
    pclass = row['Pclass']
    if pd.isnull(pclass):
        return "Unknow"
    if pclass == 1:
        return "一等舱"
    if pclass == 2:
        return "二等舱"
    if pclass == 3:
        return "三等舱"
    
pclass = data.apply(which_class,axis=1)
print(pclass)
0      三等舱
1      一等舱
2      三等舱
3      一等舱
4      三等舱
5      三等舱
6      一等舱
7      三等舱
8      三等舱
9      二等舱
10     三等舱
11     一等舱
12     三等舱
13     三等舱
14     三等舱
15     二等舱
16     三等舱
17     二等舱
18     三等舱
19     三等舱
20     二等舱
21     二等舱
22     三等舱
23     一等舱
24     三等舱
25     三等舱
26     三等舱
27     一等舱
28     三等舱
29     三等舱
      ... 
861    二等舱
862    一等舱
863    三等舱
864    二等舱
865    二等舱
866    二等舱
867    一等舱
868    三等舱
869    三等舱
870    三等舱
871    一等舱
872    一等舱
873    三等舱
874    二等舱
875    三等舱
876    三等舱
877    三等舱
878    三等舱
879    一等舱
880    二等舱
881    三等舱
882    三等舱
883    二等舱
884    三等舱
885    三等舱
886    二等舱
887    一等舱
888    三等舱
889    一等舱
890    三等舱
Length: 891, dtype: object
def generate_age_lable(row):
    age = row['Age']
    if pd.isnull(age):
        return "Unknown"
    elif age <18:
        return "未成年人"
    else:
        return "成年人"
    
age_lable = data.apply(generate_age_lable,axis = 1)
print(age_lable)
data['age_lable'] = age_lable
age_group_survival = data.pivot_table(index="age_lable", values = "Survived",aggfunc=np.mean)
print(age_group_survival)
0          成年人
1          成年人
2          成年人
3          成年人
4          成年人
5      Unknown
6          成年人
7         未成年人
8          成年人
9         未成年人
10        未成年人
11         成年人
12         成年人
13         成年人
14        未成年人
15         成年人
16        未成年人
17     Unknown
18         成年人
19     Unknown
20         成年人
21         成年人
22        未成年人
23         成年人
24        未成年人
25         成年人
26     Unknown
27         成年人
28     Unknown
29     Unknown
        ...   
861        成年人
862        成年人
863    Unknown
864        成年人
865        成年人
866        成年人
867        成年人
868    Unknown
869       未成年人
870        成年人
871        成年人
872        成年人
873        成年人
874        成年人
875       未成年人
876        成年人
877        成年人
878    Unknown
879        成年人
880        成年人
881        成年人
882        成年人
883        成年人
884        成年人
885        成年人
886        成年人
887        成年人
888    Unknown
889        成年人
890        成年人
Length: 891, dtype: object
           Survived
age_lable          
Unknown    0.293785
成年人        0.381032
未成年人       0.539823
# 性别与获救比例的关系
sex_survival = data.pivot_table(index = "Sex",values="Survived",aggfunc = np.mean)
print(sex_survival)
        Survived
Sex             
female  0.742038
male    0.188908
```
