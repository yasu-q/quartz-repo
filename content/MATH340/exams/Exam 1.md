**09/30**

See [[Exam 1, Study Guide.pdf]]
All problems come from homework, check answers [here](https://umd.instructure.com/courses/1370507/files/folder/Homework)

Will be on subjects from week 1-4
### Week 1
- [[1.1 Sets]]
- [[1.2 Functions]]
- [[1.3 Proofs]]
- [[1.4 Vector spaces]]
- [[01_notes.pdf]]
### Week 2
- [[2.1 Subspaces]]
- [[2.2 Linear dependency, spanning, and basis]]
- [[2.3 Example subspaces, row, and col spaces]]
- [[2.4 System of Linear Equations]]
- [[02_notes.pdf]]
### Week 3
- [[3.1 Dimension of vector spaces]]
- [[3.2 Pivot analysis]]
- [[3.3 Inner product and angles]]
- [[03_notes.pdf]]
### Week 4
- [[4.1 Norms]]
- [[4.2 Linear transformations and matrix operations]]
- [[4.3 Kernel and image]]
- [[04_notes.pdf]]

# 1.1 Sets
## Set
A set is an unordered list of elements. They are denoted with curly braces. Note that order and repetition **does not matter** meaning {1, 2, 2} is equivalent to {1, 2} which is equivalent to {2, 1}
## Well defined set
A set whose elements fulfill some conditions
$$
A = \{x \in \mathbb{Z} | \text{x is even}\}
$$
'the set of all evens'
## Subsets
A set $A$ is a subset of another set $B$ if all the elements within $A$ are also within $B$
$$
x \in A \Rightarrow x \in B
$$
Meaning $A \subseteq  B$. $A$ is a proper subset of $B$ if it is a subset, but not equal to $B$.
## Unions and intersections
A union $C$ between two sets $A$ and $B$ is a set which contains all elements that are located in $A$ or $B$ (or both)
$$
C = \{x |x \in A \text{ or } x \in B\}
$$
A union $D$ between two sets $A$ and $B$ is a set which contains all elements that within BOTH $A$ AND $B$
$$
D = \{x | x \in A \text{ and } x \in B\}
$$
## The empty set
The empty set is the set which contains no elements. It is usually denoted as $\emptyset$ or $\{\}$
## Equality of sets
Two sets $A$ and $B$ are equal iff 
$$
A \subseteq B \text{ and } B \subseteq B
$$
In proofs, this is the usual two step procedure for showing two sets are equal.

SEE EXAMPLES IN [[1.1 Sets]]
## Ordered pairs
An ordered pair $(a,b)$ is what you would expect an ordered pair to be 
$$
(a,b) = (c, d) \iff a=c \text{ and } b=d
$$
## Cartesian product
The set of all tuples that can be made out of two sets
$$
A \times B = \{(a, b) | a \in A \text{ and }b \in B\}
$$
Like, you can make the cartesian plane if you do $\mathbb{R} \times \mathbb{R}$ because yeah
## Disjoint sets
Two sets are disjoint if their intersection is the $\emptyset$. A set of sets is pairwise disjoint they are all disjoint relative to one-another.
## Difference of sets
$A -B$ is defined the set of all elements in $A$ but not in $B$
$$
C = \{x \in A \text{ and } x \notin B\}
$$
### Complement of a set
The complement of a set $A$ is $A^c$ is defined as the set of EVERY element not in $A$. EVERY depends on your universal set. If $U$ is $\mathbb{R}$ and $A = \{1,2,3\}$, then $A^c = \mathbb{R}- \{1,2,3\}$
## Demogorgon's law
'The complement of intersections is the same as the union of complements'
'The complement of unions is the same as the intersection of complements'
![[Pasted image 20240925183643.png]]

# 1.2 Functions
A function $f : A \rightarrow B$ is a mapping of elements from $A$ onto $B$.
$f : \mathbb{R} \rightarrow \mathbb{R}, f(x) = x^2$ 
Inputs are all real numbers, (possible) outputs are all r.
'define domain and codomain' vs 'find domain and range'
## Surjectivity
A function is surjective (onto) if for every element in the codomain, there is at least one element in the domain that maps to it
## Injectivity
A function is injective if inputs have inputs have unique outputs
## Bijectivity
The two conditions above
## Identity function
Sends every input back to itself
## Invertibility
A function $f$ is invertible if there is some function $g$ such that $f  \circ g = \text{id}$ 
See example in [[1.2 Functions]]
## Images and pre-images
The image is the range of the function. The set of all possible outputs of the function (this lives in the codomain. the image is always either equal to the codomain or it is a subset of the codomain)
The pre-image a set of inputs within the domain that lead to outputs in the codomain
'the set of x such that f(x) is in the {input set, in codomain}'.
## Theorem 1.2
Let $f$ be from $A$ to $B$. Let $S$ be a subset of $A$. Then $S$ is always at least a subset of $f^{-1}(f(S))$ 
because $f(S)$ will spit out all, well $f(S)$ and $f^{-1}(\text{that})$ will spit out all inputs that can lead to those outputs. Note that sometimes they are not equivalent because the outputs from $f(S)$ might sometimes have other valid inputs that lead to those outputs. But $S$ will always be contained within those outputs by definition (because if is one of those valid outputs)

Let $T_i$ be in the codomain. The pre image of the union of all $T_i$ is the same thing as the union of the pre image of all $T_i$

Same thing for intersections.
# 1.3 Proofs
General points
- Don't give an example for universal statements
- Always be clear in what variables mean
- Only assume what was give in the assumption (and prev example or stuff we went over in class)
- Justify steps
- for iff statements both sides need to be proved
## Direct proof
Show something is true directly
## Proof by contradiction
Show that if we make an assumption (usually against what we want to prove), than that leads to some sort of contradiction, thus our assumption was wrong (meaning what we wanted to prove must be true)
## Proof by inductions
Base case --> hypothesis --> inductive step
idfk tbh
# 1.4 Vector spaces
## Vector
its a vector. an $n$-tuple. you know.
## Operations
- scalar multiplication
- addition
## Properties of a vector space
- Closure
	- Adding two vectors within the space won't escape it
- Associativity
	- Normal math associativity for vectors
- Commutativity
	- Normal math commutativity for vectors
- Additive identity
	- there is some vector so that if we take a vector and add that vector we get the same vector (like 1 + 0 =1)
- Distributivity
	- Normal math distributivity
- Multiplicative identify
	- 1 *$\vec{a} = \vec{a}$
	- Yes this is implied by scalar multiplication but in more abstract vector spaces that may not be the case
## 2.1 Subspaces
A subspace $W$ is $\mathbb{R}^n$ is a subset of it such that it fulfills the definition of a vector space. see subspace criterion in [[2.1 Subspaces]]

- $\{0\} \in \mathbb{R}^2$ is a subspace
- Lines going through the origin are subspaces
# 2.2 Linear dependency, spanning, and basis
## Linear dependency
A set of vectors is linearly dependent if we can write of these the vectors as a linear combination of the others OR just
$$
c_1{\bf v}_1 + \dots + c_n{\bf v}_n = 0, \exists c_1, \dots, c_n \text{ not all } 0
$$
So not all $c_i$ need to be zero in order for the whole sum to be zero.
## Spanning
A set of vectors $W$ spans a subspace $V$ if we can write all vectors in $V$ are linear combinations of the vectors in $W$.
## Basis
A set of vectors $W$ serves as a basis for $V$ which is a subspace if they span $V$, are within $V$, and are linearly independent.
# 2.3 Example subspaces
- The span of a set of vectors is always a valid subspace
- The zero vector is a valid subspace
- $\mathbb{R}^n$ is always a subspace of itself
## 2.6 Matrices
You know what a matrix is. A matrix $A$ with $n$ columns and $m$ rows ($n \times m$) is like a matrix yknow
$$
\begin{pmatrix}
1 & 2 & -1 \\
0 & 4 & 2
\end{pmatrix}
$$
$2 \times 3$ (two rows, three columns)
## 2.7 Row and column spaces
Row and column spaces of matrices are always valid subspace
# 2.4 System of linear equations
A system of linear equations is defined as scalar times variable + scalar times variable ... = some number
$$
\begin{matrix}
3x + 2y - z = 4 \\
x + 3y -2z = 1 \\
5x + y - z =4
\end{matrix}
$$
We can use augmented matrices to solve these using row operations
$$
\left( 
    \begin{array}{ccc|c}
        3 & 2 & -1 & 4 \\
        1 & 3 & -2 & 1 \\
        5 & 1 & -1 & 4
    \end{array}
\right)
$$
Row echelon form, and if possible reduced row echelon form. Note a few things
- A system can only have the following as solutions
	- Exactly one
	- None
	- Infinitely many
- If a system has exactly one solution, then its matrix can be put into rref 
- If a system has no solution (is inconsistent) or has infinitely many, its matrix can't be put into rref (IN A WAY THAT MAKES THE SYSTEM MAKE SENSE)
### Row echelon form
- Forms a staircase
- All entries below pivot zero
- First nonzero entry of a row is the pivot
### Reduced row echelon
- Pivots are zero
- Entries above and below are zero
- Pivots are only the number one
## Theorem 2.4
Every matrix can be turned into reduced row echelon. Yes, this applies to augmented matrices for all systems.
## Pivots 
Pivot entries are the first non-zero entry in a matrix in row echelon/reduced row echelon form. The column of each pivot is called a pivot column
## Homogenous systems
Systems of equations which all equal to zero. 
$$
\begin{matrix}
a_{11}x_1 + a_{12}x_2+...+a_{1n}x_n = 0 \\
a_{21}x_1 + a_{22}x_2+...+a_{2n}x_n = 0 \\
... \\
a_{m1}x_1+a_{m2}x_2+...+a_{mn}x_{n} = 0
\end{matrix}
$$
These systems always have the trivial solution where all variables equal to zero.
## Theorem 2.5
Any homogenous system that has less equations that variables has a nontrivial solution

This also implies that $n + 1$ vectors in $\mathbb{R}^n$ are linearly dependent. 
If a homogenous system has even one solution other than the trivial, that means it has infinitely many which also means that its rows (and columns) are linearly dependent.
# 3.1 Dimension of vector spaces
## Theorem 3.1
If $V$ is a subspace of $\mathbb{R}^n$, then there is some basis for $V$ containing $m$ vectors where $m \leq n$. Note
- The only time where $m = n$ is if $V$ is $\mathbb{R}^n$ itself
## 3.1 Dimension of a vector space
A subspace $V$ has a dimension of $m$ where $m$ is the number of vectors that make up $V$'s basis
# 3.2 Pivot analysis
## Theorem 3.3
Let $A$ be a matrix

- The dimension of the row space is equal to the number of pivot entries in echelon form
	- The non-zero rows of A in echelon form will form a basis for row A
- The dimension of the column space is equal to the number of pivot columns
	- The pivot columns in the original $A$ will form a basis for col B
- dim Row = dim Col 
## Rank 
The rank of a matrix is the dimension of the row/col space (they both have the same dimension). This means that the rank of a matrix is also the number of pivot entries/columns
## Transpose
The transpose of a matrix $A$ is a matrix $A^T$ in which the rows of and columns of $A$ were swapped
## Theorem 3.4
The rank of $A$ is the same as the rank of $A^T$
## Null/kernel space
the set of vectors within the domain of a linear function $T$ such that
$$
M_T {\bf v} = 0
$$
Note that the kernel is orthogonal to the row space 
# 3.3 Inner product and angles
## Inner product
An inner product is some function that takes in two vectors and spits out a scalar. It must have the properties:

- $I(v,v) > 0$ for all $v \neq 0$
- $I(v, w) = I(w, v)$
- $I(av + bw, z) = aI(v, z) + bI(w, z)$

strange
## Dot product
This is the standard inner product in Euclidean geometry. Assume this if problem does not specify inner product. Given by lining up terms of vectors, multiplying, and adding them up
### Length of a vector
The length of a vector is given by $\sqrt{\langle {\bf v}, {\bf v} \rangle}$ because magnitude squared is inner product yadda yadda. With the dot product, this is just the distance formula for whatever $n$ v is in.
## Orthogonality
Two vectors are orthogonal if their inner product is equal to zero.
## Theorem 3.5 Pythagorean Theorem
$$
||\vec{v}||^2 + ||\vec{w}||^2 = ||\vec{v} + \vec{w}||^2
$$
## Theorem 3.6 Cauchy-Schwarz
$$
\langle {\bf v}, {\bf w} \rangle \leq ||{\bf v}|| \space ||{\bf w}||
$$
In fact, equality will only hold if either zero or w is a linear scaling of v i.e. if vectors are linearly dependent
## Theorem 3.8 Grandma-Smith
if v_1 ... v_n are linearly independent, then you make make an orthogonal basis

![[Pasted image 20240912193143.png]]
## 3.8 Orthonormality
A set of vectors is said to be orthonormal if the inner product of every one of them with every other one. this implies that they all have length 1
## 3.9 Orthogonal Complement
The orthogonal complement of a vector subspace $W$ is the subspace of vectors orthogonal to EVERY vector in $W$. its denoted as $W^\perp$
## Theorem 3.9
let $W \in \mathbb{R}^n$
$$
\dim W + \dim W^\perp = n
$$
# 4.1 Norms
A norm of R^n is some function that assigns vectors a nonnegative number. a normal has to satisfy the following properties:

1. $||\vec{v}|| \gt 0$ for every non zero $\vec{v} \in \mathbb{R}^n$ (Positivity)

2. $||\vec{v} + \vec{w}|| \leq ||\vec{v}|| + ||\vec{w}||$ for every $\vec{v}, \vec{w} \in \mathbb{R}^n$ (Triangle Inequality)

3. $||c\vec{v}|| = |c| \space ||\vec{v}||$ for every $\vec{v} \in \mathbb{R}^n$ and $c \in \mathbb{R}$ (Homogeneity)

## Theorem 4.1
If an inner product is defined in R^n, then the following is a norm
 $$
 ||\vec{v}|| = \sqrt{⟨\vec{v}, \vec{v}⟩}
 $$
yes this is the length as defined in 3.3 or something like that.
 Norms can have my forms, so long as they fulfill the requirements. If a norm is not specified, the standard Euclidean norm is utilized
# 4.2 Linear transformations and matrix operations
A linear transformation is some function between two subspaces that fulfills the following requirements:

1. $L(\vec{v} + \vec{w}) = L(\vec{v}) + L(\vec{w})$ (Additivity)

2. $L(c\vec{v}) = cL(\vec{v})$ (Homogeneity)
## Theorem 4.2
You can prove a function is linear via showing one of these:

1. $L$ is linear (no shit)

2. $L(\vec{u} + c\vec{v}) = L(\vec{u}) + cL(\vec{v})$ for all $\vec{u}, \vec{v} \in V$ and all $c \in \mathbb{R}^n$

3. $L(a\vec{u} + b\vec{v}) = aL(\vec{u}) + bL(\vec{v})$ for all $\vec{u}, \vec{v} \in V$ and all $c \in \mathbb{R}^n$
## Matrix-column multiplication
You have a matrix with $n$ columns, you can take the dot product of every row with a column vector with $n$ rows.
## Theorem 4.3
Every linear function can be written in the form
$$
f({\bf v}) = M_f {\bf v}
$$
Where $M_f$ is a matrix that uniquely describes f's linear transformation. The columns of this matrix are given by taking $f{\bf e_i}$ at each $i$th column
## Matrix multiplication
ROW 1, DOT WITH FIRST COLUMN, FIRST ENTRY OF FIRST ROW
ROW 1, DOT WITH SECOND COLUMN, SECOND ENTRY OF FIRST ROW
...
ROW 2, DOT WITH FIRST COLUMN, FIRST ENTRY OF SECOND ROW
ROW 2, DOT WITH SECOND COLUMN, SECOND ENTRY OF SECOND ROW
... keep going
## Theorem 4.4
If $f$ and $g$ are linearly functions, then the matrix of their composition $g \circ f$ is given by $M_g M_f$
\
like, apply first transformation (f), then second $g$. pretty obv
## Identity matrix
please see [[Identity matrix]]
## Sum of matrices
sum each matrix by element. not difficult (they must have matching dimensions)
## Theorem 4.5
properties of matrix multiplication

1. $A(BC) = (AB)C$ (Associativity)

2. $A(B + C) = AB + AC$ (Distributivity)

3. $AI_n = A$ and $I_mA = A$ (Multiplicative Identity)

4. $r(AB) = (rA)B = A(rB)$ 

please note that commutativity is not one of them
## Commuting matrices
two matrices commute if they are commutative, wow
# 4.3 Kernel and image
The kernel of a linear transformation is the set of vectors in the domain such that L(v) = 0. 
The range / image of a linear function are the actual outputs of a function. as a result, the image to the codomain if a function is surjective.
## Theorem 4.6
Is $L$ is some linear function, then the kernel of L and its image are subspaces of V
## Theorem 4.8
suppose you have some linear function $L$, then
1. Im $L = \text{Col} (A)$ 

2. Ker $L = (\text{Row}(A))^\perp$

3. dim Ker $L$ + dim Im $L$ = $n$
## Theorem 4.9 Rank-Nullity
Let $V$ and $W$ be a vector subspaces, and $L : V \rightarrow W$ be a linear Transformation. Then,
$$
\dim\text{Ker } L + \dim\text{Im} L = \dim V
$$
