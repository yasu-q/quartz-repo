- Making an ordered linked list
``` java
public class OLinkedList<T extends Comparable<T>> 
	implements Comparable<OLinkedList<T>>
```
- Methods should throw exceptions for bad calls and leave the list unmodified
	- Null passes
- **==THROW IllegalArgumentException IF PARAM NULL==**\
### 3.2 Copy constructor
- MAKE A DEEP COPY
### 3.3 add element
- insertion has to be sorted
### 3.5 get element (int)
- don't mind the vulnerability of returning a reference to the object cause like that's what the method has to do so 
- return LAST ELEMENT if duplicates
### 3.6 search for element
- If no element found, return null
### 3.8 get index of element
- return index of FIRST element found (if duplicates)
### 3.11 sub list
- from first occurrence of first to first occurrence of second, inclusive
- new list must be independent of list copied from
	- deep copy thing
- if first element = second element, the list should be 1 object long
### 3.12 compareTo
- if same number of elements the same and all elements match, return 0
- if param list's first non matching element is greater than this's element, return -integer
- if param list's first non matching element is less than this's element, return +integer
- if all in order but length mismatch
	- -integer if the tail param  (of other) is greater
	- +integer if the tail param is less