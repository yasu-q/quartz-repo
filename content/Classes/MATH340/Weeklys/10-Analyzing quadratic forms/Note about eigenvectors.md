Ok so the reason why we can use
$$
\det(A - \lambda I) = 0
$$
To find $\lambda$ is because we had the expression
$$
(A-\lambda I){\bf v}={\bf 0}
$$
from
$$
A{\bf v} = \lambda {\bf v}
$$
Where ${\bf v} \neq {\bf 0}$  which is the definition of an eigenvector/eigen value. This means that the matrix $A-\lambda I$ has a non-trivial kernel space (${\bf 0}$ is not the only vector in the kernel space). This gives us
$$
\begin{pmatrix}
a_{11} & \cdots & a_{1n} \\
\vdots & \ddots & \vdots \\
a_{n1} & \cdots & a_{nn}
\end{pmatrix}
\begin{pmatrix}
v_1 \\
\vdots \\
v_n
\end{pmatrix}
=
{\bf 0}
$$
Which as you know implies that this matrix's row vectors are not linearly independent. By Theorem 5.5 in [[5.2 Row operations, matrix mult, and det]] this implies that the matrix's determinant will be zero.

THE MINIMUM AND MAX WILL BE THE EIGENVALUES