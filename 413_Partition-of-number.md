<span style="color:#28a745">Definition</span>

Partition of a positive integer $n$ is a representation of $n$ as an unordered sum of one or more positive integers, called parts.



<span style="color:#28a745">Definition</span>

The Ferrers diagram, also called Young diagram, of a partition ==...==



<span style="color:#28a745">Definition</span>

The conjugate of a partition $\lambda$ ==...==

<span style="color:#28a745">Definition</span>

==self-conjugate== if $\lambda = \lambda^*$



### <span style="color:#3c66b5">Theorem</span>

The number of self-conjugate partitions of $n$ is also the number of partitions of $n$ into distinct, odd parts.

**"Proof"**

$20 = 5 + 3 + 3 + 3 + 1 + 1 + 1 + 1 + 1 + 1$

Our goal is to build a bijection between odd parts and disctinct parts.

Express 20 as: 
$$
\begin{align*}
20 &= 1 \cdot 5 + 3 \cdot 3 + 6 \cdot 1\\
&= 1 \cdot (5) + 3 \cdot (2^1 + 2^0) + 1 \cdot (2^1 + 2^2) && \text{binary}\\
&= 5 + 3 \cdot 2 + 3 + 2 + 2^2
\end{align*}
$$
We observe that the last expansion must have distinct numbers added together. This is true 





### <span style="color:#3c66b5">Theorem</span>

Let $p_n$ be the number of partitions of $n$. Then, we have:
$$
\sum_{n=0}^{\infty}p_nx^n = \prod_{k=1}^{\infty}(1-x^k)^{-1}
$$
<span style="color:#eb861c">Proof</span>
$$
\frac{1}{1-x^k} = \sum_{j=1} x^{jk}
$$
$\implies$
$$
\sum_{n=0}^{\infty}p_nx^n \overset{?}{=} \left( \sum_{j=1} x^{jk} \right)
$$
We are interested in the coefficients of $x^n$ of the left side. This is equal to the number of equations to: 
$$
k_1 \cdot 1 + k_2 \cdot 2 + k_3 \cdot 3 + \ldots + k_n \cdot n = n
$$












