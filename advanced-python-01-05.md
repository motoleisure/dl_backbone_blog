- [Youtube-Advanced Python](https://www.youtube.com/watch?v=QLTdOEn79Rc&list=PLqnslRFeH2UqLwzS0AwKDKLrpYBKzLBy2&index=1)

## 01, List: ordered, mutable, allows duplicate elements
- 数组：有序的，可变的，允许重复元素

- list.remove
- list.clear
- list.sort()
- sorted(list)
- list = [0] * 5
- list1 + list2
- list.insert(idx, new_element)
- list[::-1], reverse 
- list.copy(), otherwise, list1 = list2, they are refer to the same address, that's bad

## 02, Tuple: ordered, immutable, allows duplicate elements
- 元组：有序的，不可变的，允许重复元素

- tuple.count('elem')
- tuple.index('elem')
- list(tuple1), tranfer to list
- tuple.copy()


```python
tp1 = (0, 2, 3, 4, 5, 7)
i1, *i2, i3 = tp1
print(i1)
print(*i2)
print(i3)
```

    0
    2 3 4 5
    7



```python
import sys
lst1 = [0, 1, 2, 'hello', True]
tpl1 = (0, 1, 2, 'hello', True)
print(sys.getsizeof(lst1), 'bytes')
print(sys.getsizeof(tpl1), 'bytes')
```

    112 bytes
    96 bytes



```python
import timeit
print(timeit.timeit(stmt="[0, 1, 2, 3, 4, 5]", number=10000000))
print(timeit.timeit(stmt="(0, 1, 2, 3, 4, 5)", number=10000000))
```

    0.3781467250009882
    0.045868095998230274


## 03, Dictionary: key-value pairs, unordered, mutable
- 字典：键值对，无序的，可变的

- dict[key] = value
- del dict[key]
- dict.popitem(), pop last key-value
- dict.copy()
- dict1.update(dict2)


```python
dict1 = {"name":"Max", "age":28, "email":"max@xyz.com"}
dict2 = dict(name="Mary", age=27, city="Boston")

dict1.update(dict2)
print(dict1)
```

    {'name': 'Mary', 'age': 27, 'email': 'max@xyz.com', 'city': 'Boston'}



```python
tpl1 = (8,7)
dict3 = {tpl1: 15}
print(dict3)
```

    {(8, 7): 15}



```python
l1 = [8,7]
dict3 = {l1: 15}
print(dict3)
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-9-dc5d8192d542> in <module>
          1 l1 = [8,7]
    ----> 2 dict3 = {l1: 15}
          3 print(dict3)


    TypeError: unhashable type: 'list'


## 04, Sets: unordered, mutable, no duplicates
- 集合：无序的，可变的，不允许重复元素


```python
myset = {1, 2, 3}
print(myset)
myset = set("Hello")
print(myset)

```

    {1, 2, 3}
    {'o', 'H', 'l', 'e'}



```python
myset.add(1)
myset.add(2)
print(myset)
```

    {'o', 'e', 'l', 1, 2, 'H'}


- myset.pop()
- myset.copy()


```python
odds = {1, 3, 5, 7, 9}
evens = {0, 2, 4, 6, 8}
primes = {2, 3 ,5, 7}
u = odds.union(evens)
print(u)
```

    {0, 1, 2, 3, 4, 5, 6, 7, 8, 9}



```python
i1 = odds.intersection(evens)
print(i1)
i2 = odds.intersection(primes)
print(i2)
```

    set()
    {3, 5, 7}



```python
# 我有你没有的
d1 = odds.difference(primes)
print(d1)
d2 = primes.difference(odds)
print(d2)
```

    {1, 9}
    {2}



```python
# 删除共同元素
sd1 = odds.symmetric_difference(primes)
print(sd1)
sd2 = primes.symmetric_difference(odds)
print(sd2)
```

    {1, 2, 9}
    {1, 2, 9}



```python
# update, 
odds.update(evens)
print(odds)
```

    {0, 1, 2, 3, 4, 5, 6, 7, 8, 9}



```python
setA = {1, 2, 3, 4}
setB = {3, 4, 5, 6}
# 保留共同元素
setA.intersection_update(setB)
print(setA)
```

    {3, 4}



```python
setA = {1, 2, 3, 4}
setB = {3, 4, 5, 6}
setA.difference_update(setB)
print(setA)
```

    {1, 2}



```python
setA = {1, 2, 3, 4}
setB = {3, 4, 5, 6}
setA.symmetric_difference_update(setB)
print(setA)
```

    {1, 2, 5, 6}



```python
# issubeset
setA = {1, 2, 3, 4}
setB = {3, 4, 5, 6}
print(setA.issubset(setB))
```

    False



```python
# isdisjoint(), 如果2个集合没有共同元素，返回True
setA = {1, 2, 3, 4}
setB = {3, 4, 5, 6}
print(setA.isdisjoint(setB))
setC = {5, 6}
print(setA.isdisjoint(setC))
```

    False
    True



```python
a = frozenset([1, 2 ,3 ,4])
#a.add(5)
a.remove(1)
print(a)
```


    ---------------------------------------------------------------------------

    AttributeError                            Traceback (most recent call last)

    <ipython-input-34-c50e76109b8e> in <module>
          1 a = frozenset([1, 2 ,3 ,4])
          2 #a.add(5)
    ----> 3 a.remove(1)
          4 print(a)


    AttributeError: 'frozenset' object has no attribute 'remove'


## 05, Strings: ordered, immutable, text representation
- 字符串：有序的，不可变的，文字表示


```python
mystring1 = ""
mystring2 = """hellow \
world"""
print(mystring2)
```

    hellow world



```python
substring = mystring2[3:]
print(substring)
```

    low world



```python
greeting = "Hello"
name = "Tim"
print(greeting + ' ' + name)
```

    Hello Tim



```python
mystring = "      hello world   a  "
print(mystring)
print(mystring.strip())
```

          hello world   a  
    hello world   a


- str1.startsWith()
- str1.endsWith()
- str1.find()
- str1.count()
- str1.replace(old, new)
- str1.split(" "), transfer to list
- "".join(lst1), transfer to string


```python
# %s.format() f-String
var1 = 3
var2 = 3.1415926
print("the number is %s" % var1)
print("the number is %s" % var2)
print('----------------')
print("the number is %d" % var2)
print("the number is %f" % var2)
print("the number is %.2f" % var2)
print('----------------')
print("the number is {:.2f}".format(var2))

print('----------------')
print(f"the number is {var2}")
print(f"the number is {var2*2}")
```

    the number is 3
    the number is 3.1415926
    ----------------
    the number is 3
    the number is 3.141593
    the number is 3.14
    ----------------
    the number is 3.14
    ----------------
    the number is 3.1415926
    the number is 6.2831852

