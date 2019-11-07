
Python3 基本数据类型

# 变量

## 变量赋值-创建

1. Python 中的变量不需要声明。每个变量在使用前都必须赋值，变量赋值以后该变量才会被创建。
2. 在 Python 中，变量就是变量，它没有类型，我们所说的"类型"是变量所指的内存中对象的类型。
   + 等号（=）用来给变量赋值。
    等号（=）运算符左边是一个变量名,等号（=）运算符右边是存储在变量中的值。例如：


```python
counter = 100          # 整型变量
miles   = 1000.0       # 浮点型变量
name    = "runoob"     # 字符串
 
print (counter)
print (miles)
print (name)
```

    100
    1000.0
    runoob
    

## 多个变量赋值

三个变量被赋予相同的数值，创建一个整型对象，值为 1，从后向前赋值。


```python
a = b = c = 1
print(a,b,c)
```

    1 1 1
    

为多个对象指定多个变量，两个整型对象 1 和 2 的分配给变量 a 和 b，字符串对象 "runoob" 分配给变量 c。


```python
a, b, c = 1, 2, "runoob"
print(a,b,c)
```

    1 2 runoob
    

# 标准数据类型

Python3 中有六个标准的数据类型：

- 不可变数据
  1. Number（数字）
  2. String（字符串）
  3. Tuple（元组）

- 可变数据
  1. List（列表）
  2. Set（集合）
  3. Dictionary（字典）

## Number（数字）

### 类型

Python 支持4种不同的数值类型：

1. 整型(Int) - 通常被称为是整型或整数，是正或负整数，不带小数点
2. 浮点型(float) - 浮点型由整数部分与小数部分组成
3. 布尔(bool) - 如 True
4. 复数(complex) - 复数由实数部分和虚数部分构成，可以用a + bj,或者complex(a,b)表示

我们可以使用十六进制和八进制来代表整数


```python
number = 0xA0F # 十六进制
number
```




    2575




```python
number=0o37    # 八进制
number
```




    31



1. 用 type() 函数 来查询变量所指的对象类型
2. 用 isinstance 函数 来判断变量所指的对象类型


```python
a, b, c, d = 20, 5.5, True, 4+3j
print(type(a), type(b), type(c), type(d))
```

    <class 'int'> <class 'float'> <class 'bool'> <class 'complex'>
    


```python
a = 111
isinstance(a, int)
```




    True



### 数字类型转换

数据类型的转换，你只需要将数据类型作为函数名即可

1. int(x) 将x转换为一个整数

2. float(x) 将x转换到一个浮点数

3. complex(x) 将x转换到一个复数，实数部分为 x，虚数部分为 0

4. complex(x, y) 将 x 和 y 转换到一个复数，实数部分为 x，虚数部分为 y

### 数字运算


```python
5 + 4  # 加法
```




    9




```python
4.3 - 2 # 减法
```




    2.3




```python
3 * 7  # 乘法
```




    21




```python
2 / 4  # 除法，得到一个浮点数
```




    0.5




```python
2 ** 5 # 乘方
```




    32




```python
17 % 3 # 取余（只允许整型）
```




    2




```python
2 // 4 # 除法，得到一个整数
```




    0




```python
7.0 // 2 # //得到的并不一定是整数类型的数，它与分母分子的数据类型有关系
```




    3.0



不同类型的数混合运算时会将整数转换为浮点数：


```python
3 * 3.75 / 1.5
```




    7.5



### 数学函数

round()内置方法
   1. 如果只有一个数作为参数，不指定位数的时候，返回的是一个整数，而且是最靠近的整数（这点上类似四舍五入）。
         - round(2.2) = 2
         - round(2.6) = 3
   2. 但是当出现.5 的时候，两边的距离都一样，round()取靠近的偶数。
         - round(2.5) = 2
         - round(3.5) = 3
   3. 当指定取舍的小数点位数的时候，一般情况也是使用四舍五入的规则，但是碰到.5 的这样情况；
         - 如果要取舍的位数前的小树是奇数，则直接舍弃。print(round(2.655,2)) = 2.65
         - 如果偶数这向上取舍。round(2.665,2) = 2.67


```python
round(3.1415926,4) # round( x , n]  ), x 保留n位小数，需要四舍五入
```




    3.1416




```python
abs(-1) # 返回数字的绝对值
```




    1




```python
max(1,2,3,4,5,6,7,8,9,0)
```




    9




```python
min(1,2,3,4,5,6,7,8,9,0)
```




    0




```python
pow(2, 3) # pow(x, y), 返回x**y 运算后的值。
```




    8



需 import math 后使用


```python
import math
math.sqrt(4) # sqrt(x), 返回数字x的平方根。
```




    2.0




```python
import math
math.modf( 4.23 ) # math.modf( x )，返回数字x的整数部分与小数部分
```




    (0.23000000000000043, 4.0)




```python
import math
math.ceil(4.1) # 返回数字的上入整数
```




    5




```python
import math
math.floor(4.1) # 返回数字的下舍整数
```




    4




```python
import math
math.exp(1) # exp(x), 返回e的x次幂(ex)
```




    2.718281828459045




```python
import math
math.log(100,10) # math.log(值.基数),math.log(100,10)返回2.0
```




    2.0




```python
import math
math.log10(100) # math.logM(X), 返回以M为基数的X的对数
```




    2.0



### 随机数函数

random() 方法返回随机生成的一个实数，它在[0,1)范围内。


```python
import random

# 第一个随机数
print ("random() : ", random.random())

# 第二个随机数
print ("random() : ", random.random())
```

    random() :  0.9457483750744298
    random() :  0.9444525154845035
    

random.choice() 方法返回一个列表，元组或字符串的随机项


```python
import random

print ("从 range(100) 返回一个随机数 : ",random.choice(range(100)))
print ("从列表中 [1, 2, 3, 5, 9]) 返回一个随机元素 : ", random.choice([1, 2, 3, 5, 9]))
print ("从字符串中 'Runoob' 返回一个随机字符 : ", random.choice('Runoob'))
```

    从 range(100) 返回一个随机数 :  28
    从列表中 [1, 2, 3, 5, 9]) 返回一个随机元素 :  2
    从字符串中 'Runoob' 返回一个随机字符 :  R
    

random.randrange (start, stop ,step)
random.randrange (stop)==random.randrange (0, stop ,1)
1. start -- 指定范围内的开始值，包含在范围内。
2. stop -- 指定范围内的结束值，不包含在范围内。
3. step -- 指定递增基数。


```python
import random
 
# 从 1-100 中选取一个奇数
print ("randrange(1,100, 2) : ", random.randrange(1, 100, 2))
 
# 从 0-99 选取一个随机数
print ("randrange(100) : ", random.randrange(100))
```

    randrange(1,100, 2) :  93
    randrange(100) :  39
    

random.uniform() 方法将随机生成下一个实数，它在 [x,y] 范围内


```python
import random
 
print ("uniform(5, 10) 的随机浮点数 : ",  random.uniform(5, 10))
 
print ("uniform(7, 14) 的随机浮点数 : ",  random.uniform(7, 14))
```

    uniform(5, 10) 的随机浮点数 :  6.011476018536204
    uniform(7, 14) 的随机浮点数 :  13.855100212556705
    

random.shuffle() 方法将序列的所有元素随机排序


```python
import random
 
list = [20, 16, 10, 5];
random.shuffle(list)
print ("随机排序列表 : ",  list)
 
random.shuffle(list)
print ("随机排序列表 : ",  list)
```

    随机排序列表 :  [5, 16, 20, 10]
    随机排序列表 :  [10, 20, 5, 16]
    

### 三角函数

1. acos(x) : 返回x的反余弦弧度值


```python
import math

print ("acos(0.64) : ",  math.acos(0.64))
```

    acos(0.64) :  0.8762980611683406
    

2. asin(x) : 返回x的反正弦弧度值


```python
import math

print ("asin(0.64) : ",  math.asin(0.64))
```

    asin(0.64) :  0.694498265626556
    

3. atan(x) : 返回x的反正切弧度值


```python
import math

print ("atan(0.64) : ",  math.atan(0.64))
```

    atan(0.64) :  0.5693131911006619
    

4. atan2(y, x) : 返回给定的 X 及 Y 坐标值的反正切值


```python
import math

print ("atan2(-0.50,-0.50) : ",  math.atan2(-0.50,-0.50))
```

    atan2(-0.50,-0.50) :  -2.356194490192345
    

5. cos(x) : 返回x的弧度的余弦值。


```python
import math

print ("cos(3) : ",  math.cos(3))
```

    cos(3) :  -0.9899924966004454
    

6. hypot(x, y) : 返回欧几里德范数 sqrt(x*x + y*y)


```python
import math

print ("hypot(3, 2) : ",  math.hypot(3, 2))
```

    hypot(3, 2) :  3.605551275463989
    

7. sin(x) : 返回的x弧度的正弦值


```python
import math

print ("sin(3) : ",  math.sin(3))
```

    sin(3) :  0.1411200080598672
    

8. tan(x) : 返回x弧度的正切值。


```python
import math
 
print ("(tan(3) : ",  math.tan(3))
print ("tan(math.pi/4) : ",  math.tan(math.pi/4))
```

    (tan(3) :  -0.1425465430742778
    tan(math.pi/4) :  0.9999999999999999
    

9. degrees(x) : 将弧度转换为角度,如degrees(math.pi/2) ， 返回90.0


```python
import math

print ("degrees(3) : ",  math.degrees(3))
print ("degrees(math.pi/4) : ",  math.degrees(math.pi/4))
```

    degrees(3) :  171.88733853924697
    degrees(math.pi/4) :  45.0
    

10. radians(x) : 将角度转换为弧度


```python
import math

print ("radians(3) : ",  math.radians(3))
```

    radians(3) :  0.05235987755982989
    

### 数学常量


```python
import random
math.pi        # 数学常量 pi（圆周率，一般以π来表示）
```




    3.141592653589793




```python
import random
math.e         # 数学常量 e，e即自然常数（自然常数）
```




    2.718281828459045



## String（字符串）

字符串是 Python 中最常用的数据类型。我们可以使用引号( ' 或 " )来创建字符串。

创建字符串很简单，只要为变量分配一个值即可。例如：


```python
var1 = 'Hello World!'
var2 = "Runoob"
```

### 字符串的 截取

1. 字符串的截取的语法格式如下：变量[头下标:尾下标:步长]
2. 索引值以 0 为开始值，-1 为从末尾的开始位置
![jupyter](./pictures/1.jpg)


```python
str = 'Runoab'
 
print (str)          # 输出字符串
print (str[0])       # 输出字符串第一个字符
print (str[-1])       # 输出字符串最后一个字符
print (str[0:-1])    # 输出第一个到倒数第二个(最后一个之前)的所有字符
print (str[2:5])     # 输出从第三个开始到第五个的字符
print (str[2:5:2])     # 输出从第三个开始到第五个的字符步长为2
print (str[2:])      # 输出从第三个开始的后的所有字符
print (str[:-2])     # 输出倒数第二个之前的所有字符
```

    Runoab
    R
    b
    Runoa
    noa
    na
    noab
    Runo
    

### 字符串的 连接&复制

1. 加号 + 是字符串的连接符
2. 星号 * 表示复制当前字符串，紧跟的数字为复制的次数。


```python
str = 'Runoob'
 
print (str * 4)      # 输出字符串4次
print (str + "TEST") # 连接字符串
```

    RunoobRunoobRunoobRunoob
    RunoobTEST
    

### 转义特殊字符

1. 使用反斜杠(\\)转义特殊字符
2. 在字符串前面添加一个 r，表示原始字符串


```python
print('Ru\noob')
print(r'Ru\noob')
```

    Ru
    oob
    Ru\noob
    

在需要在字符中使用特殊字符时，python用反斜杠(\)转义字符。如下表：
![jupyter](./pictures/3.jpg)

### 字符串运算符


```python
a = "Hello"
b = "Python"
 
print("a + b 输出结果：", a + b)
print("a * 3 输出结果：", a * 3)
print("a[1] 输出结果：", a[1])
print("a[1:4] 输出结果：", a[1:4])
 
if( "H" in a) :
    print("H 在变量 a 中")
else :
    print("H 不在变量 a 中")
 
if( "M" not in a) :
    print("M 不在变量 a 中")
else :
    print("M 在变量 a 中")
 
print (r'\n')
print (R'\n')
```

    a + b 输出结果： HelloPython
    a * 3 输出结果： HelloHelloHello
    a[1] 输出结果： e
    a[1:4] 输出结果： ell
    H 在变量 a 中
    M 不在变量 a 中
    \n
    \n
    

### 字符串格式化

Python 支持格式化字符串的输出 。尽管这样可能会用到非常复杂的表达式，但最基本的用法是将一个值插入到一个有字符串格式符 %s 的字符串中


```python
print ("我叫 %s 今年 %d 岁!" % ('小明', 10))
```

    我叫 小明 今年 10 岁!
    

### Python三引号

python三引号允许一个字符串跨多行，字符串中可以包含换行符、制表符以及其他特殊字符。实例如下


```python
para_str = """这是一个多行字符串的实例
多行字符串可以使用制表符
TAB ( \t )。
也可以使用换行符 [ \n ]。
"""
print (para_str)
```

    这是一个多行字符串的实例
    多行字符串可以使用制表符
    TAB ( 	 )。
    也可以使用换行符 [ 
     ]。
    
    

### 字符串内建函数


```python
str = "this is string example from runoob....wow!!!"

print ("len(str) : ", len(str)) # 字符串长度

print ("str.upper() : ", str.upper()) # 返回小写字母转为大写字母的字符串

print( "str.lower() : ",str.lower() ) # 转换字符串中所有大写字符为小写

print ("str.title() : ",str.title()) # 返回"标题化"的字符串,就是说所有单词的首字母都转化为大写
```

    len(str) :  44
    str.upper() :  THIS IS STRING EXAMPLE FROM RUNOOB....WOW!!!
    str.lower() :  this is string example from runoob....wow!!!
    str.title() :  This Is String Example From Runoob....Wow!!!
    

其他字符串函数
https://www.runoob.com/python3/python3-string.html

## Tuple（元组）

Python 的元组与列表类似，不同之处在于元组的**元素不能修改**。

元组使用小括号，列表使用方括号。

元组创建很简单，只需要在括号中添加元素，并使用逗号隔开即可。

- 元组中只包含一个元素时，需要在元素后面添加逗号，否则括号会被当作运算符使用

### 访问元组


```python
tup1 = ('Google', 'Runoob', 1997, 2000)
tup2 = (1, 2, 3, 4, 5, 6, 7 )
 
print ("tup1[0]: ", tup1[0])
print ("tup2[1:5]: ", tup2[1:5])
```

    tup1[0]:  Google
    tup2[1:5]:  (2, 3, 4, 5)
    

### 修改元组（伪）

元组中的元素值是不允许修改的，但我们可以对元组进行连接组合


```python
tup1 = (12, 34.56);
tup2 = ('abc', 'xyz')
 
# 以下修改元组元素操作是非法的。
# tup1[0] = 100
 
# 创建一个新的元组
tup3 = tup1 + tup2;
print (tup3)
```

    (12, 34.56, 'abc', 'xyz')
    

### 删除元组（伪）

元组中的元素值是不允许删除的，但我们可以使用del语句来删除整个元组
元组被删除后，输出变量会有异常信息


```python
tup = ('Google', 'Runoob', 1997, 2000)
 
print (tup)
del tup;
print ("删除后的元组 tup : ")
print (tup)
```

    ('Google', 'Runoob', 1997, 2000)
    删除后的元组 tup : 
    


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-63-cc087dd11595> in <module>()
          4 del tup;
          5 print ("删除后的元组 tup : ")
    ----> 6 print (tup)
    

    NameError: name 'tup' is not defined


### 元组间操作

与字符串一样，元组之间可以使用 + 号和 * 号进行运算。这就意味着他们可以组合和复制，运算后会生成一个新的元组。


```python
tup1 = ('Google', 'Runoob', 1997)
tup2 = (1, 2, 3, 4)

print ("len(tup1) : ", len(tup1)) # 列表长度
print ("tup1+tup2 : ", tup1+tup2)
print ("tup1*2 : ", tup1*2)
print ("3 in tup2 : ", 3 in tup2,"\n")

print (tup1) 
print (tup2) 
```

### 元组--列表


```python
list1= ['Google', 'Taobao', 'Runoob', 'Baidu']
tuple1=tuple(list1)


print(list1)
print(tuple1)
```

## List（列表）

序列是Python中最基本的数据结构。序列中的每个元素都分配一个数字 - 它的位置，或索引，第一个索引是0，第二个索引是1，依此类推。

列表可以作为一个方括号内的逗号分隔值出现，列表的数据项不需要具有相同的类型


```python
list1 = ['Google', 'Runoob', 1997, 2000]
list2 = [1, 2, 3, 4, 5 ]
list3 = ["a", "b", "c", "d"]

print (list1)
print (list2)
print (list3)
```

### 访问列表中的值

使用下标索引来访问列表中的值，同样你也可以使用方括号的形式截取字符


```python
list1 = ['Google', 'Runoob', 1997, 2000]
list2 = [1, 2, 3, 4, 5, 6, 7 ]

print ("list1[0]: ", list1[0])
print ("list1[-1]: ", list1[-1])
print ("list2[1:5]: ", list2[1:5])
print ("list2[5:]: ", list2[5:])
```

### 更新列表

1. 直接修改


```python
list = ['Google', 'Runoob', 1997, 2000]
 
print ("第三个元素为 : ", list[2])
list[2] = 2001
print ("更新后的第三个元素为 : ", list[2])
```

2. 删除列表元素


```python
list = ['Google', 'Runoob', 1997, 2000]
 
print ("原始列表 : ", list)
del list[2]
print ("删除第三个元素后 : ", list)
```

3. 在列表末尾添加新的对象


```python
list = ['Google', 'Runoob', 'Taobao']

print ("原始列表 : ", list)
list1.append('Baidu')
print ("更新后的列表 : ", list)
```

4. 将对象插入列表指定位置索引前


```python
list = ['Google', 'Runoob', 'Taobao']

print ("原始列表 : ", list)
list1.insert(1, 'Baidu')
print ('列表插入元素后为 : ', list)
```

5. 复制列表


```python
list1 = ['Google', 'Runoob', 'Taobao', 'Baidu']
list2 = list1.copy()
list3 = list1[:]
list1.insert(1, 'Baidu')

print ("list1 列表: ", list1)
print ("list2 列表: ", list2)
print ("list3 列表: ", list3)
```

6. 清空列表


```python
list = ['Google', 'Runoob', 'Taobao', 'Baidu']

print ("原始列表 : ", list)
list1.clear()
print ("列表清空后 : ", list)
```

7. 对原列表进行排序


```python
list = ['Google', 'Runoob', 'Taobao', 'Facebook']
 
print ("原始列表 : ", list)
print ("排序副本sorted(list) : ", sorted(list))
print ("原始列表 : ", list ,"\n")

list.sort()
print ( "升序排序后 : ", list)
list.sort(reverse=True)
print ( "降序排序后 : ", list)
```

### 列表间操作

列表对 + 和 * 的操作符与字符串相似。+ 号用于组合列表，* 号用于重复列表


```python
list1 = ['Google', 'Runoob', 1997]
list2 = [1, 2, 3, 4]

print ("len(list1) : ", len(list1)) # 列表长度

print ("list1+list2 : ", list1+list2)

print ("list1*2 : ", list1*2)

print ("3 in list2 : ", 3 in list2)
```

### 嵌套列表


```python
a = ['a', 'b', 'c']
n = [1, 2, 3]
x = [a, n]

print ("x : ", x)
print ("x[0] : ", x[0])
print ("x[0][1] : ", x[0][1])
```

## Set（集合)

集合（set）是一个无序的不重复元素序列。

可以使用大括号 { } 或者 set() 函数创建集合


```python
parame = {1,1,2,3,4,4,5}
value=[1,1,2,3,4,4,5]

print(parame)
print(set(value))
```

### 集合间运算


```python
basket = {'apple', 'orange', 'apple', 'pear', 'orange', 'banana'}
print(basket)                      # 这里演示的是去重功能

print('orange' in basket)          # 快速判断元素是否在集合内
print('crabgrass' in basket) 

 
# 下面展示两个集合间的运算.

a = set('abracadabra')
b = set('alacazam')
                                
print(a - b)              # 集合a中包含而集合b中不包含的元素
print(a | b)              # 集合a或b中包含的所有元素
print(a & b)              # 集合a和b中都包含了的元素
print(a ^ b)              # 不同时包含于a和b的元素

```

### 集合的基本操作

1. 添加元素
将元素 x 添加到集合 s 中，如果元素已存在，则不进行任何操作。


```python
thisset = set(("Google", "Runoob", "Taobao"))

# s.add( x )
thisset.add("Facebook")
print(thisset)

# s.update( x ) 也可以添加元素，且参数可以是列表，元组，字典等
thisset.update({1,3})
thisset.update([1,4],[5,6]) 
thisset.update({'Name': 'Runoob', 'Age': 7, 'Class': 'First'})
print(thisset)
```

2. 移除元素

- s.remove( x ) 将元素 x 从集合 s 中移除，如果元素不存在，则会发生错误。

- s.discard( x ) 移除集合中的元素，且如果元素不存在，不会发生错误。

- s.pop() 随机删除集合中的一个元素

3. 计算集合元素个数


```python
thisset = set(("Google", "Runoob", "Taobao"))
print("len(thisset) :", len(thisset))
```

4. 清空集合


```python
thisset = set(("Google", "Runoob", "Taobao"))
print(thisset)
thisset.clear()
print(thisset)
```

更多操作https://www.runoob.com/python3/python3-set.html

## Dictionary（字典）

字典是另一种可变容器模型，且可存储任意类型对象。

字典的每个键值(key=>value)对用冒号(:)分割，每个对之间用逗号(,)分割，整个字典包括在花括号({})中


```python
dict = {'Alice': '2341', 'Beth': '9102', 'Cecil': '3258'}
```

### 规则

1. 键必须是唯一的，但值则不必，创建时如果同一个键被赋值两次，后一个值会被记住。


```python
dict = {'Name': 'Runoob', 'Age': 7, 'Name': '小菜鸟'}
 
print ("dict['Name']: ", dict['Name'])
```

2. 值可以取任何数据类型，但键必须是不可变的，如字符串，数字或元组。


```python
dict = {'Age': 7, 2: 7, (1,2): 'Runoob', }
 
print (dict)
```


```python
dict = {['Name']: 'Runoob', 'Age': 7}
 
print ("dict['Name']: ", dict['Name'])
```

### 访问字典里的值

把相应的键放入到方括号中


```python
dict = {'Name': 'Runoob', 'Age': 7, 'Class': 'First'}
 
print ("dict['Name']: ", dict['Name'])
print ("dict['Age']: ", dict['Age'])
```

### 修改字典

增加新的键/值对，修改或删除已有键/值


```python
dict = {'Name': 'Runoob', 'Age': 7, 'Class': 'First'}
 
dict['Age'] = 8;               # 更新 Age
dict['School'] = "菜鸟教程"    # 添加信息
 
 
print ("dict['Age']: ", dict['Age'])
print ("dict['School']: ", dict['School'])
```

### 删除字典元素

删除字典后字典不再存在


```python
dict = {'Name': 'Runoob', 'Age': 7, 'Class': 'First'}
 
print (dict)

del dict['Name'] # 删除键 'Name'
print (dict)

dict.clear()     # 清空字典
print (dict)

del dict         # 删除字典
```

### 字典内置函数&方法


```python
dict = {'Name': 'Runoob', 'Age': 7, 'Class': 'First'}

print("len(dict) :",len(dict))
```
