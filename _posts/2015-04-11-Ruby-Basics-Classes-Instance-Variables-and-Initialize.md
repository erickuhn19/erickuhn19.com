---
layout: post
title: Ruby Basics Classes, Instance Variables and Initialize
category: blog
date: '2015-04-11'
---
I want to quickly touch on 3 concepts that are super important to the Ruby language. Having an understanding how Classes, Instance Variables and the Initialize method work together will be beneficial in mastering the Ruby programming language.

To give some context of these three concepts lets define one additional term. A Local Variable is only accessible within the method it’s declared in. Meaning we can not call a local variable outside of the method it was created in. Lets look at an example:

`ruby def local_variable x = 19 puts x end`

In this case x is our local variable and can not be called outside of the local_variable method. To use x we would need to call local_variable.

`ruby def to_s “My Local Variable is #{local_variable}” end`

Ok, now we have established what a local variable is lets see what these other concepts are.

### Classes:

The Class in Ruby is like a production line that creates objects that have a unique state and a group of methods to call on those objects. The naming convention for classes always start with an uppercase method or known as CamelCase.

### Initialize Method:

The Initialize Method is part of the Ruby magic. You don't actually call this method on an object, but Ruby calls it for you every time you use the New method for your class to create a new object. An example is coming.

### Instance Variable:

This is why we defined what a Local Variable was earlier. An Instance Variable is how we store an object’s state in a Class. These variables can be used throughout the life of your object, but you need to call them differently. These variables start with the @ symbol. You also define your Instance Variables in the Initialize Method.

`ruby class Dog def initialize(name, energy=100) @name = name @energy = energy end`

`ruby def to_s “My dogs name is #{@name} and he has #{@energy} % energy! This dog loves to play!” end`

So I just created an example class of Dog. When I want to create a new Dog, I would use the new method for the Dog class which will create a state in my instance variables which I defined in the initialize method.

`ruby Dexter = Dog.new(“Dexter”, 110) puts Dexter`

So using that one line of code I created a class object of Dexter who has two instance variables of @name and @health. When I call “puts Dexter”, the output will be “My dogs name is Dexter and he has 110% energy! This dog loves to play!”

Take this example and try it for yourself in your text editor! **Or go play with a dog that has lots of energy!**
