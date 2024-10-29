Lectures 14-24. There is no lecture 15 (exam)
# Important vocab / concepts
### Formula for summing $n$ increasing integers
$$
\sum\limits_{i = 1}^{n} n = \frac{n(n+1)}{2}
$$
- $i=1$ mf
- $1 + 2 +  3 + 4 + 5 + \dots + n$ 
## Case analysis
- Best case
- Worst case
- Average case
## Errors and exceptions
### Line coverage
The percentage of lines executed
### Branch coverage
The percentage of control points executed by code
### Path coverage
The percentage of possible execution sequences run
### Java exceptions
Java exceptions refer to objects which inherit from the `Throwable` class, these are some of this class's methods
```java
public class Throwable extends Object {
	Throwable();               // no error mssg constructor
	Throwable(String message); // constructor w/ error mssg
	String getMessage();       // return error message of string
	void printStackTrace;      // record methods called - exception occur.
}
```
### Checked and unchecked 
Checked
- The compiler will force you to put these in try blocks
Unchecked
- Compiler does not care
- Usually common exceptions or ones that are fatal and you can't possibly handle them

![[Pasted image 20241022220227.png]]
## Analyzing algorithms
Benchmarking
- Running real world tests
Asymptotic analysis
- Math nerd shit
- $\mathcal{O}$
### Big $\mathcal{O}$ rankings
![[Pasted image 20241022223503.png]]
### Critical section of an algorithm
The part the runs the most times
## Recursion
![[Pasted image 20241023232842.png]]
## Tail and head recursion
tail
- When the recursive call is the last thing performed
- Queue-like
	- Like, the methods will perform operations as they are called
head
- When the recursive step is executed first
- Stack-like
	- Like, the last methods in the stack call will be the first ones to actually perform operations
## Polymorphic lists
Lists that utilize different types of classes as their 'nodes'
***
# Handouts 
# Case analysis
### Best case measure
Best case scenarios for algorithms
- Many have $\mathcal{O}(1)$ (like insertion) but some don't. Take linear array search for example, it will always be $\mathcal{O}(n)$
### Worst case
Worst case scenario, duh
### Average case
The 'average case' for an algorithm. Think expected value, amortized cost, etc.
# Errors + exceptions
### Error
The underlying cause of a problem
### Fault / defect
The issue which occurred, indicative of an error
### Syntax errors
Errors that prevent code from compiling, caught by the compiler
- Semicolon
- Invalid declaration
- Unclosed block
- etc
### Runtime errors
Errors which occur at runtime. Compiler can't catch these
- Array out of bounds
- Null references
- Division by zero
- etc
### Logic errors
When your program does not behave in an intended manner
- 2 + 2 = 5 type shit
## Code coverage
% of your code that is run by your tests
### Line/statement coverage
Measures what % of the lines/statement of some code was executed by a set of tests
### Branch coverage
Measures that percentage of control points (conditionals) in some code that were executed in all possible ways
``` java
if (condition)
```
- This has two possible ways of execution; either true or false
![[Pasted image 20241022212451.png]]
This has more 
### Path coverage
Measures the percentage execution sequences that were run by a set of test
## Error handling
Error handling refers to the actions a program may perform when faced with an error. these include
- Quitting the program
- Printing an error message
- Requesting new input data
- Retry of operation
- Ignore
- Inform some calling method
	- Via returning an error code
	- Throwing an exception (not all languages)
dawg
## Java exceptions
Java exceptions refer to objects which inherit from the `Throwable` class, these are some of this class's methods
```java
public class Throwable extends Object {
	Throwable();               // no error mssg constructor
	Throwable(String message); // constructor w/ error mssg
	String getMessage();       // return error message of string
	void printStackTrace;      // record methods called - exception occur.
}
```
### Keywords relating to exception handling
```java
- try 
- throw
- catch
- finally
```
#### try
run code in this block and watch for errors
#### throw
throw error, for whatever reason, sending execution to the catch block. execution at a `try` block halts the moment an error is throw, so in the following code inside a `try` block
``` java
print("hello");
throw new Exception();
print("code won't ever make it here");
```
the second `print` is never executed
#### catch
follows a try block, catches a specified error from the try block. can catch any error if declared as
```java
} catch (Exception e) {
	// do thing
}
```
Since all exception inherit from ```Exception```

there can be multiple `catch` blocks after a try block. error will be checked against each one sequentially until a suitable one is found. even if an error could qualify to be run by two different catch blocks, the first one in line will be the one to catch the error
#### finally
execute after `try` and `catch`, regardless of what happened

https://stackoverflow.com/questions/6703085/is-it-necessary-to-put-catch-statements-after-a-try-block
### Error flow
Once an error is thrown, it will look for a suitable catch. if this error occurred within a `try` block, then it will check against that block's `catch` blocks. if no suitable catch is found, the the error will check for `catch` blocks in the method that just called this method that generated to error. this will go on until either a `catch` is found or the error propagates to the main method, at which point the JVM will kill the program
## Types of Java exceptions
https://www.geeksforgeeks.org/checked-vs-unchecked-exceptions-in-java/

![[Pasted image 20241022215519.png]]
### Checked
- Occur during compile time
- Compiler mandates these to be checked i.e. put things that can throw them within `try` `catch` blocks
- Generally done with operations prone to errors
### Unchecked
- Occur during runtime
- Optional handling
	- If left to be handled by JVM, program is killed'
- Either errors that are too grave to handle or those that often occur
### Errors (bottom branch)

![[Pasted image 20241022220227.png]]

Not much you can do if these happen
***
# Lecture 14
- Test coverage
	- See that section above
- Error handling
	- See that section above
# Lecture 16
## Analyzing the efficiency of algorithms
### Benchmarking
- Actually running the algorithm and checking cases
Pros
- Science
- 'Real world' data
Drawbacks
- Hardware dependent
- Biased tests
- Not indicative of efficiency
### Asymptotic complexity (big $\mathcal{O}$)

![[Pasted image 20241022222953.png]]

Mathematical analysis of algorithm
Pros
- Intrinsic efficiency
- Irrelevant to language, compiler, hardware, etc
## Formal definition of big $\mathcal{O}$
A function $T(n)$ is $\mathcal{O}(f(n))$ if, for some integer constants $c>0$ and $n_0 \geq 1$, $T(n) \leq c \times f(n)$ for every $n \geq n_0$ 

https://en.wikipedia.org/wiki/Big_O_notation
some wack ass $\epsilon-\delta$ definition

It will be the upper bound for the complexity of some algorithm, generally
### $\mathcal{O}$usama ranking

![[Pasted image 20241022223503.png]]
![[Pasted image 20241022223550.png]]

## Critical section of an algorithm
The section which is executed more than or equal to all other sections in an algorithm times
# Lecture 17
Recursion
- When a method calls itself
## Design
### Base case
When we want it to end
### Inductive case
When it aint over

The main idea w/ recursion is that your problem can be split into subproblems, and these can be split further but this process eventually terminates

- Tree -> subtree -> subtree -> null

When we are in a sub method call, we only have the information that was passed available to us. with this information, we must determine if we should take action, ending the recursion (base case), or pass the problem on to another method call (w/ modified passes ofc)
## Tail and head recursion
tail
- When the recursive call is the last thing performed
- Queue-like
	- Like, the methods will perform operations as they are called
head
- When the recursive step is executed first
- Stack-like
	- Like, the last methods in the stack call will be the first ones to actually perform operations
# Lecture 18
Discussion on recursion vs iterative approaches

![[Pasted image 20241022225119.png]]
# Lecture 19
## Polymorphic lists
Lists that utilize different types of classes as their 'nodes'
### Polymorphic linked list
- Nodes are either `EmptyList` or `NonEmptyList` 
- Either subclasses, or implementations of a shared class/interface (so they can be polymorphismd)

![[Pasted image 20241022225353.png]]
![[Pasted image 20241022225406.png]]

and then some asymptotic analysis example
# Lecture 20
- More asymptotic complexity
- Case analysis (see handout)
- Complexity of search/insert operations for arrays and linked lists
# Lecture 21
Array operations time complexities
![[Pasted image 20241022225724.png]]![[Pasted image 20241022225740.png]]
## Iterator interface
```java
public interface Iterator<E> {
	boolean hasNext();
	E next();
	void remove();
}
```

`hasNext()`
- will return `true` if there are element that have yet to have been returned at the time of calling
`next()`
- will return the 'next' `E` in the list. this does not have to be in order, especially since a list may not have a specific order to begin with
`remove()`
- optional; can be called once after each `next()` call to remove the element which was just returned by `next()`
### Iterator design
Classes that have iterators must implement the the `Iterable` interface
```java
public class Listler implements Iterable<T> {
	...
}
```
Then, it must have a method
```java
public Iterator<T> iterator() {
	return new ...
}
```
To return its iterator. Usually, the iterator for a class will be an inner class of that class (for convenience reasons, see slideshow). Iterators must be of the following form
```java
public Titrator implements Iterator<T> {
	boolean hasNext();
	E next();
	void remove();     //optional
}
```
as discussed before
## Collections framework
- A bunch of interfaces and classes and yadda yadda that stand for different types of data structures
- some algorithms too
Members are usually able to
- Add elements
- Find elements
- Remove elements
- Return size
- Iterate over elements
like they yknow are data structures

![[Pasted image 20241022230659.png]]
# Lecture 22
Notable methods for members of the collections framework

![[Pasted image 20241022230842.png]]

like its obvious what they do
## Collections class
Static class that contains methods designed to operate on collection members
- `sort()`
- `shuffle()`
- `copy()`
- `fill()`
That kind of thing
### Note about for loops
Enhanced for loops will just compile into loops that use `hasNext()` and `next()` which is why they only work on `Iterable` objects
## Stack (data structure)
First in, last out

![[Pasted image 20241023205816.png]]

### Common operations
Push
- Add element to stack
Pop 
- Remove top element
Peek
- Return top element w/o removing
isEmpty
- Empty or naw
### Runtime stack
Method stack calls. Behaves like an execution stack
### Stack implementations

![[Pasted image 20241023210031.png]]

see exam2 file
## Design patterns
Design patterns are descriptions of reusable solutions to common software design problems 
- They capture the experience of experts:
- Rationale for design 
- Tradeoffs 
- Codifies design in reusable form 
Goals: 
- Solve common programming challenges 
- Improve reliability of solutions 
- Aid rapid software development 
- Useful for real-world applications
### Types of design patterns
Creational
- Deals with the best way to create objects
Structural
- Ways to bring together groups of objects
Behavioral
- Ways for objects to communicate and interact
## The adapter pattern
- Convert existing interfaces to a new 

like, making stacks and queues using and already existing linked list
## Queues
First in, first out

![[Pasted image 20241023212259.png]]

### Operations
Enqueue
- Insert element into queue
Dequeue
- Remove element from queue
isEmpty
- is empty???
### Implementations

![[Pasted image 20241023213036.png]]
![[Pasted image 20241023213054.png]]

see exam2 file
# Lecture 23
## Trees
Self referential data structures. Trees can have any number of children but children can have at most one parent

![[Pasted image 20241023215106.png]]

Root
- Topmost element
- Element w/o a parent
Leaf
- Elements with no children
Interior elements
- Elements with children
Siblings
- Elements who share a parent
Descendants
- A node is a descendant of another if we can go up the tree and get to that node
Subtrees
- Like, the subtree bruhv
## Binary trees
Trees where nodes have at most two children
- Left
- Right
Like a linked list with two nexts
## Tree traversals

![[Pasted image 20241023215459.png]]

![[Pasted image 20241023215507.png]]

first three are depth-first searches

Consider the tree
![[tree.excalidraw]]

Preorder traversal:
18, 10, 8, 4, 7, 17, 14, 23, 20, 19, 29, 24, 32
In order traversal
4, 7, 8, 10, 14, 17, 18, 19, 20, 23, 24, 29, 32
Postorder traversal
7, 4, 8, 14, 17, 10, 19, 20, 24, 32, 29, 23, 18
Breadth-first
18, 10, 23, 8, 17, 20, 29, 4, 14, 19, 24, 32, 7

pre-order is like
- check
- go left
- go right

in order is like
- go left until null
- check

post order is like
- go to both, left first
- check

breadth first is like
- go by depth
## Binary search trees
Trees where the left element of a node is always less than it and the right element is always greater than its own

These can be constructed by inserting elements following this rule

![[Pasted image 20241023230029.png]]
# Lecture 24
## BST search
![[Pasted image 20241023230327.png]]
## BST insertion
![[Pasted image 20241023230619.png]]