![https://www.youtube.com/watch?v=Av6x06E11nw](https://www.youtube.com/watch?v=Av6x06E11nw)

Suppose you have $n$ unit vectors evenly spaced around a circle such that the angle between each vector is given by $\frac{2\pi}{n}$ for $n > 1$. Why is it that summing these vectors yields ${\bf 0}$? 

![[circlevectors.png]]

Here, each vector $k$ will have components
$$
x = \cos(\theta_k)\hat{i}
\,\,\,\,\,\,\,\,\,\,\,\,\,\,\,\,\,\,\,\,\,\,\,\,\,\,\,\,\,
y = \sin(\theta_k)\hat{j}
$$
Where $\theta$ is given by $\frac{2k\pi}{n}$ with the $x$-axis. Then, the sum of every vector will be given by 
$$
\sum_{k=0}^{n - 1} {\bf v}_k = \sum_{k=0}^{n - 1}\left(\cos\left(\frac{2k\pi}{n}\right)\hat{i} + \sin\left(\frac{2k\pi}{n}\right)\hat{j}\right)
$$
Now, we must prove that both the $x$ and $y$ sums will lead to zero. This is where [[1.1 Complex numbers#Theorem 1.3 [Euler's formula](https //en.wikipedia.org/wiki/Euler%27s_formula)|Euler's formula]] comes in handy. We can represent each vector in the complex plane utilizing
$$
e^{i\theta_k} = \cos(\theta_k) + \hat{i}\sin(\theta_k)
$$
Here, they will be represented by taking into account that $\theta_k = \frac{2k\pi}{n}$
$$
e^{i\frac{2k\pi}{n}}= \cos\left(\frac{2k\pi}{n}\right) + i\sin\left(\frac{2k\pi}{n}\right)
$$
Thus, we can now simply prove that $\sum e^{i\frac{2k\pi}{n}} = 0$. To do this, lets expand the sum and analyze each term
$$
\sum_{k = 0}^{n - 1}e^{i\frac{2k\pi}{n}} = 1 + e^{i\frac{2k\pi}{n}} + e^{i\frac{4k\pi}{n}} + \dots + e^{i\frac{2(n-1)\pi}{n}} 
$$
Each term has a common factor $e^{i\frac{2\pi}{n}}$ which we can set equal to $x$. Doing this transforms the sum into 
$$
\sum_{k = 0}^{n - 1} x^k = 1 + x + x^2 + \cdots + x^{n-1}
$$
This is a [geometric series](https://en.wikipedia.org/wiki/Geometric_series) whose sum can be found by utilizing the formula
$$
\frac{1 - x^n}{1 - x}
$$
Substituting $x = e^{i\frac{2\pi}{n}}$ into the formula yields
$$
\Rightarrow \frac{1 - e^{i\frac{2\pi}{n}n}}{1 - e^{i\frac{2\pi}{n}}} = \frac{1 - e^{i2\pi}}{1 - e^{i\frac{2\pi}{n}}} = \frac{1 - 1}{1 - e^{i\frac{2\pi}{n}}} = 0
$$
Which implies,
$$
\sum_{k=0}^{n - 1} {\bf v}_k = \sum_{k=0}^{n - 1}\left(\cos\left(\frac{2k\pi}{n}\right) + i\sin\left(\frac{2k\pi}{n}\right)\right) = \sum_{k = 0}^{n - 1}e^{i\frac{2k\pi}{n}} = 0
$$
Thus summing all $k$ vectors indeed yields ${\bf 0} \, \square$ 