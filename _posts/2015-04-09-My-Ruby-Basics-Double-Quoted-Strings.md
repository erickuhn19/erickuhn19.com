---
layout: post
title: Ruby Basics Double Quoted Strings
category: blog
date: '2015-04-09'
---
For all intensive purposes I only use double quoted strings. I highly recommend taking a look at [ThoughtBot’s Ruby Style Guide](https://github.com/thoughtbot/guides/tree/master/style/ruby) which I am echoing here, but lets take a quick at look why we should use double quoted strings.

Lets say I have two variables:

`ruby name = “Eric” bitcoin = 100` If I have single quoted strings and I want to use both variables I have to use concatenation. Which means using the “+” symbol to add two strings together. Well I can quickly run into errors if I’m not careful.

`ruby puts ‘My name is ‘ + name + ‘and I have ‘ + bitcoin ‘bitcoins.’`

We will get an error message if we run this code. Specifically a TypeError of 'no implicit conversion of Fixnum into String'. The reason we get this error is the variable, bitcoin = 100, is a fixnum, which is just an integer, and this can't be called without using the string version. So lets see how this is done correctly.

`ruby puts ‘My name is ‘ + name + ‘and I have ‘ + bitcoin.to_s ‘bitcoins.’`

Not a huge difference but something you have to remember and its more typing. Now lets see this refactored using double quotes. What does refactoring mean? Its the process of altering existing code internally to make it better without altering what that code does external. We will change the code but it will still have the same result.

`ruby puts “My name is #{name} and I have #{bitcoin} bitcoins.”` Using the double quoted strings and using a technique called interpolation, it automatically converts the variable into a string so we can run it without errors. Interpolation just allows Ruby code to appear evaluated within the string.

If we wanted to say I had double the bitcoins then the hardcoded variable, we could just do:

`ruby puts “My name is #{name} and I have #{bitcoin * 2} bitcoins.”`

Another quick tip if you are writing this code out in your Sublime Text editor (on a Mac) and you want to see if the code will run, just hit command + B. This will run the code right in the text editor without jumping to the command line. You can also test this out in IRB as well. To get to IRB, just hit IRB in the command line and typing out (exit) will get you out.
