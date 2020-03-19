---
layout: post
title: My First Open Source Project rails blogger engine
category: blog
date: '2015-04-04'
---
In the final weeks of Codecademy Labs we had to break off into teams, and choose a final project that will be presented on the last day. My mind instantly raced about what project I would choose. We only had two weeks to complete the project and this is a part time course. Did I want to build one of my pet projects I’ve been planning? Not really, I didn't want to rush one of those. Maybe I could just think of some small idea and hack it together with a team in two weeks, only to never use it again. That didn't sound like a good idea either. Then I thought it would be really cool to start some open source project and then be able to continue working on it after the class ended. Create something that not only would be an interesting final project but something real people could use. And maybe other people in the class would eventually contribute to it.

So me and my teammate, [Meg](https://github.com/meghart), started working on the idea. At first, we wanted to build a super simple authentication gem that could be used instead of Devise for personal blogs created in Rails (like this site). We started going through the tedious trial and error process to build a gem. Can I be honest here? I think gem building is probably the weakest area of documentation. OK, I just had to say it. Anyway, so there is multiple ways to build a gem. You can use bundler, you can create a plugin or you can make a mountable engine.

After we had a good sense on how the different types of gems were made, we began asking ourselves what we were trying to accomplish? A simple authentication gem for a rails blog! Does that mean the only thing the rails app has is a blog or is this just a piece of a bigger rails app? We wanted this gem to have a future and a future where I would want to use this in future applications. We needed to think bigger.

We ultimately decided to build a blogging gem for Rails that encompasses all of the pieces needed to just bolt on a blog to your rails app. Its called [Rails_Blogger_Engine](https://rubygems.org/gems/rails_blogger_engine/). That eventually includes our original idea of simple authentication. We didn't get there in the gem’s 1.0 release for the project, but its definitely included in the projects roadmap.

If you’re reading this and want to contribute to an open source project. Check out the features we think would be cool to add to this project. If you have your own ideas then just [submit a pull request](https://github.com/erickuhn19/rails_blogger_engine) and we’ll see if it works.

### Feature List

*   Initializers to push views & controllers to app
*   Bootstrap template
*   Markdown with syntax highlighting
*   Simple authentication (Create admins on the rails console, no views for creating users)
*   Google ReCaptcha for comment spam
*   Comment form by clicking button through jQuery
*   URL’s created through title of post
*   SEO
*   Pagination
*   Tests!

Anything else that you can think of!
