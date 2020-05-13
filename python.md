# 数据类型
##  数字类型
数字类型包括 int类型、float类型、complex类型

### int
Python 的 int 不同于 Java 的 int，Python 中无论整数的大小长度为多少，统称为 int。


```python
int_sample = 2 ** 50
print("%s 的类型为：%s" % (int_sample, type(int_sample)))
str_int = int("123")
print("%s 的类型为：%s" % (str_int, type(str_int)))
```

    1125899906842624 的类型为：<class 'int'>
    123 的类型为：<class 'int'>


### float
float 等会补充

### complex
主要用于高级数学计算

## 布尔（bool）

对于 bool 型来说，只存在两种值 True 和 False，对应二进制分别为 0 和 1。值为 False 的数有：None、空、[]、{}、()、0。 


```python
bl_none = bool(None)
bl_blank = bool()
bl_brackets = bool(())
bl_0 = bool(0)
print("%s 的类型为：%s" %(bl_none, type(bl_none)))
print("%s 的类型为：%s" %(bl_blank, type(bl_blank)))
print("%s 的类型为：%s" %(bl_brackets, type(bl_brackets)))
print("%s 的类型为：%s" %(bl_0, type(bl_0)))
```

    False 的类型为：<class 'bool'>
    False 的类型为：<class 'bool'>
    False 的类型为：<class 'bool'>
    False 的类型为：<class 'bool'>


## 字符串（str）
字符串可由单引号或双引号（没区别）来创建，字符串是不可修改的。

索引：index 和 find

区别：index 和 find 都可以进行字符串的索引，区别在于索引的数据不存在的时候，index 返回的是 ValueError 错误；而 find 返回的是 -1。

字符串转换：str(object)


```python
print("str dict is: ", type(str({"a":1, "b":2})))

str_sample = "1234cabdef"
index_str1 = str_sample.index("a")
print("%s 的 index 索引是 %s" % (str_sample, index_str1))
try:
    index_str2 = str_sample("x")
except Exception as e:
    print("%s 的 index 索引是不存在返回 %s" % (str_sample, e))
    
print(".............................\n")

find_str1 = str_sample.find("ab")
print("%s 的 index 索引是 %s" % (str_sample, find_str1))
find_str2 =  str_sample.find("x")
print("%s 的 index 索引是 %s" % (str_sample, find_str2))
```

    str dict is:  <class 'str'>
    1234cabdef 的 index 索引是 5
    1234cabdef 的 index 索引是不存在返回 'str' object is not callable
    .............................
    
    1234cabdef 的 index 索引是 5
    1234cabdef 的 index 索引是 -1


### 切片 - [start: end: step]


```python
str_sample = "1234567890abcdef"
section_str_1 = str_sample[0: 4]
section_str_2 = str_sample[0: 6: 2]
print("%s 的切片是：%s" % (str_sample, section_str_1))
print("%s 的切片是：%s" % (str_sample, section_str_2))
```

    1234567890abcdef 的切片是：1234
    1234567890abcdef 的切片是：135


### 遍历 - for


```python
str_sample = "1234567890abcdef"
for i in str_sample:
    print("字符串的元素有：%s" % i)
# for i in range(len(str_sample)):
#    print("字符串的元素有：%s" % str_sample[i])
```

    字符串的元素有：1
    字符串的元素有：2
    字符串的元素有：3
    字符串的元素有：4
    字符串的元素有：5
    字符串的元素有：6
    字符串的元素有：7
    字符串的元素有：8
    字符串的元素有：9
    字符串的元素有：0
    字符串的元素有：a
    字符串的元素有：b
    字符串的元素有：c
    字符串的元素有：d
    字符串的元素有：e
    字符串的元素有：f


### 删除 - del



```python
del_str = "del none"
del del_str
try:
    print("del_str: ", del_str)
except Exception as e:
    print("del_str: %s" % e)
```

    del_str: name 'del_str' is not defined


### 分割 - split + partition
partition 指定分隔符，split 指定分隔符分割


```python
par_spl_str = "This-is-a-good work tool."
par = par_spl_str.partition("-")
print("partition str is:  ", par)
spl = par_spl_str.split(" ", 2)
print("split str is:  %s" % spl)
```

    partition str is:   ('This', '-', 'is-a-good work tool.')
    split str is:  ['This-is-a-good', 'work', 'tool.']


### 替换 - replace、strip、lstrip、rstrip


```python
str_sample = " This is a good boy. "
print("replace str is: ", str_sample.replace("good", "bad"))
print("strip str(去掉字符串两端的空格) is: ", str_sample.strip())
print("lstrip str(去掉字符串左端的空格) is: ", str_sample.lstrip())
print("rstrip str(去掉字符串左端的空格) is: ", str_sample.rstrip())
```

    replace str is:   This is a bad boy. 
    strip str(去掉字符串两端的空格) is:  This is a good boy.
    lstrip str(去掉字符串左端的空格) is:  This is a good boy. 
    rstrip str(去掉字符串左端的空格) is:   This is a good boy.


### 连接 - join


```python
str_sample = "abcdefgh"
print("-->".join(str_sample))
```

    a-->b-->c-->d-->e-->f-->g-->h


### 大小写转化 
    capitalize - 第一个单词首字母大写
    lower - 所有字符转换为小写字母
    upper - 所有字符转换为大写字母
    title - 将字符串转换为标题形式
    swapcase - 字符串大小写相互转换


```python
capitalize_str = "i am boy."
print("capitalize str is: %s" % capitalize_str.capitalize())
lower_str = "I AM A BOY."
print("lower str is: %s" % lower_str.lower())
upper_str = "i am a boy."
print("upper str is: %s" % upper_str.upper())
title_str = "i am a boy."
print("title str is: %s" % title_str.title())
swapcase_str = "I Am A Boy."
print("swapcase str is: %s" % swapcase_str.swapcase())
```

    capitalize str is: I am boy.
    lower str is: i am a boy.
    upper str is: I AM A BOY.
    title str is: I Am A Boy.
    swapcase str is: i aM a bOY.


### 字符串始末 - startswith、endswith


```python
str_sample = "We are lovely person."
print("str_sample startswith is: %s" % str_sample.startswith("We"))
print("str_sample startswith is: %s" % str_sample.startswith("we"))
print("str_sample endswith is: %s" % str_sample.endswith("n."))
print("str_sample endswith is: %s" % str_sample.endswith("n"))
```

    str_sample startswith is: True
    str_sample startswith is: False
    str_sample endswith is: True
    str_sample endswith is: False


### 判断字符串
    isalnum - 字符串是数字或字母的组合
    isalpha - 字符串是字母组合
    isdigit - 字符串是数字组合


```python
def judge_str(str_sample):
    if str_sample.isdigit() == True:
        print("数字组合")
    elif str_sample.isalpha() == True:
        print("字母组合")
    elif str_sample.isalnum() == True:
        print("数字或字母组合")
    else:
        print("混杂组合")
        
if __name__ == "__main__":
    str_sample_1 = "abc123"
    str_sample_2 = "abc"
    str_sample_3 = "123"
    str_sample_4 = "abc123字符串"
    judge_str(str_sample_1)
    judge_str(str_sample_2)
    judge_str(str_sample_3)
    judge_str(str_sample_4)

```

    数字或字母组合
    字母组合
    数字组合
    数字或字母组合


### 格式化输出 - %、format、format_map


```python
str_sample = "My name is {name}, i am {age} years old."
print(str_sample.format(name="A", age=26))
print(str_sample.format_map({"name": "B", "age": 25}))
print("My name is %s, i am %s years old." % ("c", 27))
```

    My name is A, i am 26 years old.
    My name is B, i am 25 years old.
    My name is c, i am 27 years old.


### 扩展 - expandtabs


```python
str_sample = "name\tage\tsex\tA\t22\t'男'\tB\t23\t'女'"
print("str_sample expandtabs str is: %s" % str_sample.expandtabs())
```

    str_sample expandtabs str is: name    age     sex     A       22      '男'     B       23      '女'


## 列表（list）
是由一系列特定元素顺序排列的元素组成，组成元素组成可以是：数字、字符串、列表、元组、布尔值、字典，列表是可以修改的。

### 取值（索引+切片）
    索引 - 根据特定位置取值
    切片 - 根据指定范围位置取值


```python
list_sample = [123, "sample", [1,2,3], (1,2,3), True, {"a": 1., "b": 2}]
print("%s 位置上索引的值是：%s" % (5, list_sample[2]))
print("%s:%s之间的切片值是：%s" % (0,4, list_sample[0:4]))
print("反向输出列表方法一：%s" % list_sample[::-1])
list_sample.reverse()
print("反向输出列表方法二：%s" % list_sample)
```

    5 位置上索引的值是：[1, 2, 3]
    0:4之间的切片值是：[123, 'sample', [1, 2, 3], (1, 2, 3)]
    反向输出列表方法一：[{'a': 1.0, 'b': 2}, True, (1, 2, 3), [1, 2, 3], 'sample', 123]
    反向输出列表方法二：[{'a': 1.0, 'b': 2}, True, (1, 2, 3), [1, 2, 3], 'sample', 123]


### 修改（追加、拓展、插入、取出、删除）

    append([列表元素1, 列表元素2]) - 将元素整体添加
    extend([列表元素1, 列表元素2]) - 将元素分解添加
    insert(插入的位置, 插入的元素)  - 插入元素
    pop() - 取出元素，pop一次就取出最后一个元素
    remove(要移除的元素) - 删除指定的元素
    del list_sample[元素索引位置] - 删除指定位置上的元素


```python
list_sample = [123, "sample", [1,2,3], (1,2,3), True, {"a": 1., "b": 2}]
list_sample.append([11,22])
print("**append** list is: %s" % list_sample)
list_sample.extend([33, 44])
print("**extend** list is: %s" % list_sample)
list_sample.insert(2, "list replace")
print("**insert** list is: %s" % list_sample)
list_sample.pop()
print("**pop** list is: %s" % list_sample)
list_sample.remove(123)
print("**remove** list is: %s" % list_sample)
del list_sample[0]
print("**del** list is: %s" % list_sample)
```

    **append** list is: [123, 'sample', [1, 2, 3], (1, 2, 3), True, {'a': 1.0, 'b': 2}, [11, 22]]
    **extend** list is: [123, 'sample', [1, 2, 3], (1, 2, 3), True, {'a': 1.0, 'b': 2}, [11, 22], 33, 44]
    **insert** list is: [123, 'sample', 'list replace', [1, 2, 3], (1, 2, 3), True, {'a': 1.0, 'b': 2}, [11, 22], 33, 44]
    **pop** list is: [123, 'sample', 'list replace', [1, 2, 3], (1, 2, 3), True, {'a': 1.0, 'b': 2}, [11, 22], 33]
    **remove** list is: ['sample', 'list replace', [1, 2, 3], (1, 2, 3), True, {'a': 1.0, 'b': 2}, [11, 22], 33]
    **del** list is: ['list replace', [1, 2, 3], (1, 2, 3), True, {'a': 1.0, 'b': 2}, [11, 22], 33]


### 排序 - sorted
    list_sample.sorte() - 排序后原list_sample就变成了一个新的list
    sorted(list_sample) - 排序后不改变原list的顺序


```python
list_sample = [11,55,88,66,35,42]
# list_sample.sort()
# print("sort list is: %s" % list_sample)
print("sorted list is: %s" % sorted(list_sample))
print("list is: %s" % list_sample)
print("sorted reverse list is: %s" % sorted(list_sample, reverse=True))
```

    sorted list is: [11, 35, 42, 55, 66, 88]
    list is: [11, 55, 88, 66, 35, 42]
    sorted reverse list is: [88, 66, 55, 42, 35, 11]


### 列表转换
将元组转换成列表


```python
tuple_sample = (1, 2, 3, 4)
print("list tuple is: ", list(tuple_sample))
```

    list tuple is:  [1, 2, 3, 4]


字符串转换成列表


```python
str_sample = "1213abc"
print("list str is: ", list(str_sample))
```

    list str is:  ['1', '2', '1', '3', 'a', 'b', 'c']


## 元组（tuple）
与list相似，即为不可修改的list。


```python
str_sample = "121333"
list_sample = ["1", 'B', 'C']
dict_sample = {"a":1, "b":2}
set_sample = set({1, 2, 3, "A"})
print("str tuple is: ", tuple(str_sample))
print("list tuple is: ", tuple(list_sample))
print("dict tuple is: ", tuple(dict_sample))
print("set tuple is: ", tuple(set_sample))

tuple_sample = (1,2,3,4,5)
print("tuple 切片是: %s" % tuple_sample[0])
```

    str tuple is:  ('1', '2', '1', '3', '3', '3')
    list tuple is:  ('1', 'B', 'C')
    dict tuple is:  ('a', 'b')
    set tuple is:  (1, 2, 3, 'A')
    tuple 切片是: 1


## 字典
    字典是一系列键值对，每个键值对通过逗号分割。特点：
        键必须是不可变的，可以是数字、字符串、元组、布尔值；
        键是唯一的

### 


```python
str_sample = "abc123"
int_sample = 12
list_sample = [1, 2, 3]
# print("str dict is,", dict(str_sample))
# print("int dict is,", dict(int_sample))
# print("list dict is,", dict(list_sample))

dict_sample = {
    ('ok', ): 1,
    "abc": "中文",
    True: ['abc']
}
print("dict is %s" % dict_sample)
print("dict 获取字典的键为：", dict_sample.keys())
print("dict 获取字典的值为：", dict_sample.values())
# 遍历字典元素
for i in dict_sample:
    print("%s 的值为：%s" % (i, dict_sample[i]))
```

    dict is {('ok',): 1, 'abc': '中文', True: ['abc']}
    dict 获取字典的键为： dict_keys([('ok',), 'abc', True])
    dict 获取字典的值为： dict_values([1, '中文', ['abc']])
    ('ok',) 的值为：1
    abc 的值为：中文
    True 的值为：['abc']


## 集合（set）
集合是一个无序不重复的元素集，由于集合是不重复的元素，所以可以对字符串、列表、元组进行去重。

### 创建
    set - 创建一个可变的集合
    frozenset - 创建一个不可变的集合


```python
# set_sample_error = {"ABC", "abc", 1, 2, [1,2,3]}
# print("set_sample_1 is: %s" % sett_sample_error)
set_sample_1 = {"ABC", 'abc', "test", "test", (12, 3), True}
print("set_sample_1 is: %s" % set_sample_1)
set_sample_set = set({"ABC", 'abc', "test", "test", (12, 3), True})
print("set_sample_set is: %s" % set_sample_set)
frozenset_sample = frozenset({"ABC", 'abc', "test", "test", (12, 3), True})
print("frozen_sample is %s" % frozenset_sample)

def compare_set(set_1, set_2):
    if set_1 == set_2:
        print("%s equal %s \n" % (set_1, set_2))
    else:
        print("%s not equal %s \ng" % (set_1, set_2))
compare_set(set_sample_1, set_sample_set)
compare_set(set_sample_set, frozenset_sample)
```

    set_sample_1 is: {'abc', True, 'ABC', 'test', (12, 3)}
    set_sample_set is: {(12, 3), 'abc', True, 'ABC', 'test'}
    frozen_sample is frozenset({(12, 3), 'abc', True, 'ABC', 'test'})
    {'abc', True, 'ABC', 'test', (12, 3)} equal {(12, 3), 'abc', True, 'ABC', 'test'} 
    
    {(12, 3), 'abc', True, 'ABC', 'test'} equal frozenset({(12, 3), 'abc', True, 'ABC', 'test'}) 
    


### 修改（add、update）
    add(添加元素) - 添加元素作为整体修改
    update(添加元素) - 添加元素分解成单个元素修改


```python
set_sample = {"a", "b", "c"}
set_sample.add("Hello")
set_sample.add((1,2))
print("set add is: %s" % (set_sample))
set_sample_update = {"A", "B", 1, 2}
set_sample_update.update("D")
set_sample_update.update("Hello")
print("set update is: %s" % set_sample_update)
```

    set add is: {'a', (1, 2), 'b', 'c', 'Hello'}
    set update is: {'D', 1, 2, 'H', 'l', 'A', 'o', 'e', 'B'}


### 删除（remove、pop、discard）
    remove(要移除的元素) - 删除传入要移除的元素，如果元素不存则报错
    pop() - 删除集合中任意一个元素
    discard(要移除的元素) - 删除传入要移除的元素，如果元素不存在无视不会保存 


```python
set_sample = set({"A", "B", "C", 1, (1,2,"C")})
set_sample.remove("B")
print("set remove is: %s" % set_sample)
try:
    set_sample.remove("E")
    print("set remove is: %s" % set_sample)
except Exception as e:
    print("e error is: %s" % e.with_traceback)
set_sample.pop()
print("set pop is: %s" % set_sample)
set_sample.discard("E")
print("set discard is: %s" % set_sample)
```

    set remove is: {1, (1, 2, 'C'), 'A', 'C'}
    e error is: <built-in method with_traceback of KeyError object at 0x7f28e817d2b0>
    set pop is: {(1, 2, 'C'), 'A', 'C'}
    set discard is: {(1, 2, 'C'), 'A', 'C'}


### 关系运算（&、|、-、^、子集、父集）
    A & B           - 交集，A 和 B 共同有的元素的集合
    A | B           - 并集，A 和 B 集合去重后的合集的集合
    A - B           - 差集，A 相比 B 中 A 独有的元素
    A ^ B           - 补集，A 和 B 中独有的元素
    A.issubset(B)   - A 是否是 B 的子集
    A.isupperset(B) - A 是否是 B 的父集


```python
set_sample_1 = set({"a", "c", (1, 2), True, "E"})
set_sample_11 = set({"a", "c", (1, 2), True})
set_sample_2 = set({"a", "c", (1, 2), True, 123, "a", "B"})
print("%s & %s is: %s" % (set_sample_1, set_sample_2, set_sample_1 & set_sample_2))
print("%s | %s is: %s" % (set_sample_1, set_sample_2, set_sample_1 | set_sample_2))
print("%s - %s is: %s" % (set_sample_1, set_sample_2, set_sample_1 - set_sample_2))
print("%s - %s is: %s" % (set_sample_2, set_sample_1, set_sample_2 - set_sample_1))
print("%s ^ %s is: %s" % (set_sample_1, set_sample_2, set_sample_1 ^ set_sample_2))
print("%s ^ %s is: %s" % (set_sample_2, set_sample_1, set_sample_2 ^ set_sample_1))
print("%s issubset %s is: %s" % (set_sample_1, set_sample_2,  set_sample_1.issubset(set_sample_2)))
print("%s issubset %s is: %s" % (set_sample_11, set_sample_2,  set_sample_11.issubset(set_sample_2)))
print("%s isupperset %s is: %s" % (set_sample_2, set_sample_1,  set_sample_2.issuperset(set_sample_1)))
print("%s isupperset %s is: %s" % (set_sample_2, set_sample_11,  set_sample_2.issuperset(set_sample_11)))
```

    {'a', True, (1, 2), 'c', 'E'} & {'a', True, (1, 2), 'c', 'B', 123} is: {'a', True, 'c', (1, 2)}
    {'a', True, (1, 2), 'c', 'E'} | {'a', True, (1, 2), 'c', 'B', 123} is: {'a', True, (1, 2), 'c', 'E', 'B', 123}
    {'a', True, (1, 2), 'c', 'E'} - {'a', True, (1, 2), 'c', 'B', 123} is: {'E'}
    {'a', True, (1, 2), 'c', 'B', 123} - {'a', True, (1, 2), 'c', 'E'} is: {123, 'B'}
    {'a', True, (1, 2), 'c', 'E'} ^ {'a', True, (1, 2), 'c', 'B', 123} is: {'E', 'B', 123}
    {'a', True, (1, 2), 'c', 'B', 123} ^ {'a', True, (1, 2), 'c', 'E'} is: {'E', 'B', 123}
    {'a', True, (1, 2), 'c', 'E'} issubset {'a', True, (1, 2), 'c', 'B', 123} is: False
    {'a', True, 'c', (1, 2)} issubset {'a', True, (1, 2), 'c', 'B', 123} is: True
    {'a', True, (1, 2), 'c', 'B', 123} isupperset {'a', True, (1, 2), 'c', 'E'} is: False
    {'a', True, (1, 2), 'c', 'B', 123} isupperset {'a', True, 'c', (1, 2)} is: True


### 栈（stack）


```python
# 稍后
```

### 堆（queue）


```python
# 稍后
```

# 逻辑控制
常用的逻辑控制结构有：顺序结构、选择结构 和 循环结构
    
    顺序结构：就是按照代码的编写顺序，一行一行进行顺序执行。
           

## 选择结构
     选择结构：根据条件判断进行选择性的执行代码分支。
        if...elif...else...


```python
def judge_people(name, age, score):
    if age >= 18:
        if name == "crisimple":
            if score == 100:
                print("%s is in service, he is a outstanding soldier." % name)
            else:
                print("He should go on.")
        else:
            print("%s is not in service." % name)
    else:
        print("%s is not a soldier." % age)

if __name__ == "__main__":
    judge_people("crisimple", 25, 100)
    judge_people("crisimple", 17, 100)
```

    crisimple is in service, he is a outstanding soldier.
    17 is not a soldier.


## 循环结构
    循环结构：满足一定条件，重复执行某段代码的一种编码结构。
        while循环
        for循环 - 常用于遍历字符串、列表、字典等数据结构


```python
for i in range(1, 10):
    for j in range(1, i+1):
        print("%s*%s=%s" % (j, i, (i*j)), end="   ")
    print("\n")
```

    1*1=1   
    
    1*2=2   2*2=4   
    
    1*3=3   2*3=6   3*3=9   
    
    1*4=4   2*4=8   3*4=12   4*4=16   
    
    1*5=5   2*5=10   3*5=15   4*5=20   5*5=25   
    
    1*6=6   2*6=12   3*6=18   4*6=24   5*6=30   6*6=36   
    
    1*7=7   2*7=14   3*7=21   4*7=28   5*7=35   6*7=42   7*7=49   
    
    1*8=8   2*8=16   3*8=24   4*8=32   5*8=40   6*8=48   7*8=56   8*8=64   
    
    1*9=9   2*9=18   3*9=27   4*9=36   5*9=45   6*9=54   7*9=63   8*9=72   9*9=81   
    


# IO操作
读写文件是最常见的IO操作，现代操作系统不允许普通程序直接操作磁盘，读写文件就是请求操作系统打开一个文件操作对象，通过操作系统提供的接口进行对文件的读写操作。

本文是以 txt 文件为操作对象进行数据读写操作，更多其他类型文件（csv、json、excel、yaml等），可参考[《Python 文件操作》](../OperateFile/)

## 文件读取
文件读取三步骤：

    （1）创建文件操作句柄 f_read；
    （2）使用 f_read.read() 方法读取文件中的内容；
    （3）文件读取完关闭文件（不然文件对象会占用操作系统资源）。


```python
# codecs模块：读写文件模块，用来解决文件乱码问题
import codecs

f_read = codecs.open("./data/read.txt", 'rb', encoding="utf-8")
print("f_read: \n", f_read.read())
f_read.close()
```

    f_read: 
     《青花瓷》
    天青色等烟雨
    而我在等你
    炊烟袅袅升起
    隔江千万里


## 文件写入
文件写入三步骤：

    （1）创建文件操作句柄 f_write；
    （2）使用 f_write.write() 方法把内容写入文件；
    （3）文件操作完关闭文件（不然文件对象会占用操作系统资源）。


```python
import codecs

f = codecs.open("./data/write.txt", 'wb', encoding="utf-8")
f.write("《送别》 \n")
f.write(" 长亭外，古道边。 \n")
f.write(" 芳草碧连天。 \n")
f.close()
```

## 文件操作方法
    readline() - 读取所有文件，包含特殊字符（\n、\t）；如果指定了非负数的整数，则读取整数个字节数。
    readlines() - 读取文件中的所有行，返回为列表形式。
    __next__() - 返回迭代器的下一个指向
    writelines() - 向文件中写入一系列的字符串
    tell() - 返回文件的当前位置，即文件当前位置
    seek() - 移动文件读取指针到指定位置
    name() - 读取文件名
    
    flush() - 刷新缓冲区，即将缓冲区的数据写入文件，同时清空缓冲区


```python
import codecs

fr = codecs.open("./data/read.txt", 'rb', encoding="utf-8")
# print("f.readlines is: ", fr.readlines())
print("fr.readlines is: ", fr.readline(1))
print("fr.__next__() is: ", fr.__next__())
fr.close()

fw = codecs.open('./data/write.txt', 'wb', encoding="utf-8")

fw.writelines(["a\n"])

print("fw.tell() is: ", fw.tell())
fw.seek(0)
fw.writelines(["a\n"])
print("fw.tell() is: ", fw.tell())
print("fw.name(): ", fw.name)
fw.close()
```

    fr.readlines is:  《
    fr.__next__() is:  青花瓷》
    
    fw.tell() is:  2
    fw.tell() is:  2
    fw.name():  ./data/write.txt


## 上下文管理



```python
#  在实际操作中操作完文件经常会忘记关闭文件，上下文管理会避免出现这种问题
with codecs.open("./data/read.txt", 'rb', encoding="utf-8") as f:
    print("f.read(): ", f.read())
print("f.closed()", f.closed)
```

    f.read():  《青花瓷》
    天青色等烟雨
    而我在等你
    炊烟袅袅升起
    隔江千万里
    f.closed() True


# 函数
函数 - 一段组织好的，可以多次重复使用的，用来实现单一功能或相关功能的代码段

自定义函数语法：
```python
def custom_func(elem):
    print("这是我的自定义函数...")
    print("我是参数elem: ", elem)
```

函数调用：custom_func(1)


## 参数及返回值
**函数参数**

    （1）位置参数
    （2）动态参数
             *args -- 接受的是按照位置传参的值，组成一个元组
             **kwargs -- 接受的是按关键字传参的值，组成一个字符串
参数的传递位置：位置参数、**args、默认参数、***kwargs

**函数返回值**：return 用于退出函数，选择性地向调用方法返回一个表达式，不带参数值的 return 语句返回为 None。


```python
def paraeter_func(par1, par2, *args, par_def="default", **kwargs):
    print(par1)
    print(par2)
    print(args)
    print(par_def)
    print(kwargs["name"])
    print(kwargs["age"])
paraeter_func(
    1, 
    2,
    3, 4, "a",
    name="crisimple",
    age="25"
)


def return_func(a, b):
    total = a + b
    print("函数内：", total)
    return total
return_func(1, 2)
```

    1
    2
    (3, 4, 'a')
    default
    crisimple
    25
    函数内： 3





    3



## 异常处理
异常是程序执行时发生的错误信号，当 Python 解释器检测到错误时，程序就在当前异常处终止。编写特定的异常来处理代码来专门处理代码，如果捕获到异常使程序进行预期分支而不使程序奔溃。在代码中编写异常处理程序机制来提高程序的健壮性和容错性，提升用户体验。

Python 中常见的异常：
    
    AttributeError               访问的对象没有该属性
    IOError                          输入/输出异常，基本上是无法打开文件
    ImportError                   无法引入模块或包，基本是路径或名称错误
    IndentationError           语法错误，代码没有正确对齐
    IndexError                     下标索引超出边界
    KeyError                        访问的字典里面不存在的键
    KeyboardInterrupt        Ctrl + c 被按下
    NameError                    访问一个还未被赋予对象的变量
    SyntaxError                   Python代码非法，代码不能编译
    TypeError                      传入对象类型与要求的不符合
    ValueError                     传入一个调用者不期望的值
    UnboundLocalError      访问一个还未被设置的局部变量，基本上是由于另有一个同名的全局变量
    AssertionError               断言错误，说明断言的条件为假

### try...exception...finally


```python
exce_sample = [1,2,3]
try:
    for i in exce_sample:
        print(exce_sample[i+1])
except IndexError as e:
    print("e: ", e)
except Exceptione as e:
    print("e: ", e)
finally:
    print("程序执行结束，不管异常是否被捕获，这里一定始终会执行")
```

    3
    e:  list index out of range
    程序执行结束，不管异常是否被捕获，这里一定始终会执行


### try...exception...else


```python
exce_sample = [1, 2, 3]
try:
    for i in exce_sample:
        print(exce_sample[i+1])
except IndexError as e:
    print("e: ", e)
except Exceptione as e:
    print("e: ", e)
else:
    print("只有再try语句里面的执行成功的时候，才会执行else里面的内容")
```

    3
    e:  list index out of range


### 断言


```python
try:
    assert 1 == 2
except AssertionError as e:
    print("e: ", e.with_traceback)
```

    e:  <built-in method with_traceback of AssertionError object at 0x7f28e80679e8>


## 迭代器
**迭代器** - 迭代取值的工具，迭代是每一次结果都是基于上一次结果而进行的。迭代提供了不依赖于索引而进行取值。

**可迭代对象**：内置`__iter__` 方法都为可迭代对象（str、list、tuple、set、文件对象）

**迭代器对象**：既内置`__iter__` ，又内置`__next__`方法的对象，执行`__iter__`依然是迭代器对象，执行`__next__`可以取值


```python
from collections.abc import Iterable, Iterator

def judge_type(par):
    if isinstance(par, Iterator)  :
        print("{} 是迭代器".format(par))
    elif isinstance(par, Iterable):
         print("{} 是可迭代对象".format(par))
    else:
        print("{} 既不是迭代器，也不是可迭代对象".format(par))
    
if __name__ == "__main__":
    # 可迭代对象
    str_sample = "string123"
    list_sample = [1,2,3,"A","b",[5]]
    tuple_sample = (1,2,3,"A","b")
    set_sample = set({"a", "b", 1, 2})
    judge_type(str_sample)
    judge_type(tuple_sample)
    judge_type(list_sample)
    judge_type(set_sample)
    print("\n")
    
    # 迭代器
    sample = range(10)
    judge_type(sample)
    Iterator_sample = iter(sample)
    judge_type(Iterator_sample)
    print(next(Iterator_sample))
    print(next(Iterator_sample))
```

    string123 是可迭代对象
    (1, 2, 3, 'A', 'b') 是可迭代对象
    [1, 2, 3, 'A', 'b', [5]] 是可迭代对象
    {1, 'b', 2, 'a'} 是可迭代对象
    
    
    range(0, 10) 是可迭代对象
    <range_iterator object at 0x7f3c10f1a900> 是迭代器
    0
    1


## 生成器
**生成器** 是 **迭代器**的一种，使用 yield 返回函数值，每次调用 yield 会暂停，可以使用 next() 和 send() 函数恢复生成器。常用于生成比较大的列表数据时，受制于内存大小的限制，生成器就派上用场了。


```python
generate_sample = (x*x for x in range(5))
try:
    print(next(generate_sample))
    print(next(generate_sample))
    print(next(generate_sample))
    print(next(generate_sample))
    print(next(generate_sample))
    print(next(generate_sample))
except StopIteration as e:
    print("e: ", e.with_traceback)
    
# 斐波拉契数列：0 1 1 2 3 5 8 13 21
def fib(max):
    x, y, z = 0, 0, 1
    while x < max:
        yield z
        y, z = z, y+z
        x = x + 1
    return "done."

g = fib(8)
while True:
    try:
        print(next(g))
    except StopIteration as e:
        print(e.value)
        print(e.args)
        break
```

    0
    1
    4
    9
    16
    e:  <built-in method with_traceback of StopIteration object at 0x7f28eb2b4dc8>
    1
    1
    2
    3
    5
    8
    13
    21
    done.
    ('done.',)


## 装饰器
Python的装饰器（decorators）用来拓展（在不改变原函数或类名的情况下，给函数增加新功能）原函数功能的一种函数。

**应用背景举例：**

    以开发哔哩哔哩为例，前期开发了个人空间、个人关注、钱包等功能，这些功能的访问的必须和个人账号的登录状态是挂钩的。如果不登录直接访问这些功能的话就会收到权限限制的提示。这些不同的功能又是由不同的程序员开发的，权限验证是由公共部门开发的，权限保密权限涉密等级又比较高，不能全员皆知。
    装饰器的引入就可以完美的解决这个问题。公共部门开发权限认证装饰器，需要调用权限认证的功能只需调用装饰器即可。
  
**应用场景：**
    
    引入日志
    函数执行时间统计
    执行函数前准备
    执行函数后清理数据
    权限校验（登录等）
    缓存


```python
# bilibili钱包权限验证
def authority(func):
    def auth():
        username = input("输入用户名：")
        password = input("输入密码：")
        if username == "crisimple" and password == "passwd":
            print("恭喜你登录成功...")
            func()
        else:
            print("error，请检查你的用户名或密码...")
    return auth

@authority
def wallet():
    print("这是您的钱包...")
    
    
if __name__ == "__main__":
    wallet()
```

### 固定参数


```python
def authority(func):
    def auth(user, passwd):
        username = input("请输入用户名：")
        password = input("请输入用户密码：")
        if username == user and password == passwd:
            print("......认证成功......")
            func(user, passwd)
        else:
            print("......认证失败......")
    return auth

@authority
def message(user, passwd):
    print("......您可以查看您的消息了......")
    
if __name__ == "__main__":
    message("crisimple", "123456")
```

### 动态参数


```python
def pay_auth(function_to_decorate):
    def auth(*args, **kwargs):
        input("=====请输入你的动态口令=====: ")
        function_to_decorate(*args, **kwargs)
    return auth

@pay_auth
def pay(a, b, c):
    print("......您的账户余额为动态口令之和：%s" % (a+b+c))
    

if __name__ == "__main__":
    pay(1, 2, 3)
```

### 多个装饰器
对于Python中的”@”语法糖，装饰器的调用顺序与使用 @ 语法糖声明的顺序相反。


```python
def first_decorator(function_to_decorator):
    def wrapper():
        print("This is first decorator01")
        function_to_decorator()
        print("End of the first decorator01")
    return wrapper

def second_decorator(function_to_decorator):
    def wrapper():
        print("This is second decorator02")
        function_to_decorator()
        print("End of the second decorator02")
    return wrapper

@first_decorator
@second_decorator
def func_decorator():
    print("...【This is to be decorated function】...")
    
if __name__ == "__main__":
    function_to_decorator()
```

### 内置装饰器
    staticmethod --- 静态方法，其跟成员方法的区别是没有 self 参数（相当于普通方法），并且可以在类不进行实例化的情况下调用
    classmethod --- 类方法，与成员方法的区别在于所接收的第一个参数不是 self （类实例的指针），而是cls（当前类的具体类型）
    property --- 属性，表示可以通过通过类实例直接访问的信息，对于一个类的属性，python的访问是没有限制的，但有时候我们需要对属性的访问加以限制，property可以胜任（它有三个方法，deleter，setter，getter）


```python
class Foo(object):
    def __init__(self):
        self.name = "crisimple"
        self.age = 25
    
    @staticmethod
    def static_method():
        print("静态方法就相当于普通方法，可不用传self参数，可以在类不进行实例化情况下调用。")
        
    @classmethod
    def class_method(cls):
        print(cls)
        
    @property
    def name(self):
        return self.name
    
    @name.setter
    def name(self, set_num):
        return self.name == set_num
    
    @name.getter
    def name(self):
        return self.name
    
  

if __name__ == "__main__":
    # 静态方法调用
    Foo.static_method()
    
    # 类方法调用
    Foo.class_method()
    
    # f = Foo()
   # f.name
```

### 内建函数

#### 数据处理

**abs() --- 返回数字的绝对值**


```python
a = 0
b = -1
c = 2
# d = -a1
print("%s 的绝对值为 %s" % (a, abs(a)))
print("%s 的绝对值为 %s" % (b, abs(b)))
print("%s 的绝对值为 %s" % (c, abs(c)))
# print("%s 的绝对值为 %s" % (d, abs(d)))
```

**bin()  --- 返回一个整数 int 或长整型 long int 的二进制表示**


```python
bin_1 = 10
bin_2 = 20
print("%s 经过bin后返回：%s" % (bin_1, bin(10)))
print("%s 经过bin后返回：%s" % (bin_2, bin(20)))
```

**oct() --- 将整数转换为八进制字符串**


```python
print(oct(10))
print(type(oct(10)))
```

**max() --- 返回给定参数的最大值，参数可以为序列**<br>

序列 --- 序列是是Python中最基本的数据结构。序列中的每个元素都分配一个数字 - 它的位置，或索引，第一个索引是0，第二个索引是1，依此类推。每个索引对应一个元素。Python包含 6 中内建的序列，包括列表、元组、字符串、Unicode字符串、buffer对象和xrange对象。


```python
print("返回序列的最大值：", max(100, 200, 3000, 800))
```

**min() --- 返回给定参数的最小值，参数可为序列**


```python
print("返回序列的最小值：", min(-100, 200, 0, -10000))
```

**reversed() --- 对列表进行反向输出**


```python
list_sample = [1,2,3,4,5]
tuple_sample = (1,2,3,4,5)
list_sample.reverse()
print("reverse list is: ", list_sample)
```

**zip() --- 将可迭代的对象作为参数，将对象中对应的元素打包成一个个元组，然后返回由这些元组组成的列表**<br>
**如果各个迭代器的元素个数不一致，则返回列表长度与最短的对象相同，利用 * 号操作符，可以将元组解压为列表**


```python
zip_1 = [1, 2, 3]
zip_2 = [4, 5, 6]
zip_3 = [7, 8, 9]
zip1 = zip(zip_1, zip_2)
zip2 = zip(zip_2, zip_3)
# 压缩： <zip object at 0x7f7edf5c75c8>
print("压缩：", zip1)
# print("解压：", zip(*zip1))
print(type(zip1))
for i in zip1:
    print(i)
print("\n")
for j in zip(*zip2):
    print(j)
```

**complex([real[, imag]])   创建一个值为 real + imag * j 的复数或者转化一个字符串或数为复数。如果第一个参数为字符串，则不需要指定第二个参数**<br>
real -- int, long, float或字符串<br>
imag -- int, long, float<br>


```python
print("返回一个复数：", complex(1, 2))
print("返回一个复数：", complex("1+2j"))
```

#### 数据计算

 **divmod() --- 返回一个商和余数元组**


```python
divmod_1 = -7
divmod_2 = -2
print("%s divmod %s is: %s" % (divmod_1, divmod_2, divmod(divmod_1, divmod_2)))
```

**pow(x, y) -- 指数运算，x 的 y 次方**


```python
pow_1 = -3
pow_2 = 4
print("%s pow %s is: %s" % (pow_1, pow_2, pow(pow_1, pow_2)))
```

**sum() -- 对一系列数求和**

    iterable --- 可迭代对象：列表、数组、元组、集合
    start --- 指定增加的参数，如果没有此值，默认为0


```python
sum_1 = [1, 2, 3, 4]
sum_2 = [5, 6, 7, 8]
sum_3 = [9, 10, 11, 12]
print("%s sum is: %s" % (sum_1, sum(sum_1)))
```

**sorted(iterable, cmp=None, key=None, reverse=False) --- 对可迭代对象进行排序**
    
    iterable ---可迭代对象（如：列表、元组、集合）
    cmp --- 比较的函数有两个参数，参数的值可以从迭代对象中取出，函数必须遵守：大于返回1，小于返回-1，等于返回0
    key --- 用来进行比较的元素，只有一个参数，函数的参数取自于可迭代对象中，指定可迭代对象中的一个元素来进行排序
    reverse --- 排序规则，reverse = True 降序 ， reverse = False 升序（默认）


```python
sorted_dict = [('john', 'A', 15), ('jane', 'B', 12), ('dave', 'B', 10)]
print("排序结果为：", sorted(sorted_dict, key=lambda s: s[2], reverse=True))
```

#### 输入

**input() --- 输入的字符串必须引号包起来，否则会引发 SyntaxError**<br>

*有时候我们还会看到raw_input()也可以进行用户输入，那么他们的区别是：*<br>
    
    input() --- 适用于 Python3 和 Python2，输入值必须是：字符串
    raw_input() --- 只适用于 Python2，会将输入值强制转换成 str 展示，即使输入为整数


```python
print("input: ", input("请输入："))
print("input type is: ", type(input("请输入：")))
```

#### 文件操作
    open(file_name, [,access_model][,buffering]) --- 文件操作函数 ；另外也可以用 file() 函数（一样的）进行操作；官方推荐使用open()。
           file_name: file_name变量是一个包含了你要访问的文件名称的字符串值。
           access_mode：access_mode决定了打开文件的模式：只读，写入，追加等
           buffering：如果buffering的值被设为0，就不会有寄存。如果buffering的值取1，访问文件时会寄存行。如果将buffering的值设为大于1的整数，表明了这就是的寄存区的缓冲大小。如果取负值，寄存区的缓冲大小则为系统默认。
           
      r	以只读方式打开文件。文件的指针将会放在文件的开头。这是默认模式。
     rb	以二进制格式打开一个文件用于只读。文件指针将会放在文件的开头。这是默认模式。
     r+	打开一个文件用于读写。文件指针将会放在文件的开头。
     rb+	以二进制格式打开一个文件用于读写。文件指针将会放在文件的开头。
     w	打开并只能写入。若文件已存则打开文件并从头开始编辑，原内容会被删除。若该不存在，创建新文件。
     wb	二进制格式打开文件只用于写入。若文件已存在则打开文件并从头开始编辑，即原有内容会被删除。如果该文件不存在，创建新文件。
     w+	打开一个文件用于读写。如果该文件已存在则打开文件，并从开头开始编辑，即原有内容会被删除。如果该文件不存在，创建新文件。
     wb+	以二进制格式打开文件用于读写。如果该文件已存在则打开文件从开头开始编辑原内容会被删除。如果该文件不存在，创建新文件。
     a	打开文件用于追加。若文件已存在，文件指针放在文件的结尾。新的内容会被写入已有内容。若文件不存在，创建新文件进行写入。
     ab	二进制格式打开文件用于追加。若文件已存文件指针放在文件结尾。新内容会写入到已有内容。若文件不存在，创建新文件进行写入。
     a+	打开文件用于读写。若文件已存在文件指针将放在文件的结尾。文件打开时会是追加模式。如果该文件不存在，创建新文件用于读写。
     ab+	以二进制格式打开一个文件用于追加。如果该文件已存在，文件指针将会放在文件的结尾。如果该文件不存在，创建新文件用于读写。
     
     


```python
with open('./data/read.txt', 'r', encoding='utf-8') as f:
    content = f.readline()
    print(content)
print("\n")
```

#### 帮助类函数

help() ---  查看模块或方法用途的详细说明，即帮助文档


```python
print("sys: ", help('sys'))
```

dir() --- 带参数时，返回当前范围内的变量、方法或定义的类型列表。<br>
带参数时，返回参数的属性、方法列表。如果参数包含方法`__dir__()`，该方法将被调用；<br>
如果参数不包含`__dir__()`，该方法见最大限度地手机参数信息。


```python
print("dir: ", dir())
```

id() --- 获取对象的内存地址


```python
a = 1
b = 3
c = 7
print("%s 的内存 id 为：%s" % (a, id(a)))
print("%s 的内存 id 为：%s" % (b, id(b)))
print("%s 的内存 id 为：%s" % (c, id(c)))
```

#### 

# 面向对象
对象是一个抽象概念，万物皆可对象。对象通常有静态部分（也叫属性）和 动态部分（也叫方法）。在面向对象（对象也叫类的实例）中，将函数和变量进一步封装成类，类是程序的基本组成元素，和数据操作紧密相连，并保护数据不被外界任意改变。

## 面向对象术语


```python
# 类（ClassSample）：具有相同属性和方法的集合
class ClassSample(object):
    
    # 类变量（user_name）:定义在类中但在方法体之外的变量；类变量是所有实例共有的变量
    user_name = "crisimple"
    pass_word = "123456"
    
    # __init__ 在类实例化的时候会自动调用该方法，并传递对应的参数
    def __init__(self, name, age):
        # 实例变量（name）：定义在实例中并只作用于当前实例
        self.name = name
        self.age = age
        
    # 实例方法（sample_func）:
    def sample_func(self):
        print("这是一个实例方法", self.name)
        
    # 静态方法（static_fun）:声明时不需要传参数 self；调用时不需要对类进行实例化，直接可以用类进行调用
    @staticmethod
    def static_func():
        print("这是一个静态方法")
        
    # 类方法（class_func）:类方法是将类本身作为对象进行操作的方法，采用@classmethod装饰，至少传入一个cls（指类本身，类似于self）参数，行类方法时，自动将调用该方法的类赋值给cls。
    # 调用：类名.类方法（或 实例名.类方法）
    @classmethod
    def class_func(cls):
        print("这是一个方法：", cls.user_name)        
        

if __name__ == "__main__":
    # 实例化过程
    cs1 = ClassSample("crisimple1", "25")

    # 调用实例化方法
    cs1.sample_func()
    
    # 调用静态方法
    # cs1.static_func()
    ClassSample.static_func()
    
    # 调用类方法
    cs1.class_func()
    ClassSample.class_func()
    
```

## 面向对象三大特征

### 封装
封装是指将 数据 或 具体操作 代码放在某个对象内部，使这些代码的内部细节不被外界所知，外部只能通过接口访问该对象的属性和方法，不能通过任何方法修改对象内部的实现。


```python
class SampleClass(object):
    
    user_name = "crisimple"
    pass_word = "123456"
    
    def __init__(self, name, passwd):
        self.name = name
        self.passwd = passwd
        
    def sample_func(self):
        print(self.name)
        
        
if __name__ == "__main__":
    try:
        # e:  name 'user_name' is not defined --- 说明外部无法直接访问类内部的属性
        # print(user_name)
        
        # 'set' object is not callable --- 外部无法直接访问类内部的方法
        # set_sample()
        
        # 类.属性，访问类属性；
        print(SampleClass.user_name)
        # SampleClass.sample_func("crisimple2")
        
        # 实例化对象.属性；实例化对象.方法。
        sc1 = SampleClass("crisimple2", "123456")
        sc1.sample_func()
        print(sc1.user_name)
    except Exception as e:
        print("e: ", e)

```

### 继承
继承实现了代码的复用，多个类共用的代码可以在一个类中提供，其他类只需要集成这个公共类即可。

继承的好处：子类 获得了 父类（也叫超类或基类）的全部变量和方法，还可以根据需要对子类进行修改和扩展。

继承分为：实现继承（使用基类的属性和方法无需额外编码）、接口继承（仅使用属性和方法的名称，子类实现属性和方法的具体实现，即子类重构父类方法）。

方法的继承分两种：

    （1）子类继承父类构造方法：
            经典继承写法：FatherClass.__init__(self, user_name, pass_word)
            新式继承方法：super(Child, self).__int__(self, user_name, pass_word)
    （2）子类继承父类方法：
            不重名的方法，子类可以直接访问父类的方法；
            重名的方法，子类重写父类的方法


```python
class FatherClass(object):
    
    def __init__(self, user_name, pass_word):
        self.user_name = user_name
        self.pass_word = pass_word
        self.father_property = "property"
        
    def father_func(self):
        print("print father func name is: ", self.user_name)
        
    def judge_passwd(self):
        if self.pass_word == "123":
            print("身份验证成功")
        else:
            print("请检查你的账号信息")
    
class ChildClass(FatherClass):
    #--------------子类对父类构造方法的继承--------------------
    # 遵循：先继承再重构
    def __init__(self, user_name, pass_word, ip):
        # 继承的两种写法：
        # 经典继承写法：
        # FatherClass.__init__(self, user_name, pass_word)
        # 新式继承写法：
        super(ChildClass, self).__init__(user_name, pass_word)
        # 子类构造构造新的属性
        self.ip = ip
        
    def child_func(self):
        print("print child func name is: ", self.user_name)
            
    def judge_passwd(self):
        if self.pass_word == "456":
             print("身份验证成功")
        else:
            print("请检查你的账号信息")
    
    
if __name__ == "__main__":
    
    # 实例化 子类对父类构造方法的重写
    #  实例化对象  ---> 调用子类的构造方法__init__() ---> 子类的构造方法__init__()继承父类的构造方法__init__() ---> 调用父类的构造方法__init__()
    cc1 = ChildClass("c1", "123", "10.10.10.10")
    print(cc1.user_name)
    print(cc1.pass_word)
    print(cc1.ip)
    print(cc1.father_property)
    
    # 实例化，子类对父类方法的重写
    cc2 = ChildClass("c2", "123", "11.11.11.11")
    cc2.judge_passwd()
    cc2.father_func()
    cc2.child_func()
    cc3 = ChildClass("c3", "456", "11.11.11.11")
    cc3.judge_passwd()
    
```

### 多态
多态指一类事务具有多种形态（动物类多种形态老虎、狮子）。Python 的多态是指在不考虑实例类型的情况下使用实例，也就是说不同类型的实例具有相同的调用方法。

多态的好处：
    
    （1）增加了程序的灵活性：以不变应万变，不论对象千变万化，使用同一种形式去调用，如show_say(animal)
    （2）增加了程序的可扩展性：通过继承Animal（下面代码例子）类创建了一个新的类，使用者无需更改自己的代码，还是用show_say(animal)方法去调用。


```python
# 一类事物 --- Animal
class Animal(object):
    def say(self):
        print("This is Animal.")
        
# Animal 的形态之一：Dog
class Dog(Animal):
    def say(self):
        print("wang wang~")
        
# Animal 的形态之一：Cat
class Cat(Animal):
    def say(self):
        print("miao miao~")
        
# Animal的形态之一：Sheep
class Sheep(Animal):
    def say(self):
        print("mie mie ~")
        
def animal_say(Animal):
    Animal.say()
        
if __name__ == "__main__":
    a = Animal()
    d = Dog()
    c = Cat()
    s = Sheep()
    a.say()
    d.say()
    c.say()
    s.say()
    
    # 统计接口调用动物类的say()方法
    animal_say(d)
    animal_say(s)
```

## 元类
Python中一切皆对象，用 class 关键字定义的类本身也是一个对象，负责产生该对象的类称为元类。

元类的目的：控制类产生和对象的产生过程。

类对象可以用 class 关键字创建，类对象的类型是 type，也就是说可以用 type（元类）来创建


```python
class Foo(object):
    def __init__(self, name, age):
        self.name = name
        self.age = age
        
    def introduce(self):
        print("My name is : %s" % self.name)
        
if __name__ == "__main__":
    
    int_sample = 123
    print("int_sample id is: ", id(int_sample))
    print("int_sample type is: ", type(int_sample))
    
    dict_sample = {
        "name": "test",
        "passwd": 1233
    }
    print("dict_sample id is: ", id(dict_sample))
    print("dict_sample type is: ", type(dict_sample))
    
    f = Foo("crisimple", 25)
    f.introduce()
    print("f id is:", id(f))
    print("f type is:", type(f))
    print("Foo id is:", id(Foo))
    print("Foo type is:", type(Foo))
    

# 故，用元类创建类
Person = type("Person", (object, ), {"name": "crisimple", "age": 25})
print("Person type is, ", type(Person))
p1 = Person()
print("p1 type is,", type(p1))
```

# Python高级编程

## 多进程
**多道技术**：为保证并发能力，可以将一个 cpu 变成多个虚拟的 cpu。时间多路复用和空间多路复用+硬件上支持隔离

    空间复用：如内存中同时有多道程序 
    时间复用：复用一个CPU的时间片，强调：遇到io切，占用CPU时间过长也切，核心在于切之前将进程的状态保存下来，这样才能保证下次切换回来时，能基于上次切走的位置继续运行
    
**进程**：正在进行的一个过程或一个任务，负责任务的是CPU；同一程序执行两次，那也就是两个进程，比如打开两个chrome浏览器，一个看学习视频，一个写学习笔记。

**并发**：是伪并行，看起来是同时运行，单个CPU+多道技术就可以实现并发。

**并行**：同时运行，具有多个CPU才能实现并行。

### 开启进程

multiprocessing模块

multiprocess模块用来开启子进程，并在子进程中执行我们定制的任务（如函数），支持子进程、通信和共享数据，执行不同形式的同步，提供了Process、Queue、Pipe、Lock 等组件；与线程不同，进程没有任何共享状态，进程修改的数据，改动仅限于改进程内。


```python
from multiprocessing import Process
import time
import random
import os

# 开启进程方法一：
def task(name):
    print("%s is running..." % name)
    time.sleep(random.randrange(1, 5))
    print("%s is done..." % name)
    
    
# 开启进程方法二：继承 Process 类
class ProcessSmaple(Process):
    def __init__(self, name):
        # 重用父类 Process 的功能
        super().__init__()
        self.name = name
        
    # start将调用这个run方法
    def run(self):
        print("%s %s is running..., parent id is %s" % (self.name, os.getpid(), os.getppid()))
        time.sleep(3)
        print("%s %s is done-----, parent id is %s" % (self.name, os.getpid(), os.getppid()))
    


if __name__ == "__main__":
    # 方式一：
    # 只是给操作系统发送了一个信号，由操作系统将父进程地址空间中的数据拷贝给子进程，作为子进程运行的初始状态，开启后再运行task
#     p1 = Process(target=task, args=("a", ))
#     p2 = Process(target=task, args=("b", ))
#     p3 = Process(target=task, args=("c", ))
#     p4 = Process(target=task, args=("d", ))
#     p1.start()
#     p2.start()
#     p3.start()
#     p4.start()
#     print('主1......', os.getpid(), os.getppid())

    # 方式二：
    p = ProcessSmaple('子进程2')
    p.start()
    # os.getpid() --- 查看子进程的id
    # os.getppid() --- 查看父进程的id
    print('主2......', os.getpid(), os.getppid())
```

    主2...... 312 5106
    子进程2 2122 is running..., parent id is 312
    子进程2 2122 is done-----, parent id is 312


### 主进程与子进程
在主进程运行过程中，想要并发地执行其他任务，我们可以开启一个子进程。

主进程和子进程执行分两种情况：

    （1）主进程和子进程之间执行彼此独立，主进程执行完毕后会等待子进程执行完毕后，统计回收系统资源。
    （2）主进程执行到某一阶段后，需要等待子进程执行完毕后再进行后面主进程的执行，这时候就要用 join 来判断检测子进程什么时候执行完再进行主进程的执行，也是等主进程执行完毕后，统一对主进程和子进程进行系统资源回收。
    join --- 实现进程的检测、实现子进程的并发和子进程的串行任务
    is_alive --- 判断子进程的存活状态


```python
from multiprocessing import Process
import time
import os

def task(name):
    print("%s id is: %s, is's parent id is:%s" % (name, os.getpid(), os.getppid()))
    
def concurrent_task(name, n):
    print("%s id is: %s, is's parent id is:%s" % (name, os.getpid(), os.getppid()))
    time.sleep(n)
    
def serial_task(name, n):
    print("%s id is: %s, is's parent id is:%s" % (name, os.getpid(), os.getppid()))
    time.sleep(n)
    print("%s id is: %s, is's parent id is:%s" % (name, os.getpid(), os.getppid()))
    
def spatial_isolation():
    global n
    n = 0
    print("进程内的n为：", n)
    

if __name__ == "__main__":
    # 创建子进程
    p_task = Process(target=task("task进程"), name="自定义进程名")
    p_task.start()
    print("查看子进程的存活状态：%s" % p_task.is_alive())
    # join 检测子进程完毕后再执行主进程
    p_task.join()
    print("查看子进程的存活状态：%s" % p_task.is_alive())
    print("子进程的 id is: %s, is's parent id is:%s" % (os.getpid(), os.getppid()))
    print("查看僵尸进程：%s" % p_task.pid)
    print("查看子进程的名称：%s" % p_task.name)
    print(" ")
    
    print("start 并发")
    # 并发进程，并发进行，但是得等执行最长的程序执行完毕才算结束
    concurrent_start_time = time.time()
    p_concurrent_1 = Process(target=concurrent_task, args=('并发1', 5))
    p_concurrent_2 = Process(target=concurrent_task, args=('并发2', 3))
    p_concurrent_3 = Process(target=concurrent_task, args=('并发3', 1))
    p_concurrent_1.start()
    p_concurrent_2.start()
    p_concurrent_3.start()
    p_concurrent_1.join()
    p_concurrent_2.join()
    p_concurrent_3.join()
    concurrent_end_time = time.time()
    print("并发的总耗时长：", (concurrent_end_time - concurrent_start_time))
    print(" ")
    
    print("串行")
    serial_start_time = time.time()
    p_serial_1 = Process(target=serial_task, args=("串行1", 5))
    p_serial_2 = Process(target=serial_task, args=("串行2", 3))
    p_serial_3 = Process(target=serial_task, args=("串行3", 6))
    p_serial_1.start()
    p_serial_1.join()
    p_serial_2.start()
    p_serial_2.join()
    p_serial_3.start()
    p_serial_3.join()
    serial_end_time = time.time()
    print("串行任务总耗时长: ", (serial_end_time - serial_start_time))
    print(" ")
    
    # 进程之间的变量是相互隔离的
    p_spatial_isolation = Process(target=spatial_isolation)
    p_spatial_isolation.start()
    
```

### 守护进程
如果有多个任务需要并发执行，如果子进程任务结束后在主进程没有存在的必要了，那么可以改子进程可以被设置成守护进程（子进程执行完后，被设置的守护进程会被立即终止），未设置守护进程的子进程会等待主进程执行完毕后，统一被系统回收。

注意：守护进程内无法再开启子进程，否则会抛出异常：AssertionError: daemonic processes are not allowed to have children。


```python
from multiprocessing import Process
import time
import os

def task_1(name, n):
    print("%s id is: %s, it's parent id is: %s" % (name, os.getpid(), os.getppid()))
    time.sleep(n)
    print("%s id is: %s, it's parent id is: %s" % (name, os.getpid(), os.getppid()))
    
def task_2(name, n):
    print("%s id is: %s, it's parent id is: %s" % (name, os.getpid(), os.getppid()))
    time.sleep(n)
    print("%s id is: %s, it's parent id is: %s" % (name, os.getpid(), os.getppid()))
    
def task_3(name, n):
    print("%s id is: %s, it's parent id is: %s" % (name, os.getpid(), os.getppid()))
    time.sleep(n)
    print("%s id is: %s, it's parent id is: %s" % (name, os.getpid(), os.getppid()))
    

if __name__ == "__main__":
    p_task_1 = Process(target=task_1, args=("task_1_name", 5))
    p_task_2 = Process(target=task_2, args=("task_2_name", 2))
    # 要在p.start()前设置, 设置p为守护进程, 禁止p创建子进程, 并且父进程代码执行结束, p即终止运行
    p_task_2.daemon = True
    p_task_1.start()
    p_task_2.start()
    print("%s 是否存活：%s" % (p_task_2, p_task_2.is_alive()))
    print("%s 是否存活：%s" % (p_task_1, p_task_1.is_alive()))
    print("主进程name: ", os.name)
```

### 互斥锁
通过添加互斥锁的位置，实现部分程序达到串行的效果，其他程序任然可以并行执行，而添加了 join 只能执行完了之后才能执行下一个。

添加互斥锁的目的：保证数据输出不错乱

应用场景：12306抢票、微信群抢红包

关于 json 处理的几种场景：https://www.cnblogs.com/hjianhui/p/10387057.html


```python
from multiprocessing import Process, Lock
import time
import json

# 模拟 12306 抢票
def search_ticket(name, tickets):
    nums = json.loads(tickets, encoding="utf-8")
    print("%s 查看当前余票有：【%s】张" % (name, nums["count"]))
        
def buy_ticket(name, tickets):
    nums = json.loads(tickets, encoding="utf-8")
    if nums["count"] > 0:
        nums["count"] -= 1
        # ******** 这块有问题 *********************
        time.sleep(3)
        print("%s 购票成功，当前余票：【%s】张" % (name, nums["count"]))
    else:
        print("%s, 抱歉！暂无余票")
        
def ticket_task(name, tickets, mutex):
    # 每个人都可以同时进行票务查询，是并发操作
    search_ticket(name, tickets)
    # 添加互斥锁，达到多人同时买票时串行执行，使得一次只能一个人成功买票
    mutex.acquire()
    buy_ticket(name, tickets)
    mutex.release()
    

if __name__ == "__main__":
    # 总票仓
    tickets_json = '{"count": "10"}'
    
    # search_ticket("crisimple", tickets_json)
    mutex = Lock()
    for i in range(20):
        pt = Process(target=ticket_task, args=("旅客%s" % i, tickets_json,mutex))
        pt.start()
        # 利用互斥锁，可以通过添加互斥锁的位置，实现部分程序执行达到串行的效果，其他程序仍然可以并行执行，而添加了join只能执行完了之后才能执行下一个，若作为每项都添加一个join，则都要串行执行。从而大大降低了效率。
        pt.join()
```

### 队列
Queue([maxsize]):创建共享的进程队列，Queue是多进程安全的队列，可以使用Queue实现多进程之间的数据传递。

    参数：
    maxsize---队列中最大的项数，可以放置任意类型的数据，省略则无大小限制。
           --- 但是：
                    队列内存放的是消息而非大数据
                    队列占用的是内存空间，因而maxsize即便是无大小限制也受限于内存大小
    方法：
    q.put --- 用以插入数据到队列中，数据不宜过大
    q.get --- 可以从队列读取并删除一个元素


队列的意义：解决大家共享硬盘文件，效率低以及使用内存解决加锁这个繁琐的步骤。multiprocessing模块提供了IPC(internet process communicate)进程之间的通信，队列以及管道，这两种方式都是使用消息传递的，队列就是管道加锁的实现。




```python
from multiprocessing import Process, Queue

q = Queue(3)
q.put(1)
q.put(2)
print("当前队列是否已满：", q.full())
q.put(3)
# 判断队列是否满了
print("当前队列是否已满：", q.full())
try:
    q.put(4, block=True, timeout=3)
except:
    print("队列已满，当前队列的深度为：%s" % q.qsize())

    
print(q.get())
print(q.get())
print("当前队列是否已空：%s" % q.empty())
print(q.get())
# 判断队列是否为空
print("当前队列是否已空：%s" % q.empty())
try:
    q.get(block=True, timeout=3)
except:
    print("队列已空，当前队列的深度为：%s" % q.qsize())
```

### 生产者消费者模型
**队列阻塞模式的生产者消费者模型**

生产者（生产数据的任务），消费者（处理数据的任务）。生产者消费者模式是通过一个容器来解决生产者和消费者的强耦合问题。

生产者和消费者之间不直接通讯，而通过阻塞队列来进行通讯，所以生产者生产完数据之后不用等待消费者处理，直接给阻塞队列，消费者直接从阻塞队列里取。阻塞队列就相当于一个缓冲区，平衡了生产者和消费者的处理能力，阻塞队列就是用来给生产者和消费者解耦的


```python
from multiprocessing import Process, Queue
import time

def producer(q, name):
    for i in range(3):
        res = "包子%s" % i
        time.sleep(0.5)
        print("%s 生产了 %s" % (name, res))
        
        q.put(res)
        
        
def consumer(q, name):
    while True:
        res = q.get()
        if res is None:
            break
        time.sleep(1)
        print("%s 吃了%s" % (name, res))


if __name__ == "__main__":
    # 队列容器
    q = Queue()

    # 生产者们
    p1 = Process(target=producer, args=(q, '生产者1'))
    p2 = Process(target=producer, args=(q, '生产者2'))
    p3 = Process(target=producer, args=(q, '生产者3'))

    # 消费者们
    c1 = Process(target=consumer, args=(q, '消费者1'))
    c2 = Process(target=consumer, args=(q, '消费者2'))

    p1.start()
    p2.start()
    p3.start()
    c1.start()
    c2.start()

    # 生产完了才开始吃
    p1.join()
    p2.join()
    p3.join()
    q.put(None)
    q.put(None)
    print("主进程")

```

**共享的信号和条件变量的生产者与消费者**

JoinableQueue对象中队列允许羡慕的使用者通知生产者项目已经被成功处理，通知进程是使用共享的信号和条件变量来实现的。

    参数
        maxsize --- 队列中允许的最大项数，省略则无大小限制；

    方法
        JoinableQueue的方法共用与Queue的方法
        q.task_done() --- 使用者使用此方法发出信号，表示q.get()的返回项目已经被处理。如果调用此方法的次数大于从队列中删除项目的数量，将引发ValueError异常
        q.join() --- 生产者调用此方法进行阻塞，直到队列中所有的项目均被处理。阻塞将持续到队列中的每个项目均调q.task_done（）方法为止


```python
from multiprocessing import Process, Queue, JoinableQueue
import time

def producer_j(qj, name):
   for i in range(3):
       res = "包子%s" % i
       time.sleep(0.5)
       print("%s 生产了 %s" % (name, res))
       qj.put(res)
   qj.join()

def consumer_j(qj, name):
   while True:
       res = qj.get()
       if res is None:
           break
       time.sleep(1)
       print("%s 吃了%s" % (name, res))
       qj.task_done()


if __name__ == "__main__":
   # ------------------------
   qj = JoinableQueue()
   # 生产者们
   pj1 = Process(target=producer_j, args=(qj, "生产者j1"))
   pj2 = Process(target=producer_j, args=(qj, "生产者j2"))
   pj3 = Process(target=producer_j, args=(qj, "生产者j3"))
   # 消费者们
   cj1 = Process(target=consumer_j, args=(qj, "消费者j1"))
   cj2 = Process(target=consumer_j, args=(qj, "消费者j2"))
   cj1.daemon = True  # 若不添加守护进程，则会卡在消费者
   cj2.daemon = True

   pj1.start()
   pj2.start()
   pj3.start()
   cj1.start()
   cj2.start()
   pj1.join()
   pj2.join()
   pj3.join()
   print('JoinableQueue主进程')

```

## 多线程
**线程**：把进程当做车间，那么就可以把线程看做是车间里的流水线，这个流水线必须属于一个车间，即一个进程至少得有一个线程，进程负责把线程整合起来。

**多线程**：在一个进程中存在多个线程，多个线程共享进程的地址空间（相当于一个车间内有多条流水线，多条流水线共用这个车间的资源）。

### 开启线程
**开始线程有两种方法**：
    
    （1）调用 Thread 类的方法；
    （2）继承 Thread 类
    
    
**Thread 对象的方法**：

    isAlive() --- 返回线程是否运行
    getName() --- 返回线程名
    setName() --- 设置线程名
    
    
**threading 模块的方法**：

    threading.currentThread() --- 返回当前线程的变量
    threading.enumerate() --- 返回包含 正在运行（正在运行指线程启动后、结束前，不包含启动前和终止后的线程） 的线程的list。
    threading.activeCount() --- 返回正在运行的线程数量，结果 == len(threading.enumerate())
    


```python
from threading import Thread, currentThread, enumerate, activeCount
import random
import time

def thread_one(name):
    print("%s is running" % name)
    time.sleep(random.randrange(1, 5))
    print("%s run end." % name)
    
    
class ThreadTwo(Thread):
    def __init__(self, name):
        super().__init__()
        self.name = name
        
    def run(self):
        print("%s is running" % self.name)
        time.sleep(random.randrange(1, 5))
        print("%s run end." % self.name)
        

if __name__ == "__main__":
    # 创建线程第一种方式
    to = Thread(target=thread_one, args=("第一种创建线程的方式...", ))
    print("%s 线程名称：%s" % (to, currentThread().getName()))
    print("%s 线程是否存活：%s" % (to, to.isAlive()))
    print("当前存在线程：%s" % enumerate())
    print("当前存在线程数：%s" % len(enumerate()))
    print("当前存在线程数：%s" % activeCount())
    to.start()
    print("%s 线程是否存活：%s" % (to, to.isAlive()))
    print("\n主线程一")
    print("%s 线程名称：%s" % (to, currentThread().getName()))

    # 创建线程第二种方式
    tt = ThreadTwo('第二种创建线程的方式...')
    tt.start()
    print("\n主线程二")
    print("%s 线程是否运行1：%s" % (tt, tt.isAlive()))
    # 获取线程的名称
    print("%s 的名称叫：%s" % (tt, tt.getName()))
    # 设置新的线程名称
    tt.setName("这是新的线程名称")
    print("%s 的名称叫：%s" % (tt, tt.getName()))
    print("%s 线程是否运行2：%s" % (tt.getName(), tt.isAlive()))
    print("当前存在线程：%s" % enumerate())
    print("当前存在线程数：%s" % len(enumerate()))
    print("当前存在线程数：%s" % activeCount())
```

### 多进程与多线程的区别
    （1）启动速度：t.start() 的同时，线程就开启了；p.start() 将开启进程的信号发给操作系统后，操作系统要shenqing内存空间，拷贝子进程到父进程的地址空间，开销远大于线程。
    （2）PID 不同：同一进程下的多个线程的 pid 和所在进程的 pid 一样；主进程下开启多个进程，每个进程都有自己独立的 pid；
    （3）地址空间划分不一样：同一进程内的多个线程共享该进程的地址空间；主进程下的多个进程不共享地址空间，各个进程之间的地址空间是互相隔离的。


```python
from threading import Thread, currentThread 
from multiprocessing import Process, current_process
import time
import random
import os


def thread_func(name):
    print("%s thread is running..." % name)
    time.sleep(random.randrange(1, 3))
    print("%s thread is run done..." % name)
    print("%s id is: %s; parent id is: %s" % (name, os.getpid(), os.getppid()))
    
def process_func(name):
    print("%s process is running..." % name)
    time.sleep(random.randrange(1, 3))
    print("%s process run done..." % name)
    print("%s id is: %s; parent id is: %s" % (name, os.getpid(), os.getppid()))
    
n = 100
def address_func(name, par):
    global n
    n = 0
    n = n + par
    print("%s 的 n 的值为：%s" % (name, n))
    
    
if __name__ == "__main__":
    # 1、开启速度：通过结果对比明显可以看出线程的开启速度比进程以肉眼可见的速度快
    # 2、pid 不同：同一主进程下，多线程中每个线程的 pid 是一样的；同一主进程下，多进程中每个进程的 pid 均不同
    # 3、
    pf_1 = Process(target=process_func, args=("process_1", ))
    pf_2 = Process(target=process_func, args=("process_2", ))
    pf_1.start()
    pf_2.start()
    print("\n当前进程名称：%s" % current_process())
    
    
    tf_1 = Thread(target=thread_func, args=("thread_1", ))
    tf_2 = Thread(target=thread_func, args=("thread_2", ))
    tf_1.start()
    tf_2.start()
    print("\n当前线程名称：%s" % currentThread().getName())
    
    p_af_1 = Process(target=address_func, args=("address_func_p_1", 100))
    p_af_2 = Process(target=address_func, args=("address_func_p_2", 200))
#     p_af_1.start()
#     p_af_2.start()
    t_af_1 = Thread(target=address_func, args=("address_func_t_1", 100))
    t_af_2 = Thread(target=address_func, args=("address_func_t_2", 200))
    t_af_1.start()
    t_af_2.start()
```

### 守护线程
无论是线程还是进程，都遵循：守护 xxx 非等待主 xxx 运行完毕后被销毁

    （1）对于主进程来说，运行完毕指的是主进程代码运行完毕，主进程在代码结束后就算运行完毕了（守护进程在此时就被回收了）；然后主进程会一直等待非守护子进程运行完毕后回收子进程的资源，否则非产生僵尸进程，才会结束。
    （2）对于主线程来说，运行完指的是主线程所在的进程内所有非守护线程统统运行完毕，主线程才算运行完毕。主线程在其他非守护线程运行完毕才算运行完毕（守护线程在此时会被回收）。因为主线程的结束意味着进程的结束，进程整体的资源都将被回收，而进程保证非守护线程都运行完毕后才结束。


```python
from threading import Thread, currentThread
import time
import random
import os

def thread_func(name):
    print("%s id is: %s, it's parent id is: %s" % (name, os.getpid(), os.getppid()))
    time.sleep(random.randrange(1, 3))
    

if __name__ == "__main__":
    tf_1 = Thread(target=thread_func, args=("thread_1", ))
    tf_2 = Thread(target=thread_func, args=("thread_2", ))
    tf_1.daemon = True
    tf_1.start()
    tf_2.start()
    print("\n%s 的当前是否运行：%s" % (tf_1, tf_1.isAlive()))
    print("\n%s 的当前是否运行：%s" % (tf_2, tf_2.isAlive()))
    print("\n当前主线程名字为：%s，id 为：%s" % (currentThread().getName(), os.getppid()))
    print("\n%s 的当前是否运行：%s" % (tf_1, tf_1.isAlive()))
    print("\n%s 的当前是否运行：%s" % (tf_2, tf_2.isAlive()))
```

### 互斥锁
线程中的互斥锁的目的：一个进程内的多个线程是共享彼此的地址空间，因此彼此之间数据也是共享的，因此带来的竞争可能将数据改乱。


```python
from threading import Thread, Lock
import os
import time
import random

n1 = 100
n2 = 100

def thread_func1(name):
    global n1
    temp = n1
    # 未加锁，多线程们都等在这，此时 temp=99
    time.sleep(0.1)
    n1 = temp -1
    print("n1: ", n1)

def thread_func2(name, mutex):
    global n2
    # 加锁
    mutex.acquire()
    temp = n2
    time.sleep(0.1)
    n2 = temp - 1
    # 解锁
    mutex.release()
    print("n2: ", n2)
    
    
if __name__ == "__main__":
    tf_1 = []
    for i in range(10):
        t = Thread(target=thread_func1, args=("Thread", ))
        tf_1.append(t)
        t.start()
    for j in tf_1:
        t.join()
    
    print("\n 加锁以后，变量一次只复制给一个线程\n")
    mutex = Lock()
    tf_2 = []
    for i in range(10):
        t = Thread(target=thread_func2, args=("Thread", mutex))
        tf_1.append(t)
        t.start()
    for j in tf_2:
        t.join()
    
```

### GIL 全局解释器锁

### 信号量、Event、定时器
信号量：信号量也是一把锁，对比互斥锁同一时间只能有一个任务进行加锁执行，信号量同一时间可以指定多个任务进行加锁执行。


```python
from threading import Thread, Semaphore, currentThread

# 定义信号量的大小，也就是同一时间可以加锁的任务个数
sm = Semaphore(3)

n = 100
def thread_func(name):
    # 加锁
    global n
    sm.acquire()
    temp = n
    time.sleep(0.1)
    n = temp - 1
    print("%s's name is: %s, id is: %s." % (name, currentThread().getName(), os.getpid()))
    print("n = ", n)
    # 解锁
    sm.release()
    
if __name__ == "__main__":
    for i in range(10):
        t = Thread(target=thread_func, args=("thread", ))
        t.start()
    
```

    Exception in thread Thread-7:
    Traceback (most recent call last):
      File "/usr/lib/python3.6/threading.py", line 916, in _bootstrap_inner
        self.run()
      File "/usr/lib/python3.6/threading.py", line 864, in run
        self._target(*self._args, **self._kwargs)
      File "<ipython-input-3-5a3985f56265>", line 12, in thread_func
        time.sleep(0.1)
    NameError: name 'time' is not defined
    
    Exception in thread Thread-5:
    Traceback (most recent call last):
      File "/usr/lib/python3.6/threading.py", line 916, in _bootstrap_inner
        self.run()
      File "/usr/lib/python3.6/threading.py", line 864, in run
        self._target(*self._args, **self._kwargs)
      File "<ipython-input-3-5a3985f56265>", line 12, in thread_func
        time.sleep(0.1)
    NameError: name 'time' is not defined
    
    Exception in thread Thread-6:
    Traceback (most recent call last):
      File "/usr/lib/python3.6/threading.py", line 916, in _bootstrap_inner
        self.run()
      File "/usr/lib/python3.6/threading.py", line 864, in run
        self._target(*self._args, **self._kwargs)
      File "<ipython-input-3-5a3985f56265>", line 12, in thread_func
        time.sleep(0.1)
    NameError: name 'time' is not defined
    


**Event**: 每个线程都是独立运行且状态不可预测的，如果某些程序需要通过某个线程的状态来确定下一步的操作，那就用Event。初始情况下，Event对象中信号标志被设置为假；如果有线程等待一个Event对象，而这个对象的标志为假，那么这个线程将会被一直阻塞到该标志为真，一个线程如果将Event对象的信号标志设置为真，它将唤醒所有等待这个Event对象的线程。如果一个线程等待一个已经被设置为真的Event对象，则直接忽略这个时间继续执行。
**Event对象就像一个红绿灯一样来控制前后车辆（线程）的运行。**

应用场景：有多个工作线程尝试链接MySQL，我们想要在连接前确保MySQL服务正常才让那些工作线程去连接MySQL服务器，如果连接不成功，都会去尝试重新连接。那么我们就可以采用threading.Event机制来协调各个工作线程的连接操作

    event.isSet()：返回event的状态值；
    event.wait()：如果 event.isSet()==False将阻塞线程；
    event.set()： 设置event的状态值为True，所有阻塞池的线程激活进入就绪状态， 等待操作系统调度；
    event.clear()：恢复event的状态值为False。


```python
from threading import Thread, Event, currentThread

event = Event()

def connect_mysql():
    n = 0 
    while not event.is_set():
        print("event.is_event: ", event.is_set())
        if n==3:
            print(currentThread().getName())
            return
        print("%s try %s" % (currentThread().getName(), n))
        event.wait(0.5)
        n += 1
    print("%s is connected" % currentThread().getName())
    
def check():
    print("%s is checking" % currentThread().getName())
    time.sleep(1)
    event.set()
    

if __name__ == "__main__":
    for i2 in range(3):
        t = Thread(target=connect_mysql)
        t.start()
    t = Thread(target=check)
    t.start()
```

**Timer**：定时器，指定 n 秒后执行某操作


```python
from threading import Timer

def timer_func():
    print("定时器，指定 n 秒后执行某操作")
    

if __name__ == "__main__":
    t = Timer(3, timer_func)
    t.start()
```

### 线程队列queue
线程队列用在多个线程之间交换信息安全。


```python
import queue

# 1. 先进先出
first_in_first_out = queue.Queue(5)
first_in_first_out.put('first')
first_in_first_out.put(2)
first_in_first_out.put('third')
# block = True时阻塞，timeout=3，等待三秒后如果还没有从里面取出数据，则阻塞
first_in_first_out.put(4, block=True, timeout=3)
print(first_in_first_out.get())
print(first_in_first_out.get())
print(first_in_first_out.get())
print(first_in_first_out.get(block=False))
print("\n")


# 2. 后进先出
last_in_first_out = queue.LifoQueue(3)
last_in_first_out.put("L1")
last_in_first_out.put("L2")
last_in_first_out.put("L3")
print(last_in_first_out.get())
print(last_in_first_out.get())
print(last_in_first_out.get())
print("\n")


# 3. 优先级队列（存储数据时可设置优先级的队列）
priority = queue.PriorityQueue(3)
priority.put((10, 'one'))
priority.put((40, 'two'))
priority.put((20, 'three'))
print(priority.get())
print(priority.get())
print(priority.get())

```

### 进程池与线程池
解决多线程或多进程实现并发的套接字通信会使服务的开启的进程或线程数都会随着开发的客户端数增多最后可能因不堪重负而瘫痪，进程池或线程池的用途就是对服务端开启的进程数或线程数加以控制，让程序自己可以在一个可承受的范围内运行。

    concurrent.futures  模块提供了高度封装的异步调用接口
    ThreadPoolExecutor：线程池，提供异步调用
    ProcessPoolExecutor: 进程池，提供异步调用

    基本方法：
    submit(fn, *args, **kwargs)     --- 异步提交任务
    map(func, *iterables, timeout=None, chunksize=1)  --- 取代for循环submit的操作
    shutdown(wait=True)     --- 相当于进程池的pool.close()+pool.join()操作
                        wait=True，等待池内所有任务执行完毕回收完资源后才继续
                        wait=False，立即返回，并不会等待池内的任务执行完毕
                    但不管wait参数为何值，整个程序都会等到所有任务执行完毕
                    submit和map必须在shutdown之前
    result(timeout=None)    --- 取得结果
    add_done_callback(fn)   --- 回调函数


```python
from concurrent.futures import ProcessPoolExecutor, ThreadPoolExecutor
import time
import os
import random

def task(name):
    print("name: %s pid: %s run" % (name, os.getpid()))
    time.sleep(random.randrange(1, 3))


if __name__ == "__main__":
    # 设置最大同时运行的进程数
    # p = ProcessPoolExecutor(4)
    p = ThreadPoolExecutor(4)
    for i in range(10):
        # 异步提交任务，提交后不用管进程是否执行
        p.submit(task, '任务 %s' % i)
    # 将进程池的入口关闭，等待任务提交结束后才执行后面的任务, 默认wait=True
    p.shutdown(wait=True)
    print("主进程")
```

### 异步调用和回调机制
**同步调用**：提交完任务后，就在原地等待任务执行完毕，拿到结果再执行下一行代码，导致程序使串行执行，同步时提交任务的一种方式，不是阻塞的结果

**异步调用**：提交完任务后，不等待任务执行完毕。


```python
from concurrent.futures import ThreadPoolExecutor
import time
import random

def swim(name):
    print("%s is swimming" % name)
    time.sleep(random.randint(1, 5))
    swim_len = random.randint(10, 20)
    return {"name": name, 'swim_len': swim_len}

def distance(swim_res):
#      swim_res = swim_res.result()
    name = swim_res['name']
    s_length = swim_res['swim_len']
    print("%s 游了 %s km" % (name, s_length))


if __name__ == '__main__':
    # 1. 同步调用
    pool = ThreadPoolExecutor(13)
    swim_res1 = pool.submit(swim, 'A').result()
    distance(swim_res1)
    swim_res2 = pool.submit(swim, 'B').result()  # result取得结果
    distance(swim_res2)
    swim_res3 = pool.submit(swim, 'C').result()
    distance(swim_res3)

    # 2. 异步调用
#     pool = ThreadPoolExecutor(13)
#     pool.submit(swim, 'AA').add_done_callback(distance)
#     pool.submit(swim, 'BB').add_done_callback(distance)
#     pool.submit(swim, 'CC').add_done_callback(distance)

```

## 协程
**协程**：协程，又称微线程，纤程。英文名Coroutine。协程其实可以认为是比线程更小的执行单元，他自带CPU上下文。这样只要在合适的时机，我们可以把一个协程切换到另一个协程。只要这个过程中保存或恢CPU上下文那么程序还是可以运行的。

**对比线程和进程**:线程和进程都有抢占式特点，线程和进程之间的切换我们是不能参与的。协程是非抢占式的，协程的切换是由用户来控制的，协程主要解决的是IO的操作。

**协程的优点**:
    
    （1）协程的切换是子程序切换，是由程序自身控制，没有线程切换的开销，和多线程比线程的数量越多，协程的性能优势越明显；
    （2）不需要多线程锁的机制，因为只有一个线程，也不存在同时写变量的冲突。在协程中共享资源不需要加锁，只需要判断状态就好了。所以执行效率比多线程好。
    
**如何高效利用多核CPU呢？**:最简单的方法是多进程+协程，既充分利用多核，又充分发挥协程的高效率，可获得极高的性能。

### yield
这就是生成器中的关键词 yield，生成器中 yield 只有在调用时才执行。


```python
import time

def task1(name):
    for i in range(3):
        print("%s is running...%s" % (name, i))
        yield
        time.sleep(1)

def task2(name):
    for i in range(3):
        print("%s is running...%s" % (name, i))
        yield
        time.sleep(1)

def main():
    g1 = task1('任务1')
    g2 = task2('任务2')
    for i in range(3):
        next(g1)
        next(g2)
    print("执行完毕")


if __name__ == "__main__":
    main()

```

# Python的内存管理
Python有两种垃圾回收机制：

**引用计数**：当数据的引用数变成0的时候，python解释器就认为这个数据是垃圾数据，进行垃圾回收，释放空间

**分代回收**：通过对象存在的时间不同，采用不同的算法来回收垃圾，形象的比喻, 三个链表,零代链表上的对象(新创建的对象都加入到零代链表),引用数都是一,每增加一个指针,引用加一,随后python会检测列表中的互相引用的对象,根据规则减掉其引用计数. GC算法对链表一的引用减一,引用为0的,清除,不为0的到链表二,链表二也执行GC算法,链表三一样. 存在时间越长的数据,越是有用的数据.

