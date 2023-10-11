# Inclusion-Exclution Principle



<span style="color:#04c2b2">Problem</span> Count the number of integers between 1 and 600, inclusive, which are divisible by 2 or 3.

**Solution:** 

$A = \{n : 2 \mid n, n \in [600]\}$

$B = \{n : 3 \mid n, n \in [600]\}$

$|A \cup B| = |A| + |B| - |A \cap B| = 300 + 200 - 100$

<img src='https://raw.githubusercontent.com/helloboyxxx/images-for-notes/master/uPic/Sketch.png' alt='Sketch' style="zoom:50%;" />

### <span style="color:#3c66b5">General form of the Inclusion-Exclusion Principle</span>

==...==

<span style="color:#28a745">Notation</span>
$$
1_{v\in S}
\begin{cases}
1& \text{if } v\in S\\
0& \text{otherwise}
\end{cases}
$$
<span style="color:#eb861c">Proof</span>

<img src='https://raw.githubusercontent.com/helloboyxxx/images-for-notes/master/uPic/Sketch 2.png' alt='Sketch2' style="zoom:33%;" />

$|A\cup B \cup C| = |A| + |B| + |C| - |A\cap B| - |B\cap C| - |A\cap C| + |A \cap B \cap C|$

It suffices to prove the following: 

Let $v \in \bigcup_{i=1}^{n} A_i$. Then,
$$
1_{v \in \bigcup_{i=1}^{n} A_i} = 
\sum_{i=1}^{n} 1_{v\in A_i} 
- \sum_{i,j \in \binom{[n]}{2}}1_{v \in A_i} + \ldots
+ \sum_{1, 2, 3\ldots n \in \binom{[n]}{n}} 1_{v \in A_1 \cap \cdots \cap A_n}
$$
Define
$k = \# \{i : v \in A_i\} \geq 1$

Suppose $v \in A_1, \ldots, A_k$ and $v \not \in A_{k+1}, \ldots A_n$

==Alternating sum==



