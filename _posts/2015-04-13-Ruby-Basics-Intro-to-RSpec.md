---
layout: post
title: Ruby Basics Intro to RSpec
category: blog
date: '2015-04-13'
---
The last post I touched on classes and in this tutorial we are going to test that class using RSpec. RSpec is described on its [website](http://rspec.info) as a behavior driven development for ruby. I think thats a pretty accurate description but to break it down even further, RSpec is a framework to test your code. It was built as a domain specific language, which means it’s built in Ruby with its own syntax but its still just Ruby code.

Now the more you learn about Ruby and the Rails framework, you will see the debate in the community about which testing framework is better, RSpec or MiniTest. The best advice I’ve heard on this issue is as long as your testing, then your going in the right direction. I’ve chosen RSpec, but that doesn't mean you have to.

Ok, so I’ve expanded the the class of Dog a bit by adding a few methods for playing and resting. To test out my code and practice on your own, create a new file called dog.rb. Tip, you can create a file in your command line like this.

`ruby touch dog.rb sublime dog.rb`

If your using Sublime thats a shortcut you can set up to have the file automatically open up. Going through the Finder directory is no fun. I used this [walk through](http://olivierlacan.com/posts/launch-sublime-text-3-from-the-command-line/) to set it up.

Write out this code into your dog.rb file. You can copy and paste it but writing out each line is recommended to understand whats going on.

```ruby class Dog attr_reader :energy, :name def initialize(name, energy=100) @name = name.capitalize @energy = energy end

def to_s "My dogs name is #{@name} and he has #{@energy} % energy! This dog loves to play!" end

def play @energy -= 20 puts "#{@name} just ran around the yard! That dog is so fast!" end

def rest @energy += 25 puts "#{@name} just took a nap. Dogs love to sleep." end end

if **FILE** == $0 dog = Dog.new("Dexter", 110) puts dog puts dog.energy puts dog.play puts dog.rest end ```

Now we want to test this class using RSpec. As of this writing RSpec version is at 3.2\. Start in your command line and run:

`ruby gem install rspec` To use RSpec create a new file named dog_spec.rb in the same folder you created dog.rb. The spec portion of the name is what RSpec looks for to run your tests. If you’ve forgotten how to create a file from the command line:

`ruby touch dog_spec.rb sublime dog_spec.rb`

Now we have our class created and we have a blank file to put our tests in, lets get to it. I’m going to give all the code at once, but its extremely helpful to go line by line adding the code into the file so you know what it does.

```ruby require_relative 'dog'

describe Dog do before do @initial_energy = 100 @dog = Dog.new("dexter", @initial_energy) end

it "has a capitalized name" do expect(@dog.name).to eq("Dexter") end

it "has an initial energy set" do expect(@dog.energy).to eq(100) end

it "has a string returned for the object" do expect(@dog.to_s).to eq("My dogs name is Dexter and he has 100 % energy! This dog loves to play!") end

it "reduces energy by 20 when a dog plays" do @dog.play expect(@dog.energy).to eq(@initial_energy - 20) end

it "increases energy by 25 when a dog rests" do @dog.rest expect(@dog.energy).to eq(@initial_energy +25) end

context "create a dog with default energy" do before do @dog = Dog.new("dexter") end

<div class="highlight">

    it "has a default energy of 100" do
      expect(@dog.energy).to eq(100)
    end   end end ```

</div>

The first thing this RSpec file needs to do is require the file we are testing, the dog.rb file. Then on line 3 we start using the basic structure of the testing framework which is supposed to express concepts like a conversation. I translate this first line into “Please describe the Class of Dog doing these things”.

The block of code that starts on line 4 runs before each testing scenario that starts with “it”. This “before do” basically creates the environment for us to test a specific use case. Instead of typing out this each time we run a scenario it can automatically run for each test case. This conforms to the DRY principle in programming, or Don’t Repeat Yourself.

Ok, so test scenario 1 is saying a statement of “it has a capitalized name”. One thing I need to say here, please don't ever call a dog an “it”, that would not be cool! It is referring to the object we are testing and this is the only time where this would be ok. Anyway, keeping the literal translation going I would translate the next line to say “it (the dog) has a capitalized name, do this test, we expect when you call the dog’s name, it will show up as ‘Dexter’ ”. Thats a pretty simple formula to follow, right? The line for “it” states the statement we are trying to test, “expect” is giving the exact parameter we want to see, “.to” wants to see a true value and “eq” is saying the output should equal “Dexter”.

To actually see this test file run, go back to your command line and you can run any one of the following three commands. Try each one out to see which format you like the best.

`ruby rspec dog_spec.rb rspec dog_spec.rb —color rspec dog_spec.rb —color —format doc`

Thanks for following along to my simple introduction to RSpec!
