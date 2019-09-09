# python notes



## 对象

在python中一切都是对象，每个对象有标识（ID）、类型（type）和值（value）组成。

而变量都是对象的引用，由于对象自带type，因此变量在赋值的时候不需要显式地生命类型，由对象的类型带出，也可以认为变量没有类型。

变量都在栈中，存的是对象的地址，对象都在堆里。

对象被删除之后，栈中没有该变量。如果对象没有变量引用，那么对象就会被回收。

### 可变对象和不可变对象：

数字、字符串、元组均是不可变对象，列表和词典是可变对象。



### python函数的参数传递

不可变类型：值传递，如整数、字符串和元组。fun(a:int),传递的是a的值，并没有影响本a对象本身。在fun(a)内部修改a的值，修改的只是复制过去的一个对象，a本身不变。

可变类型：引用传递，fun(a:list),传递的是a本身，在fun内部修改a的值，对象也会改变。



## 异常

> try:
>
> ​	copyFile("a.txt","b.txt")
>
> except Exception as e:
>
> ​	print(e)

常见的异常基本都是Exception的子类。

## 列表和生成器推导

a = [i*i for i in range(5)]  

 type(a)  # list

b = (i*i for i in range(5))

type(b)  # generator





## zip()并行迭代

zip()函数使用若干个可迭代对象作为参数，将对象中对应的元素打包为一个个元组，然后返回这些元组组成的对象





## nonlocal 和global

两者作用类似，nonlocal修改的是外层函数的值，global关键字生命全局变量。

在嵌套函数中，内层函数可以调用外层函数的变量，但是无法进行修改，进行nonlocal声明之后才能进行赋值。类似的是global引用声明。





## LEGB规则

python寻找变量的路径：local 、enclosed、global、buildin，依次是局部、闭包（嵌套）、全局、内置函数。