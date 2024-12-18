# Pyhton

## 函数

函数是组织好的，可重复使用的，用来实现单一，或相关联功能的代码段。
函数能提高应用的模块性，和代码的重复利用率

```python
abs()：返回数字的绝对值。
dict()：创建一个字典或从键值对元组列表转换为字典。
help()：提供交互式帮助，或者显示对象的帮助文档。
min()：返回给定一组数值中的最小值。
setattr()：设置对象的属性值。
all()：检查可迭代对象中所有元素是否都为真（非零/非False）。
dir()：列出一个对象的所有属性和方法名。
hex()：将整数转换成十六进制字符串表示形式。
next()：从迭代器中获取下一个项目。
slice()：创建切片对象，用于访问序列类型的子集。
any()：检查可迭代对象中是否存在至少一个真值元素。
divmod()：返回除法运算的商和余数组成的元组。
id()：返回对象的唯一标识符（内存地址）。
object()：基础类，所有类都直接或间接继承自它。
sorted()：对可迭代对象进行排序并返回一个新的排序后列表。
ascii()：将对象转化为人类可读的ASCII表示形式的字符串。
enumerate()：将序列与对应的索引打包为枚举对象。
input()：接收用户输入，并将其当作字符串返回。
open()：打开文件并返回一个文件对象。
str()：将对象转化为字符串表示。
bool()：将对象转化为布尔值。
exec()：执行存储在字符串或代码对象中的Python语句。
int()：将对象转化为整数。
- pow()：计算两个数的乘方（基数、指数）或返回基数的指数次幂与模数的余数。
- super()：返回一个代理对象，用于调用父类（超类）的方法。
- bytearray()：创建一个可变的字节数组。
- float()：将对象转化为浮点数。
- iter()：获取一个可迭代对象的迭代器。
- print()：输出到标准输出设备（通常是屏幕），可以接多个参数并以指定的分隔符分开。
- tuple()：创建一个不可变元组。

- callable(): 判断对象是否可调用。
- chr(): 返回对应于整数（Unicode码点）的字符。
- frozenset(): 创建一个不可变集合。
- list(): 创建列表或从可迭代对象转换为列表。
- range(): 创建一个整数范围对象，常用于循环。
- vars(): 返回对象的属性字典（如果没有参数，则返回当前作用域的局部变量）
```

除了内置函数，Python 的标准库（如 math、os、datetime 等）还包含大量针对特定用途的函数，例如：

```python
数学函数：
math.sqrt(x) 计算平方根
math.sin(x) 计算正弦
math.log(x[, base]) 计算自然对数或以特定基数的对数
字符串函数：
str.upper() 将字符串转换为大写
str.lower() 将字符串转换为小写
str.find(sub[, start[, end]]) 查找子字符串的位置
文件操作函数：
open(file, mode) 打开文件
file.read() 读取文件内容
file.write(data) 写入数据到文件
网络编程函数：
socket.socket(family, type[, proto]) 创建套接字对象
http.client.HTTPConnection(host[, port]) 创建HTTP连接
urllib.request.urlopen(url[, data[, timeout[, cafile[, capath[, context]]]]]) 发送HTTP请求
用户自定义函数
开发者可以根据需要编写自己的函数，这些被称为用户自定义函数，可以接受任意数量的参数，包括位置参数、关键字参数、默认参数和可变参数，并且可以通过return语句返回一个或多个值。如果函数没有return语句或者return后不跟任何表达式，则函数会默认返回None。
```

## 列表

序列是 Python 中最基本的数据结构。

列表是最常用的 Python 数据类型，它可以作为一个方括号内的逗号分隔值出现。
列表的数据项不需要具有相同的类型
创建一个列表，只要把逗号分隔的不同的数据项使用方括号括起来即可。如下所示

```pyhton
    list1 = ['Google','Runoob',2000,20024]
    list2 = [1,2,3,4,5]
    list3 = ["a","b","c","d"]
    list4 = ['red','green','blue','yellow','white', 'black']
```

### 访问列表中的值

与字符串的索引一样，列表索引从 0 开始，第二个索引是 1，依此类推。
实例：

```python
    list = ['red', 'green', 'blue', 'yellow', 'white', 'black']
    print( list[0] )
    print( list[1] )
    print( list[2] )
```

输出结果：

```python
    red green blue
```

索引也可以从尾部开始，最后一个元素的索引为 -1，往前一位为 -2，以此类推。
实例：

```python
    list = ['red', 'green', 'blue', 'yellow', 'white', 'black']
    print( list[-1] )
    print( list[-2] )
    print( list[-3] )
```

输出：

```python
black white yellow
```

使用下标索引来访问列表中的值，同样你也可以使用方括号 [] 的形式截取字符，如下所示

```python
nums = [10, 20, 30, 40, 50, 60, 70, 80, 90]
print(nums[0:4])
```

输出结果：

```python
[10, 20, 30, 40]
```

### 更新列表

你可以对列表的数据项进行修改或更新，你也可以使用 append() 方法来添加列表项，如下所示：

```python
list = ['Google','Runoob',2000,2024]

print ("第三个元素为:",list[2])
list[2] = 015
print ("更新后的第三个元素为:",list[2])

list1 = ['Google','Runoob','Taobao']
list1.append('Baidu')
print ("更新后的列表:",list1)
```

输出结果：

```python
第三个元素为:2000
更新后的第三个元素为: 015
更新后的列表:['Google','Runoob','Taobao','Baidu']
```

### 删除列表元素

可以使用 del 语句来删除列表的的元素，如下实例：

```python
list = ['Google','Runoob',2000,2024]
print ("原始列表 : ", list)
del list[2]
print ("删除第三个元素 : ", list)
```

输出结果：

```python
原始列表:['Google','Runoob',2000,2024]
删除第三个元素:['Google','Runoob',2024]
```

### Python 列表脚本操作符

列表对 + 和 _ 的操作符与字符串相似。+ 号用于组合列表，_ 号用于重复列表。

```python
len([1, 2, 3])	            3	           长度
[1, 2, 3]+[4, 5, 6]	  [1, 2, 3, 4, 5, 6]	组合
['Hi!']*4	  ['Hi!','Hi!','Hi!','Hi!']	重复
3 in [1, 2, 3]	            True 	元素是否存在于列表中
for x in [1, 2, 3]: print(x, end=" ")	1 2 3	迭代
```

### Python 列表截取与拼接

```python
L=['Google', 'Runoob', 'Taobao']
L[2]	'Taobao'	读取第三个元素
L[-2]	'Runoob'	从右侧开始读取倒数第二个元素: count from the right
L[1:]	['Runoob', 'Taobao']	输出从第二个元素开始后的所有元素
```

### 嵌套列表

使用嵌套列表即在列表里创建其它列表，例如：

```python
>>> a = ['a', 'b', 'c']
>>> n = [1, 2, 3]
>>> x = [a, n]
>>> x
[['a', 'b', 'c'], [1, 2, 3]]
>>> x[0]
['a', 'b', 'c']
>>> x[0][1]
'b'
```

### 列表比较

列表比较需要引入 operator 模块的 eq 方法

```python
# 导入 operator 模块
import operator
a = [1, 2]
b = [2, 3]
c = [2, 3]
print("operator.eq(a,b): ", operator.eq(a,b))
print("operator.eq(c,b): ", operator.eq(c,b))
```

输出：

```python
operator.eq(a,b):  False
operator.eq(c,b):  True
```

### Python 列表函数&方法

函数：

```python
len(list)  列表元素个数
max(list)  返回列表元素最大值
min(list)  返回列表元素最小值
list(seq)  将元组转换为列表
```

方法：

```python
list.append(obj)  在列表末尾添加新的对象
list.count(obj)   统计某个元素在列表中出现的次数
list.extend(seq)  在列表末尾一次性追加另一个序列中的多个值（用新列表扩展原来的列表）
list.index(obj)   从列表中找出某个值第一个匹配项的索引位置
list.insert(index, obj)   将对象插入列表
list.pop([index=-1])   移除列表中的一个元素（默认最后一个元素），并且返回该元素的值
list.remove(obj)   移除列表中某个值的第一个匹配项
list.reverse()   反向列表中元素
list.sort( key=None, reverse=False)   对原列表进行排序
list.clear()   清空列表
list.copy()    复制列表
```

## 元组

Python 的元组与列表类似，不同之处在于元组的元素不能修改。
元组使用小括号 ( )，列表使用方括号 [ ]。
元组创建很简单，只需要在括号中添加元素，并使用逗号隔开即可。

```python
tup1 = ()        #  创建空元组
>>> tup1 = ('Google', 'Runoob', 2000, 2004)
>>> tup2 = (1, 2, 3, 4, 5 )
>>> tup3 = "a", "b", "c", "d"   #  不需要括号也可以
>>> type(tup3)
```

元组中只包含一个元素时，需要在元素后面添加逗号 , ，否则括号会被当作运算符使用：

```python
>>> tup1 = (50)
>>> type(tup1)     # 不加逗号，类型为整型

>>> tup1 = (50,)
>>> type(tup1)     # 加上逗号，类型为元组
```

### 访问元组

元组可以使用下标索引来访问元组中的值，如下实例:

```python
tup1 = ('Google', 'Runoob', 2000, 2004)
tup2 = (1, 2, 3, 4, 5, 6, 7 )

print ("tup1[0]: ", tup1[0])
print ("tup2[1:5]: ", tup2[1:5])
```

输出结果：

```python
tup1[0]:  Google
tup2[1:5]:  (2, 3, 4, 5)
```

### 修改元组

元组中的元素值是不允许修改的，但我们可以对元组进行连接组合，如下实例:

```python
tup1 = (12, 34.56)
tup2 = ('abc', 'xyz')
# 以下修改元组元素操作是非法的。
# tup1[0] = 100
# 创建一个新的元组
tup3 = tup1 + tup2
print (tup3)
```

以上实例输出结果：

```python
(12, 34.56, 'abc', 'xyz')
```

### 删除元组

元组中的元素值是不允许删除的，但我们可以使用 del 语句来删除整个元组，如下实例:

```python
tup = ('Google', 'Runoob', 2000, 2004)
print (tup)
del tup
print ("删除后的元组 tup : ")
print (tup)
```

以上实例元组被删除后，输出变量会有异常信息，输出如下所示：

```python
删除后的元组 tup :
Traceback (most recent call last):
  File "test.py", line 8, in <module>
    print (tup)
NameError: name 'tup' is not defined
```

一种常见的方法是将元组转换为列表（List），列表是可变的，可以在其中添加、删除或修改元素。然后，你可以对列表执行删除操作，最后再将列表转回元组

```python
# 创建一个元组
my_tuple = (1, 2, 3, 4, 5)
# 将元组转换为列表
my_List = list(my_Tuple)
# 从列表中删除一个元素，比如删除3
my_List.remove(3)
# 如果你需要，你可以再将列表转回元组
my_Tuple = tuple(my_List)
print(my_Tuple)  # 输出: (1, 2, 4, 5)
```

请注意，这种方法会创建一个新的元组，而原始的元组仍然保持不变，因为元组是不可变的。
如果你经常需要修改元组，可能需要考虑使用列表或其他可变的数据结构，而不是元组。

### 元组运算符

与字符串一样，元组之间可以使用 +、+=和 \* 号进行运算。这就意味着他们可以组合和复制，运算后会生成一个新的元组。

```python
len((1, 2, 3))	3	计算元素个数
3 in (1, 2, 3)	True	元素是否存在
('Hi!',) * 4	('Hi!', 'Hi!', 'Hi!', 'Hi!')	复制
#等。。。。
```

### 元组索引，截取

因为元组也是一个序列，所以我们可以访问元组中的指定位置的元素，也可以截取索引中的一段元素，如下所示：

```python
tup = ('Google', 'Runoob', 'Taobao', 'Wiki', 'Weibo','Weixin')
```

表达式：

```python
tup[1]	'Runoob'	#读取第二个元素
tup[-2]	'Weibo'	 #反向读取，读取倒数第二个元素
tup[1:]	('Runoob', 'Taobao', 'Wiki', 'Weibo', 'Weixin')	#截取元素，从第二个开始后的所有元素。
tup[1:4]	('Runoob', 'Taobao', 'Wiki')	#截取元素，从第二个开始到第四个元素(索引为 3)
```

### 元组内置函数

Python 元组包含了以下内置函数

```python
len(tuple)  计算元组元素个数。
max(tuple)     返回元组中元素最大值。
min(tuple)     返回元组中元素最小值。
tuple(iterable)  将可迭代系列转换为元组。
```

### 关于元组是不可变的

所谓元组的不可变指的是元组所指向的内存中的内容不可变

## 字典

字典是另一种可变容器模型，且可存储任意类型对象。
字典的每个键值(key=>value)对用冒号(:)分割，每个对之间用逗号(,)分割，整个字典包括在花括号({})中 ,格式如下所示：

```python
d = {key1 : value1, key2 : value2 }
```

键必须是唯一的，但值则不必。
值可以取任何数据类型，但键必须是不可变的，如字符串，数字或元组。一个简单的字典实例：

```python
dict = {'Alice': '2341', 'Beth': '9102', 'Cecil': '3258'}
```

也可如此创建字典：

```python
dict1 = { 'abc': 456 }
dict2 = { 'abc': 123, 98.6: 37 }
```

### 访问字典里的值

把相应的键放入到方括号中，如下实例:

```python
dict = {'Name': 'Runoob', 'Age': 7, 'Class': 'First'}
print ("dict['Name']: ", dict['Name'])
print ("dict['Age']: ", dict['Age'])
```

以上实例输出结果：

```python
dict['Name']:  Runoob
dict['Age']:  7
```

如果尝试用字典里不存在的键来访问数据，将会触发一个 KeyError 异常。例如：

```python
my_dict = {'Name': 'Zara', 'Age': 7, 'Class': 'First'}
print(my_dict['Alice'])
# 运行上述代码会抛出以下错误：
# KeyError: 'Alice'
```

这意味着你试图访问的键 'Alice' 在字典 my_dict 中找不到。若要在尝试访问不存在的键时不引发错误，并能返回一个默认值，你可以使用 dict.get() 方法：

```python
rint(my_dict.get('Alice', 'Not found'))  # 输出: 'Not found'
```

这样，如果 'Alice' 键不存在，则会返回指定的默认值 'Not found'

### 增加字典

向字典添加新内容的方法是增加新的键/值对，如下实例:

```python
my_dict = {'name': 'Alice', 'age': 25}
my_dict['city'] = 'New York'  # 添加新的键值对
print(my_dict)  # 输出: {'name': 'Alice', 'age': 25, 'city': 'New York'}
```

更新已有键的值：

```python
my_dict['age'] = 26  # 更新已存在的键的值
print(my_dict)  # 输出: {'name': 'Alice', 'age': 26, 'city': 'New York'}
```

### 删除字典

使用 del 关键字：

```python
del my_dict['age']
print(my_dict)  # 输出: {'name': 'Alice', 'city': 'New York'}
```

使用 pop 方法：

```python
my_dict.pop('city')  # 删除并返回对应的值
print(my_dict)  # 输出: {'name': 'Alice'}
```

注意：由于字典是可变数据类型，以上所有操作都会直接修改原字典，而不会创建新的字典对象。

### 字典键的特性

字典在 Python 中是一种映射数据类型，它以键值对（key-value pairs）的形式存储数据，每个键都是独一无二的。关于字典键的特性，可以总结如下：

唯一性（Uniqueness）： 字典中的键必须是唯一的，即不同的键对应不同的值。如果尝试添加一对键值，而这个键已经存在于字典中，则旧的键对应的值会被新值覆盖。

不可变性（Immutability）： 字典的键必须是不可变对象，这意味着它们在创建后其内容不能被更改。常见的不可变类型有：整型、浮点型、字符串、元组（只要元组内部包含的元素也是不可变类型的）以及 None。列表、字典或其他可变类型不能作为字典的键，因为它们的哈希值在修改后会发生变化，违反了哈希表的要求。

```python
# 创建一个简单的字典，键是字符串（不可变类型），值是任意类型
my_dict = {
    "apple": 10,
    "banana": 20,
    "cherry": 30
}
# 展示唯一性：尝试添加一个已存在的键，会替换原有值而不是新增键值对
my_dict["apple"] = 15
print(my_dict)  # 输出: {'apple': 15, 'banana': 20, 'cherry': 30}
# 展示不可变性：尝试使用列表作为键，会抛出TypeError
try:
    my_dict[["fruit"]] = "not allowed"
except TypeError as e:
    print(e)  # 输出: unhashable type: 'list'
# 正确使用不可变对象作为键的例子
my_dict[(1, 2)] = "tuple_key"
print(my_dict)  # 输出: {'apple': 15, 'banana': 20, 'cherry': 30, (1, 2): 'tuple_key'}
# 尝试修改作为键的元组，但由于元组是不可变的，因此会创建新的元组，原来的键不受影响
key_tuple = (1, 2)
my_dict[key_tuple] = "original_value"
modified_tuple = key_tuple + (3,)  # 新的元组
my_dict[modified_tuple] = "new_value"
print(my_dict)  # 输出: {'apple': 15, 'banana': 20, 'cherry': 30, (1, 2): 'original_value', (1, 2, 3): 'new_value'}
```

可哈希性（Hashability）： 字典键必须是可哈希的，即它们必须支持*hash*()方法，该方法返回一个固定的哈希值。同时，还需要支持*eq*()方法用于判断两个键是否相等。哈希值相同的两个键必须是相等的，反之亦然。

高效查找（Efficient Lookups）： 由于键的唯一性和哈希表的底层实现，Python 字典可以通过键快速查找对应的值，时间复杂度接近 O(1)，这是字典数据结构的一大优点。

不支持索引和切片： 字典不支持像列表那样通过索引位置来访问元素，也不支持切片操作。

排序无关性（Orderlessness）： 在 Python 3.7 版本之前，字典是无序的，尽管 Python 3.7 及以后版本的字典保持插入顺序，但这不是键的固有特性，而是字典实现上的改进。键的顺序并不影响字典的逻辑结构和查找效率。

综上所述，字典键的特性确保了字典作为一种高效的数据结构，在内存管理和查找速度上有出色表现。

### 字典方法

len(d)：返回字典中键值对的数量

```python
d = {'a': 1, 'b': 2}
print(len(d))  # 输出：2
```

d[key]：访问字典中指定键对应的值，如果键不存在则抛出 KeyError

```python
d = {'a': 1, 'b': 2}
print(d['a'])  # 输出：1
```

d[key] = value：设置或更新字典中键对应的值

```python
d = {'a': 1, 'b': 2}
d['c'] = 3
```

d.clear()：删除字典中所有的键值对，使其成为一个空字典

```python
d.clear()
```

### 字典函数

dict()：创建一个字典。例如：

```python
my_dict = dict(name="Alice", age=25)
```

str(d):输出字典，以可打印的字符串表示

```python
>>> d = {'Name': 'Runoob', 'Age': 7, 'Class': 'First'}
>>> str(d)
"{'Name': 'Runoob', 'Class': 'First', 'Age': 7}"
```

dict()：构造函数，用来创建一个字典。也可以接受可迭代的键值对或者映射类型来初始化字典。

```python
d = dict(a=1, b=2)  # 直接创建
d = dict([(k, v) for k, v in [('a', 1), ('b', 2)]])  # 通过元组列表创建
```

type(variable)
返回输入的变量类型，如果变量是字典就返回字典类型

```python
>>> tinydict = {'Name': 'Runoob', 'Age': 7, 'Class': 'First'}
>>> type(tinydict)
<class 'dict'>
```

## 集合

集合（set）是一个无序的不重复元素序列。
集合中的元素不会重复，并且可以进行交集、并集、差集等常见的集合操作
可以使用大括号 { } 创建集合，元素之间用逗号 , 分隔， 或者也可以使用 set() 函数创建集合。
创建格式：

```python
parame = {value01,value02,...}
或者
set(value)
```

以下是一个简单实例：

```python
set1 = {1, 2, 3, 4}            # 直接使用大括号创建集合
set2 = set([4, 5, 6, 7])      # 使用 set() 函数从列表创建集合
```

注意：创建一个空集合必须用 set() 而不是 { }，因为 { } 是用来创建一个空字典。

更多实例演示：

```python
>>> basket = {'apple', 'orange', 'apple', 'pear', 'orange', 'banana'}
>>> print(basket)                      # 这里演示的是去重功能
{'orange', 'banana', 'pear', 'apple'}
>>> 'orange' in basket                 # 快速判断元素是否在集合内
True
>>> 'crabgrass' in basket
False
>>> # 下面展示两个集合间的运算.
...
>>> a = set('abracadabra')
>>> b = set('alacazam')
>>> a
{'a', 'r', 'b', 'c', 'd'}
>>> a - b                              # 集合a中包含而集合b中不包含的元素
{'r', 'd', 'b'}
>>> a | b                              # 集合a或b中包含的所有元素
{'a', 'c', 'r', 'd', 'b', 'm', 'z', 'l'}
>>> a & b                              # 集合a和b中都包含了的元素
{'a', 'c'}
>>> a ^ b                              # 不同时包含于a和b的元素
{'r', 'd', 'b', 'm', 'z', 'l'}
```

### 集合推导式

这是一种简洁地创建集合的方法，尤其当你需要基于现有数据结构生成新集合时非常有用。集合推导式的语法类似于列表推导式，只是用花括号 {} 替换方括号 []

```python
# 假设我们有一个列表，并希望创建一个只包含其中偶数的新集合
numbers_list = [1, 2, 3, 4, 5, 6]
# 使用集合推导式创建仅包含偶数的新集合
even_numbers_set = {num for num in numbers_list if num % 2 == 0}
print(even_numbers_set)  # 输出：{2, 4, 6}
```

### 添加元素

语法：

```python
s.add( x )
```

需要添加多个元素：

```python
#语法格式:  s.update( x )
s = set()
elements = [2, 'banana', True]
# 使用 update() 方法添加多个元素
s.update(elements)
# 或者一次性创建集合（假设之前 s 是空集合）
# s = set([2, 'banana', True])
print(s)  # 输出: {2, 'banana', True}
```

### 移除元素

使用 remove() 方法:

```python
s = {1, 2, 3, 'apple'}
s.remove(2)  # 移除指定元素
print(s)  # 输出: {1, 3, 'apple'}
```

使用 discard() 方法：

```python
s = {1, 2, 3, 'apple'}
s.discard(2)  # 尝试移除指定元素，若不存在则不做任何事且不报错
print(s)  # 输出: {1, 3, 'apple'}
```

使用 pop() 方法

```python
s = {1, 2, 3, 'apple'}
removed_element = s.pop()  # 随机移除并返回一个元素
print(s)  # 输出可能为: {1, 2, 'apple'} （具体取决于被移除的元素）
```

pop() 方法不接受参数时会随机移除并返回一个集合中的元素。如果你想要控制移除的元素，但集合不支持通过索引进行移除，你可以先通过 if 判断元素是否存在再移除。

### 计算集合元素个数

计算集合 s 元素个数

```python
#语法格式如下：len(s)
>>> thisset = set(("Google", "Runoob", "Taobao"))
>>> len(thisset)
3
```

### 清空集合

```python
#语法格式如下：s.clear()
>>> thisset = set(("Google", "Runoob", "Taobao"))
>>> thisset.clear()
>>> print(thisset)
set()
```

### 判断元素是否在集合中存在

可以使用成员运算符 in

```python
#语法格式如下： x in s
s = {"apple", "banana", "cherry"}
x = "banana"

# 判断 x 是否在集合 s 中
if x in s:
    print("True")
else:
    print("False")

# 上述代码等价于直接输出布尔值
print(x in s)  # 输出: True 如果 x 在 s 中；False 如果不在
```

### 集合方法

```python
add()	为集合添加元素
clear()	移除集合中的所有元素
copy()	拷贝一个集合
difference()	返回多个集合的差集
difference_update()	移除集合中的元素，该元素在指定的集合也存在。
discard()	删除集合中指定的元素
intersection()	返回集合的交集
intersection_update()	返回集合的交集。
isdisjoint()	判断两个集合是否包含相同的元素，如果没有返回 True，否则返回 False。
issubset()	判断指定集合是否为该方法参数集合的子集。
issuperset()	判断该方法的参数集合是否为指定集合的子集
pop()	随机移除元素
remove()	移除指定元素
symmetric_difference()	返回两个集合中不重复的元素集合。
symmetric_difference_update()	移除当前集合中在另外一个指定集合相同的元素，并将另外一个指定集合中不同的元素插入到当前集合中。
union()	返回两个集合的并集
update()	给集合添加元素
len()	计算集合元素个数
```

## 迭代器与生成器

迭代在 Python 中是一种重复访问集合元素的机制，它允许程序员按照一定的顺序逐个访问集合中的项目，而无需关心底层的实现细节
迭代是 Python 最强大的功能之一，是访问集合元素的一种方式。
迭代器是一个可以记住遍历的位置的对象。
迭代器对象从集合的第一个元素开始访问，直到所有的元素被访问完结束。迭代器只能往前不会后退。
字符串，列表或元组对象都可用于创建迭代器，显式使用（**通过 iter()和 next()函数**）：

```python
>>> list = [1, 2, 3, 4]  # 创建一个包含整数的列表
>>> it = iter(list)       # 使用 iter() 函数获取该列表的迭代器
>>> print(next(it))        # 调用 next() 函数获取并输出迭代器的第一个元素
1
>>> print(next(it))        # 再次调用 next() 获取并输出第二个元素
2
```

如果继续调用 next(it)，将会依次输出 3 和 4。当所有元素都被遍历后，再次调用 next(it)会触发 StopIteration 异常，因为迭代器已经没有更多的元素可以返回了。

迭代器对象还可以使用常规 for 语句进行遍历，隐式使用（通过 for 循环）：

```python
#创建一个列表
my_list = [1, 2, 3, 4, 5] #使用 for 循环隐式地创建并使用迭代器
for item in my_list:
print(item) #输出：
#1
#2
#3
#4
#5
```

### 创建一个迭代器

对于列表、元组、字符串等内置序列类型，它们本身就具有迭代能力，可以通过**iter()**函数直接创建迭代器
使用内置序列类型的 _ iter_ 方法（隐式创建）：

```python
#列表
numbers = [1, 2, 3, 4, 5]
iterator = iter(numbers)

#字符串
text = "Hello"
char_iterator = iter(text)
```

直接使用 iter()函数创建迭代器
对于任何实现了 _ iter _ 方法的对象，都可以通过 iter()函数获得迭代器：

```python
class MyRange:
    def __init__(self, stop):
        self.current = 0
        self.stop = stop

    def __iter__(self):
        return self

    def __next__(self):
        if self.current >= self.stop:
            raise StopIteration
        current_value = self.current
        self.current += 1
        return current_value

my_range = MyRange(5)
range_iterator = iter(my_range)
```

### 生成器函数

成器函数在 Python 中是一种特殊的函数，它们使用关键字 **yield** 而不是 return 来返回值。每次调用生成器函数的 _ next _ () 方法时，函数会从上次停止的地方继续执行，直到遇到下一个 yield 语句，并返回该处的表达式的值。这种特性使得生成器能够按需逐次产出一系列值，而不是一次性计算并返回所有结果，从而节省内存和提高效率。

```python
def simple_generator(n):
    for i in range(n):
        yield i * 2  # 每次循环都会产出i的两倍，并暂停执行
# 使用生成器
gen = simple_generator(5)
for value in gen:
    print(value)
```
