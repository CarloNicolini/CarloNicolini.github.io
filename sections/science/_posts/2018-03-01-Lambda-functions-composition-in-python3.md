---
layout: post
title: Lambda functions composition in Python 3
categories: science
published: true
date: 2018-03-01
---

Introduction
==============

I'm facing a problem with automatic generation of network connectivity model that requires me to manually generate a number of them, written as combinations of various operations.
To make this example concrete, suppose you have a number of functions in Python3 of the kind:

{% highlight python %}
def fun1(a,b):
    return a+b

def fun2(c,d,e):
    return c*d+e

def fun3(x):
    return x*x
{% endhighlight %}


and you want to automatically generate all the combinations of these functions with two arithmetical operators, let's say the multiplication `operator.mul` and the addition `operator.add`.

### First attempt using functions

A first attempt is to manually define a number of composed functions with one single argument in form of a list `x`:

{% highlight python %}
C1 = lambda x : fun1(x[0],x[1])*fun2(x[2],x[3],x[4])+fun3(x[5])
{% endhighlight %}

and then call this anonymous function in your code with a 5 elements list of numbers:

{% highlight python %}
C1([1,2,3,4,5])
{% endhighlight %}

to get the output you want. However this approach requires you to manually generate a number of combinations which may be very time-consuming and error-prone.
Especially if you have 10 different functions to combine with multiplication and addition, this task gets almost impossible to do manually.

Python3 allows you to get the argument names of a function, as it is treated as a normal variable, and you can access its code.
The field `fun1.__code__.co_varnames` will returns you the list of arguments of `fun1`.

With this in mind you can define an additional lambda function `multiplyf1f2` by exploiting list comprehension and unpacking with the help operator `*` in front of a list:

{% highlight python %}
multiplyf1f2 = lambda x : fun1(*[x[i] for i in range(0,len(fun1.__code__.co_varnames)]) * fun2(*[x[i] for i in range(len(fun1.__code__.co_varnames),len(fun1.__code__.co_varnames)+len(fun2.__code__.co_varnames)])
{% endhighlight %}

This is a first solution, already a bit more general solution than before.

However you can get even more general thanks to the `operator` module. Suppose you want to create the combinations of length 3 of sum and addition of the three functions `fun1`,`fun2`,`fun3`.

### A more powerful approach using functors

This is the approach that I finally applied. All the models I want to implement are subclasses of the `Model` class, that entails the `__call__` implementation required to pass to `scipy.minimize`. Thanks to inheritance of `Model` to some specifically defined `Operator` helper classes such as `Add` or `Mul`, I have been able not only to call these objects but also to let them carry their own parameters around. Very useful when desigining an optimization library.

More info to come with my `networkqit` freshly designed Python3 library.