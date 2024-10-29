Lectures 1-13 important pts.
# Important vocab / concepts
## Method overloading
- Using the same method signature except for the parameter list
## Method overriding
- A method in a subclass overriding a method in a superclass **with the same method signature**
- **final** and **static** methods cannot be overridden
	- private methods are implicitly final and thus can't be overridden
- A subclass can call the superclass version of a method its overridden by using **super**
## Polymorphism
- The behavior of how superclass references can refer to subclass objects
## Composition
- When a class a a reference to another class as one of its fields
	- 'car has engine' and not 'car is engine'
- Composition is generally less complex, and preferred over subtyping
	- Of course, subtyping has its appropriate use cases over composition
## Dynamic method dispatch (dynamic method binding)
- In Java, when a subclass object is upcast to a superclass type and a method is called, Java uses **dynamic method dispatch** (also called **runtime polymorphism**). This means that even though the reference is of the superclass type, the actual method executed is determined by the **object's runtime type**, which is the subclass.
- The method called is the one associated with the actual object, not the reference
## Inheritance
- `is_a` relationships
- A class can at most extend from one other class
	- Classes can only (directly) inherit from one another class at a time
### Relating to interfaces
- Classes can implement an unlimited number of interfaces
- You can have interface methods, and they can refer to any object of a class that has implemented that interface
## Object class
- Contains no fields
- If not specified, a class will extend from Object
- Contains various methods like `equals()` and `toString()`
## Interfaces
- A 'contract' signed by a a class when it `implements` an interface
- Interfaces cannot be instantiated, as they aren't really meant to be objects
- Every method in an interface HAS to be implemented in a class that implements that interface
- Every field within an interface is `public static final` as a result of the fact that you cannot have an instance of an interface
- Interfaces can declare `default` method which will be the called if a class that implements the interface does not define the method
## Abstract classes
- An abstract class is sort of like an interface
- Methods in abstract classes are implicitly abstract, meaning they are left to be implemented in subclasses
- Abstract classes can have concrete methods
	- Can have constructors
	- private and protected fields
	- Can have non-static fields
	- Non-final fields
- You can have abstract class references, much like you can have interface references
- You have to implement every abstract method

![[Pasted image 20240929131803.png]]

## Generics
- More abstraction
- Code reusability
- `<T> <T extends Class> <T super Class>`
	- `<T>` is just any type
	- `<T extends Class>` is `T` so long as its a subtype of `T` (upper bounded)
	- You cannot add elements to data structures with this, only retreive
	- `<T super Class>` is `T` so long as it is a supertype of `T` (lower bounded)
	- You can add elements and retrieve from data structures with this
### Advantages
- For Java, generics make errors relating to classes doing this that aren't associated with it compile time instead of runtime, which is better.
- Not having to cast as often
### Wildcards
- `<?> or <? extends Class> or <? super Class>`
-  In Java, even if `S` is a subclass of `T`, a `Generic<S>` is not a subclass of `Generic<T>`
## Inner classes
- A class within the scope of another class
	- Everything inside an inner class, even private fields, are visible from within the outer class
	- Also, fields from the outer class are visible from with the inner class, even those that are private
- See node in linked list
- Inner classes are linked to their outer class, and must be instantiated alongside its outer class

![[Pasted image 20240929143907.png]]

### Example
```java
Outer outerInstance = new Outer();
Outer.Inner innerInstance = outerInstance.new Inner();
// yeah
```
### Static inner classes
- Can be instantiated without an instance of its enclosing class
	- Yes, they can be instantiated even though top level static classes don't even exist
- Can only access the outer class's static fields
## Lists
- Linear data structures
- I know what a list is
### Access
Lists (can) support the following access operations
- By value
- By index (indexing)
- Position relative to another element
- By time of addition
## Linked lists
please just watch

![vid](https://www.youtube.com/watch?v=WwfhLC16bis&ab_channel=CSDojo)

- First element is called the head
	- Entry point
- Last is the tail
	- Points to null
### Nodes
- What each 'box' is referred to in a linked list
- Store data and point to other node(s)
### Insertion (singly linked lists)
- Insert before head
	- Make new element point to head, and set head to new element
- After tail
	- Make tail point to new element, new element points to null
- Between two elements node1 and node2
	- Make new element point to node2
	- Make node1 point to new object
### Deletion
- Deleting the head
	- Set head to refer to node after head
- Deleting the tail
	- set node before tail to point to null
- Anything else: Consider prev. toDel next
	- make prev. point to next
	- make toDel point to null
### Common edge cases

![[Pasted image 20240929150447.png]]

please consider
### Linked list varieties
- Doubly linked
	- Nodes point to next and prev.
- Circular
	- Tail points to head
- Keeping a tail references
- Dummy head
	- First node is always a dummy
	- Has no data 
### Ordered lists
- Lists in which elements are kept in order as they are inserted
- More efficient for certain operations, like retrieval
- Insertions are less efficient
## Static things in a class
### Fields
- Static fields can be utilized in non-static methods of a class
- One copy is shared between all classes
### Methods
- Static methods cannot use non-static fields
### Inner
- Can only access outer class's static fields
# Lecture 1
## Data privacy

![[Pasted image 20240925214312.png]]

## Copies 

![[Pasted image 20240925214434.png]]

### Copy constructor

```java
// Copy constructor
public Person(Person another) { 
	this.name = another.name; 
	this.age = another.age; 
}
// ... In another class

// Creating an original object 
Person original = new Person("Alice", 30); original.display(); 
// Creating a copy of the original object using the copy constructor 
Person copy = new Person(original); copy.display();
```
# Lecture 2
nothing
# Lecture 3
## Initialization blocks and order

![[Pasted image 20240925215334.png]]

there are also enums I guess
# Lecture 4
## Comparable interface

![[Pasted image 20240925215739.png]]

## Inheritance !

![[Pasted image 20240925215830.png]]

### Superclass constructor
Java will call the no argument superclass constructor. If a superclass has no no-argument constructor, then you MUST call some superclass constructor from within the subclass using super().

*Supertest has no no-arg constructor*
![[Pasted image 20240925220300.png]]

If there is a superclass no arg constructor, then Java will just call that at the top of every constructor in the subclass. This will happen for every constructor in a subclass UNLESS super() is called at some point within the constructor. It needs to be the first line of the constructor, btw
### Polymorphism

![[Pasted image 20240925220714.png]]

See 

![[Pasted image 20240925220823.png]]
### Using instanceOf and getClass()

instanceOf:
``` java
object instanceof ClassName
```
- instanceOf is a keyword in Java
- checks (at runtime) whether an object is of type ClassName
	- is the object is a subclass of ClassName, then it is an instance of ClassName
	- if ClassName is an interface and object implements the interface, than the object is an instance of the interface
	- If this is a superclass checking against a subclass, then it is not an instance 
- Boolean thing, obv.

getClass()
``` java
Object reference = new Object();
reference.getClass();
```
![[Pasted image 20240925222023.png]]
- Specific to class, see tester code
## Down and up casting
### Down casting
- Casting a superclass to a subclass
- Usually not a good idea
- Like, you might end up casting a superclass object to a subclass and call a subclass method, at which point you die
### Up casting
- Casting a subclass to a superclass
- Should always be safe

![[Pasted image 20240926225359.png]]
# Lecture 5
- Avoid using instanceOf and getClass
- Dynamic method binding, see top of file
### Protected
- Lets fields be visible to subclass objects, but not to outsiders
### Misc.
- A subclass can have fields with the same name as ones from a superclass
	- not encouraged
	- this does NOT override a superclass field (see code snippet)

``` java
class Superclass {
    private final int number = 2;
    
    public int getNumberFromSuperclass() {
        return number;
    }
}

class Subclass extends Superclass {
    public int number = 4;
    
    public int getNumberFromSubclass() {
        return number;
    }
}

public class Main {
    public static void main(String[] args) {
        Subclass subclass = new Subclass();
        
        // Accessing the subclass's 'number'
        System.out.println(subclass.number);  // Outputs 4
        
        // Accessing the superclass's 'number' via method
        System.out.println(subclass.getNumberFromSuperclass());  // Outputs 2
    }
}
```
# Lecture 6
- A class inherits a method from the nearest superclass where its defined or overridden

![[Pasted image 20240929123203.png]]

- YOU CANNOT CHAIN SUPER
## Final classes
- Cannot be extended
- Guarantees that classes that are meant to immutable (String) don't behave in weird ways
# Lecture 7
### Composition
- When a class has a reference to another as one of its fields
### Abstract classes
- Implementation left for subclasses
- kind of like an interface
## Generics
- minor points about why we might want generics
# Lecture 8
## Generics
- More abstraction
- Code reusability
### Advantages
- For Java, generics make errors relating to classes doing this that aren't associated with it compile time instead of runtime, which is better.
- Not having to cast as often

![[Pasted image 20240929142842.png]]

idk why you want to do this
# Lecture 9
same old on generics
## Inner classes
- A class within the scope of another class
	- Everything inside an inner class, even private fields, are visible from within the outer class
	- Also, fields from the outer class are visible from with the inner class, even those that are private
- See node in linked list
- Inner classes are linked to their outer class, and must be instantiated alongside its outer class

![[Pasted image 20240929143907.png]]

### Example
```java
Outer outerInstance = new Outer();
Outer.Inner innerInstance = outerInstance.new Inner();
// yeah
```
# Lecture 10
### static inner classes
- see top of file
## Lists
- Linear data structures
- I know what a list is
### Access
Lists (can) support the following access operations
- By value
- By index (indexing)
- Position relative to another element
- By time of addition
## Linked lists
please just watch

![vid](https://www.youtube.com/watch?v=WwfhLC16bis&ab_channel=CSDojo)

- First element is called the head
	- Entry point
- Last is the tail
	- Points to null
### Nodes
- What each 'box' is referred to in a linked list
- Store data and point to other node(s)
### Insertion (singly linked lists)
- Insert before head
	- Make new element point to head, and set head to new element
- After tail
	- Make tail point to new element, new element points to null
- Between two elements node1 and node2
	- Make new element point to node2
	- Make node1 point to new object
### Deletion
- Deleting the head
	- Set head to refer to node after head
- Deleting the tail
	- set node before tail to point to null
- Anything else: Consider prev. toDel next
	- make prev. point to next
	- make toDel point to null
# Lecture 11
- nothing
# Lecture 12
### Linked list varieties
- Doubly linked
	- Nodes point to next and prev.
- Circular
	- Tail points to head
- Keeping a tail references
- Dummy head
	- First node is always a dummy
	- Has no data 
### Ordered lists
- Lists in which elements are kept in order as they are inserted
- More efficient for certain operations, like retrieval
- Insertions are less efficient
# Lecture 13
## Linked lists vs regular lists
### pros of a linked list
- more naturally dynamic
### Cons
- Insertion
- Addition
- Retrieval