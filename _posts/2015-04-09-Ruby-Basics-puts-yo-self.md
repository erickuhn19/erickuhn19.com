---
layout: post
title: Ruby Basics puts yo self
category: blog
date: '2015-04-09'
---
As soon as you start to learn the Ruby programming language you hear about this “puts” thing. Puts right away is used and is pretty cool. When you want to “put” something to the screen, you runs puts.

`ruby puts “Eric knows Ruby!” puts “Hello World”`

Well “puts” is a method if you were wondering. Now that might not make a whole lot of sense since you probably learned that all methods are called on objects. Something like:

`ruby name = “eric” name.upcase` My method upcase was called on the object of name. So puts is a method but where is its object?

Intro to self.

Anytime there isn't an object referenced on the left hand side, Ruby references a variable called self. Self will always reference the current object. Self is a global object and its value is main. If you run:

`ruby self.class`

You get Object. We found out object! Makes sense now?

Wrap up: “puts” is a method, its called on a object and is stored in self. All methods are called on objects even if you don't see it.
