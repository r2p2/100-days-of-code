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
