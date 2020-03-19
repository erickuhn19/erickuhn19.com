---
layout: post
title: Scaffold and Devise - The Hard Way
category: blog
date: '2015-03-04'
---
I recently read this article called [Rails Scaffold’s Dangerous Defaults](http://rubyjunky.com/rails-scaffold-dangerous-defaults.html?utm_medium=email&utm_source=rubyweekly).

As a new Rails programmer I really like generating scaffolds because its so robust in nature. It creates views, controller, applies resources to the routes, stylesheets, JSON Api and even writes some basic tests! I found out pretty quickly that I don't actually use all the functionality the scaffold gives me, but at the time I wasn't worried about it.

After reading this article I have some really great insight I look forward to implementing in my next project. Instead of relying on a scaffold, even if I believe I will use most if not all of it, is to create a secondary app while in development of my main app. Run a scaffold on the secondary app and pick and choose what pieces I want to implement for my main app. This gives me the ability to analyze what the scaffold is doing and decide what pieces are essential to what I’ trying to do.

The author ends the article with these words:

> In the end, you shouldn’t put too much trust in code you haven’t written yourself. Many bugs and security holes occur in the areas of our applications that we understand the least.

This reminds me of my recent revelation with using Devise for authentication. In the early stages of learning to program, you need to do things the hard way to really understand them. Devise brings a ton of functionality but you might not need all of it. Trying to go under the hood and customize things gets tricky if you really don't understand how it works.

I’m going to focus on doing things the hard way.
