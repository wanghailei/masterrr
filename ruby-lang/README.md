# Ruby lang

This philosophy is often summarized as: "Ruby is designed to make programmers happy."

Human-Centric Design: Matz designed Ruby with an emphasis on the needs of humans rather than computers, which makes it intuitive and easy to read. It emphasises natural language elements, significant whitespace, and common idioms, so Ruby code often reads like English sentences.

Flexible: Ruby is designed to be flexible to allow programmers to have multiple ways to do the same thing. This gives you the freedom to write code that best suits your thinking process.

Consistent: In Ruby, everything is an object, and all of those objects have methods. This consistent, object-oriented approach makes Ruby code easy to understand and predict. Even basic data types like integers are objects with methods.

Metaprogramming: Ruby has robust metaprogramming capabilities. This means you can write code that generates other code, making Ruby very powerful and flexible.

Blocks, Procs, and Lambdas: Ruby features first-class support for "blocks" of code and makes it easy to pass these blocks around your program. This feature is heavily used in Ruby for handling everything from basic iteration to customising how complex objects behave.



***

### Concepts

object 形體

class 形組

type 形式

attribute 形態

method 形變

OO 以「形體」為主導的模式。

### Metaphors

符號「`.`」其實相當於英文裡的「'」或者中文裡的「的」。

一個 Function 就像一台小機器，被調用（call）時，就會進行「來料加工」，然後根據「指定規格」（-> type）返回（return）一個結果。

那麼，我想，一個 Struct 或一個 Class 就像一個個的工廠🏭。

Variable 或 Constant 就是些容器/載具，而且可能是透明材質的，用來裝東西（value）。

let 類型的容器，是放進去就再也更改不了的，叫做「非換裝容器」；而 var 類型的容器，是放進去的東西以後還可以換裝別的，叫做「可換裝容器」。

每一種容器，只能裝一種固定「型態」的東西，例如長的、寬的、球的、扁的、水的、氣的等等。

被大括號 `{}` 包起來的叫做 code block「碼塊」，裡面是實際上會執行的內容。

***



\# <mark style="background-color:orange;">A block is simply a chunk of code, and it may have arguments.</mark>

\# Here's a simple block that gets run with the \`times\` method:

5.times do |i|

puts "We are at number #{i}!"

end

\
This will output:\
We are at number 0!

We are at number 1!

We are at number 2!

We are at number 3!

We are at number 4!

WHL: 5 is an integer and an object. How can that be? With a language background of Java or Rust, it's hard to understand.

ChatGPT: Yes, the idea that everything is an object in Ruby, including primitives like integers or booleans, can be a little challenging to understand if you're coming from a language like Java or Rust where primitives are not objects.

In languages like Java or Rust, primitives such as integers or booleans are not objects, they're basic data types with a fixed size in memory and a specific set of operations that can be performed on them. They don't have methods or properties like objects do.

Ruby, however, takes a different approach. In Ruby, everything is an object. This includes integers, strings, arrays, and even classes and modules themselves. Each of these objects is an instance of a class, which means it has a set of methods it can call and it can have instance variables to hold state.

For example, an integer in Ruby is an instance of the Integer class, which means it has methods that can be called on it, like even? to check if the number is even, or times to repeat an action a certain number of times.

Here's how you can use these methods on an integer in Ruby:

ruby

Copy code

\# Here's an integer:

i = 5

\# Because \`i\` is an object, we can call methods on it:

puts i.even? # Prints 'false'

puts i.next # Prints '6'

\# We can even use a method like \`times\` to do something repeatedly:

i.times do |n|

puts "This is repetition number #{n}."

end

In this way, Ruby simplifies its model of the world by treating everything as an object, each with its own set of behaviours and data. This allows for a consistent way of interacting with all elements in the language and makes the language more flexible and expressive.

### Number

In Ruby, numbers are objects.

Keep in mind that most of the arithmetic operators you see in Ruby are methods. They don’t look that way because of the operator-like syntactic sugar that Ruby gives them.

If you define, say, a method called + in a class of your own, you can use the operator’s syntactic sugar.\
And if you see arithmetic operators behaving weirdly, it may be that someone has redefined their underlying methods.



***

**Encapsulation** describes the fact that an object contains both its own data and the methods required to manipulate that data.

**Polymorphism** describes the ability to have different classes containing methods with the same name. The same “message” (such as talk) can be sent to different objects (such as cats and dogs), and each different object responds differently to the same message with its own special method (here the talk method).&#x20;

