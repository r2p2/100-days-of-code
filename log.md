# 100 Days Of Code - Log

<!--

### Day 0: February 30, 2016 (Example 1)
##### (delete me or comment me out)

**Today's Progress**: Fixed CSS, worked on canvas functionality for the app.

**Thoughts:** I really struggled with CSS, but, overall, I feel like I am slowly getting better at it. Canvas is still new for me, but I managed to figure out some basic functionality.

**Link to work:** [Calculator App](http://www.example.com)

### Day 0: February 30, 2016 (Example 2)
##### (delete me or comment me out)

**Today's Progress**: Fixed CSS, worked on canvas functionality for the app.

**Thoughts**: I really struggled with CSS, but, overall, I feel like I am slowly getting better at it. Canvas is still new for me, but I managed to figure out some basic functionality.

**Link(s) to work**: [Calculator App](http://www.example.com)
-->

### Day 1: 2017-08-26, Saturday

**Today's Progress**: Added some test cases for my go raft implementation to cover a successfull election phase.

**Thoughts**: I am having a hard time wrapping my head around go's interface concept. I thought it would work like some kind of duck typing but constructor methods need to return the interface type instead of the actual one.

**Best Compiler Error**:
```
MockRemoteNode does not implement r2aft.RNode (AppendEntries method has pointer receiver)
```

Which, for whatever reason, means that there is an asterisk missing. Bad: `remoteNode1.(MockRemoteNode).term != 1` Good: `remoteNode1.(*MockRemoteNode).term != 1`

**Link(s) to work**
1. [Go Raft Implementation](https://github.com/r2p2/r2aft)

### Day 2: 2017-08-27, Sunday

**Today's Progress**:
1. Continued the go raft implementation by adding a tcp layer enabling it to communicate with other nodes. (not pushed yet)
2. I've also created a new project which already contains a readme to outline its purpose and some dummy source files that it won't look so empty.

**Thoughts**:
1. Adding the tcp layer seems to increase the complexity of my go code more than it should. It seems to be *best practice* to handle every connection synchronously in their own go routine. That adds management complexity for each go routine and a buch of channels for communication between them. Each routine has to handle timeouts, received and sent messages and the event that the application or node is closed. Don't know how I should achieve that.

    I might switch to a message bus approach where the whole application just reads and write to one connection. The dispatching should become much easier.

2. While bicron is a stupid name, I like the project idea. After the c++ implementation is complete, I've plans to port it to go and rust.

**Link(s) to work**
1. [Go Raft Implementation](https://github.com/r2p2/r2aft)
2. [Bicron](https://github.com/r2p2/bicron)

### Day 3: 2017-08-28, Monday

**Today's Progress**: All my energy went into improving the TimePoint class within the bicron project to handle missing date/time data.

**Thoughts**: I find it funny how I went from various class designs (mostly relying on inheritance) to hold my date and time units. Still ended up with a template version. We'll see how long the naive valid checks hold up.

**Link(s) to work** [Bicron](https://github.com/r2p2/bicron)


### Day 4: 2017-08-29, Tuesday

**Today's Progress**: Not much today. Implemented the matcher function to check if a rule matches a given time point.

**Thoughts**: Go home earlier.

**Link(s) to work**: [Bicron](https://github.com/r2p2/bicron)


### Day 5: 2017-08-30, Wednesday

**Today's Progress**: Implemented the method which runs all rules against a given time point.

**Thoughts**: My tests are failing and I don't know why yet.

**Link(s) to work**: [Bicron](https://github.com/r2p2/bicron)

### Day 6: 2017-08-31, Thursday

**Today's Progress**: Fixed the issue when matching rules against time points.

**Thoughts**: I think I'll get it done this weekend.

**Link(s) to work**: [Bicron](https://github.com/r2p2/bicron)

### Day 7: 2017-09-01, Friday

**Today's Progress**: Moved all the bicron classes into their own namespaces so that they can be used as library more easily. I've also started with the integration of a json library. But thats not ready yet.

**Thoughts**: It is harder to keep this file up to date than to write code for one hour.

**Link(s) to work**: [Bicron](https://github.com/r2p2/bicron)

### Day 8: 2017-09-02, Saturday

**Today's Progress**: Bicron got its main function and is executable now. It reads a json configuration passed as argument and prints the current state based on configured rules and the local time.

Also started working on a mandelbrot generator in rust.

**Thoughts**: My third attempt of learning rust started today. I seem to be unable to read the docs properly or it is rely just too hard to store an ImageBuffer from the image crate without writing 100 chars of template foo.

**Link(s) to work**: [Bicron](https://github.com/r2p2/bicron)

### Day 9: 2017-09-03, Sunday

**Today's Progress**: Mostly learning rust today.

**Thoughts**: After so many yeas of development experience it seems that I expect to master every new language or library within a day or two. Truth is that rushing through the easy parts straight to high level libraries makes it just harder to stay motivated when learning. I should calm down and take babysteps again. Rust ist f* hard. 

**Link(s) to work**:
1. [Collection of problems I encounter with Rust](https://github.com/r2p2/whats-hard-about-rust)
2. [Mandelbrot generator written in Rust](https://github.com/r2p2/rust-mandelbrot)

### Day 10: 2017-09-04, Monday

**Today's Progress**: Played around with adding a trait to separate the Mandelbrot implementation from the image crate to be more portable but this current implementation does not support the multithreading feature.

**Thoughts**: On the one hand, other languages seem to make it easier to add concurrency later. But rust makes it harder to add multithreading when the interfaces weren't designed with that intention from the start. At least, that is my impression. Sure it makes it more secure, when you cannot just hack somethin into existing code.

**Link(s) to work**: [Mandelbrot generator written in Rust](https://github.com/r2p2/rust-mandelbrot)

### Day 11: 2017-09-05, Tuesday

**Today's Progress**: Implementing a elementary cellular automaton using rust piston as ui. Nothing productive, just testing.

**Thoughts**: You still do the heavy stuff. Stop it already!!!

### Day 12: 2017-09-06, Wednesday

**Today's Progress**: Improved performance with the ECA and started to introduce configurable cell sizes. Still not public yet.

**Thoughts**: It starts to make fun fiddeling around with rust. Found it impressive than accessing by index operator is slower than iterating. But I did not check if there was a difference between debug and release...

### Day 13: 2017-09-07, Thursday

**Today's Progress**: Tried to fix the flickering bug. Not successful.

**Thoughts**: Too many other things in my mind.

### Day 14: 2017-09-08, Friday

**Today's Progress**: Fixed the flicker issue and renamed the project appropriately.

**Thoughts**: Everything makes much more sense now but implementing own iterators and enumerators is still way to heavy. 

**Link(s) to work**: [Rust ECA](https://github.com/r2p2/rusty-eca)

### Day 15: 2017-09-09, Saturday

**Today's Progress**: Extracted the cellular automata part into its own module.

**Thoughts**: Learned that modules normally reside in only one file. That raises the question if namespaces from C++ can be compaired with modules. Borrowchecker is still a bitch. 

**Link(s) to work**: [Rust ECA](https://github.com/r2p2/rusty-eca)

### Day 16: 2017-09-10, Sunday

**Today's Progress**: Thought it would be faster to render into an image and draw the image as a whole via opengl onto the screen instead of calling the rectangle method over and over. Turns out that it runs 500 times slower now.

**Thoughts**: Sometimes you just have to throw away your work.

**Link(s) to work**: [Rust ECA](https://github.com/r2p2/rusty-eca)

### Day 17: 2017-09-11, Monday

**Today's Progress**: Managed to get keyboard events to change the CA rule at runtime.

**Thoughts**: 404 Motivation not found

**Link(s) to work**: [Rust ECA](https://github.com/r2p2/rusty-eca)
