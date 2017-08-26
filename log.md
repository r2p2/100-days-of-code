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
