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


## python的真和假
要注意的是，python中的负数也是True,解释器认为的是假的元素有如下这些：0，None，False，以及空数据类型比如空列表，空字典等。

## python中的高级函数
map，filter，reduce等，举个例子：
map(lambda x: 2*x,[1,2,3,4,5]) ,返回的是[2,4,6,8,10].


##sort 和sorted
sort是list的一种方法，就地对列表进行排序，而sorted是所有可迭代对象的方法，原来对象不变，开辟新内存进行排序。而sort和sorted底层全部是归并排序，是稳定的排序。


##GIL
Cpython解释器中有一个叫GIL的东西，确保每一个进程中同一时刻内只有一个线程拥有解释器，因此python并没有具备真正意义上的多线程。
ref https://www.cnblogs.com/SuKiWX/p/8804974.html
