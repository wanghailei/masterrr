# Class

### Class

Classes are, at heart, a way to organise objects and methods.\
<mark style="background-color:red;">% 與其說 organise，毋寧說 define 或 design，可以說是「藍圖」。 20231117%</mark>

Defining a class lets you group behaviours (methods) into convenient bundles, so that you can quickly create many objects that behave essentially the same way.

Everything you handle in Ruby is either an object or a construct that evaluates to an object, and every object is an instance of some class.

When you use the dot notation on a class, you send a message to the class. Classes can respond to messages.



Ruby is about objects, and objects are instances of classes.

Classes are objects.

_Object_ is a built-in Ruby class.

Classes are named with constants.

% 定義一個 Class，就像「開模」來製造一個銅盤一樣。20230624 %





***

Learned from Xavier Noria&#x20;

<mark style="background-color:orange;">The</mark> <mark style="background-color:orange;"></mark><mark style="background-color:orange;">`class`</mark> <mark style="background-color:orange;"></mark><mark style="background-color:orange;">and</mark> <mark style="background-color:orange;"></mark><mark style="background-color:orange;">`module`</mark> <mark style="background-color:orange;"></mark><mark style="background-color:orange;">keywords store classes and modules in constants.</mark> &#x20;

In Ruby, when you define a class or a module using the `class` or `module` keywords, they are indeed stored as constants. This is a unique aspect of Ruby's object model. For example, when you define `class MyClass; end`, `MyClass` is a constant that references the class object.

<mark style="background-color:orange;">Constants belong to classes and modules.</mark>

Constants in Ruby are scoped within classes and modules. They are not global in the same sense as in some other languages. This means you can have different constants with the same name in different scopes without conflict. For instance, you could have `class A; MY_CONST = 1; end` and `class B; MY_CONST = 2; end` without any conflict between `A::MY_CONST` and `B::MY_CONST`.

<mark style="background-color:orange;">Top-level constants belong to</mark> <mark style="background-color:orange;"></mark><mark style="background-color:orange;">`Object`</mark><mark style="background-color:orange;">.</mark>

In Ruby, top-level constants (those defined outside of any class or module) are treated as if they belong to the `Object` class. This is because `Object` is the default object context of Ruby at the top level. This means that any constant defined at the top-level is accessible from anywhere in the program, as all classes in Ruby are descendants of `Object`.

`Module#autoload` allows you to load constants on demand.







***

### Methods

Methods defined inside a class and intended for use by all instances of the class, are called instance methods.

Methods that you define for one particular object are called singleton methods.
