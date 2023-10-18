# Inclusion-Exclution Principle



<span style="color:#04c2b2">Problem</span> Count the number of integers between 1 and 600, inclusive, which are divisible by 2 or 3.

**Solution:** 

$A = \{n : 2 \mid n, n \in [600]\}$

$B = \{n : 3 \mid n, n \in [600]\}$

$|A \cup B| = |A| + |B| - |A \cap B| = 300 + 200 - 100$

<img src='https://raw.githubusercontent.com/helloboyxxx/images-for-notes/master/uPic/Sketch.png' alt='Sketch' style="zoom:50%;" />

### <span style="color:#3c66b5">General form of the Inclusion-Exclusion Principle</span>

Let $A_1,\ldots, A_n$ be a sequence of finite sets. Then,

$$\left | \bigcup_{i=1}^n A_i\right | = \sum_{i \in [n]} |A_i|-\sum_{ij \in \binom{[n]}{2}}|A_i \cap A_j|+\ldots+(-1)^{n+1}\sum_{i \in \binom{[n]}{n}} |A_i|,$$

Where $[n]= \{1,\ldots,n\}$ and $\binom{[n]}{i}=\{A\subseteq [n]: |A|=i\}$. 



It is important to see that the size of the set $\left|\binom{[n]}{i}\right| = \binom{n}{i}$.

<span style="color:#eb861c">Proof</span>

<span style="color:#28a745">Notation</span>
$$
1_{v\in S}
\begin{cases}
1& \text{if } v\in S\\
0& \text{otherwise}
\end{cases}
$$
<img src='https://raw.githubusercontent.com/helloboyxxx/images-for-notes/master/uPic/Sketch 2.png' alt='Sketch2' style="zoom:33%;" />

There is a simple case: 

$$
|A\cup B \cup C| = |A| + |B| + |C| - |A\cap B| - |B\cap C| - |A\cap C| + |A \cap B \cap C|
$$

It suffices to prove the following: 

Let $v \in \bigcup_{i=1}^{n} A_i$. Then,
$$
1_{v \in \bigcup_{i=1}^{n} A_i} = 
\sum_{i=1}^{n} 1_{v\in A_i} 
- \sum_{i,j \in \binom{[n]}{2}}1_{v \in A_i \cap A_j} + \ldots
+ \sum_{1, 2, 3\ldots n \in \binom{[n]}{n}} 1_{v \in A_1 \cap \cdots \cap A_n}
$$
Define $k = \# \{i : v \in A_i\} \geq 1$. Suppose $v \in A_1, \ldots, A_k$ and $v \not \in A_{k+1}, \ldots A_n$.	$\blacksquare$

==Alternating sum==



**There is another form:**

Let $A_1, \ldots A_n$ be a sequence of finite subsets of a finite set then:
$$
|\bar A_1 \cap \bar A_2 \cap \cdots \cap \bar A_n| = |S| - |\bar A_1 \cup \bar A_2 \cup \cdots \cup \bar A_n|
$$
<span style="color:#eb861c">Proof</span>

1. $\subseteq$

$$
\begin{align*}
x \in |\bar A_1 \cap \bar A_2 \cap \cdots \cap \bar A_n|\\
\implies x \not \in A_i, \forall i\\
\implies x \not \in \bigcup A_i
\end{align*}
$$

2. $\supseteq$

$$
\begin{align*}
x \in |\bar A_1 \cup \bar A_2 \cup \cdots \cup \bar A_n|\\
\implies x \not \in A_i, \forall i\\
\implies x \not \in \bigcap A_i
\end{align*}
$$

==??? correct?==







<span style="color:#04c2b2">Exercise</span>

How many permutation of MATH IS ==FUN...==

**Solution:**

Let $\mathcal{P} = $ set of all permutations. 

$A_M = \set{\text{permutations in } \mathcal{P} \text{ with MATH occurring as continuous letters}}$

$A_I = \set{\text{permutations in } \mathcal{P} \text{ with IS occurring as continuous letters}}$

$A_F = \set{\text{permutations in } \mathcal{P} \text{ with FUN occurring as continuous letters}}$

Bad permutations $= A_M \cup A_I \cup A_F$. Then by the inclusion-exclution principle: 
$$
\begin{align*}
|A_M \cup A_I \cup A_F| &= |A_M| + |A_I| + |A_F| \\
&- |A_M \cap A_I| - |A_M \cap A_F| - |A_F \cap A_I|\\
&+ |A_M \cap A_I \cap A_F|
\end{align*}
$$
The rest is to put MATH, IS, and FUN as group respectively. Putting MATH as a group gives us $|A_M| = 6!$. Putting MATH and FUN as group at the same time gives us $|A_M \cap A_F| = 4!$.

None of them occurs is: $9! - |A_M \cup A_I \cup A_F|$. Done. 



### Combinations with repetition

Previously, we have learned $\binom{n}{r}$ and Theorem 2.5.1 $\binom{r+k-1}{r}$. What happens in between?



<span style="color:#04c2b2">Problem</span>

Determine the number of 10-combinations of the multiset $T = \set{3\cdot a, 4\cdot b,5\cdot c}$.

**Solution:**

It is not easy to apply inclusion-exclution on this directly. But we can do some trick. 

Define $S$ to be the set of $n$-combinations of the set $\set{10 \cdot a, 10 \cdot b, 10 \cdot c}$.

$|S| = \binom{10+3-1}{10} = \binom{12}{2}$ by theorem 2.5.1. Then, we want to find the bad combinations.

Note that every combination in the set $T$ has at most $3a, 4b, 5c$. Whenever all of these three conditions are not satisfied, we put it into the "bad combination".

$A_1 = $ combinations in $S$ with $\geq 4 $ a's

$A_2 = $ combinations in $S$ with $\geq 5 $ b's

$A_3 = $ combinations in $S$ with $\geq 6 $ c's

Then, the number of 10-combinations of $T = |S| - |A_1 \cup A_2 \cup A_3|$. 

$|A_1| = $ number of solutions of $x_1 + x_2 + x_3 = 10$ with $x_1 \geq 4$. This is equivalent to: number of solutions of $x_1 + x_2 + x_3 = 6$. Apply theorem 2.5.1, we get $\binom{6+3-1}{6} = \binom{8}{6}$

$|A_1| = \binom{8}{2}$, $|A_2| = \binom{7}{2}$, $|A_3| = \binom{6}{2}$

Similarly, $|A_1 \cap A_2| = $ number of solutions of $x_1 + x_2 + x_3 = 10$ with $x_1 \geq 4, x_2 \geq 5$. This is equivalent to: number of solutions of $x_1 + x_2 + x_3 = 1$. There are 3.

$|A_1 \cap A_2| = 3, |A_1 \cap A_3| = 1, |A_2 \cap A_3| = 0$. 

The intersection of these three is $0$. Now, we can apply the inclusion-exclution principle.





### Dearangements

At a party, 10 gentlemen check their hats. In how many ways can their hats be returned so that no gentleman gets the hat with which he arrived?

<span style="color:#28a745">Definition</span>

A derangement of $[n] := \set{1, 2, \ldots, n}$ is a permutation $i_1i_2\cdots i_n$ of $[n]$ such that $i_j \neq j$ for all $j \in [n]$.




### <span style="color:#3c66b5">Theorem</span>

For $n \geq 1$, 
$$
D_n = n!(1 - \frac{1}{1!} + \frac{1}{2!} - \frac{1}{3!} + \cdots + (-1)^n \frac{1}{n!})
$$



$$
\begin{aligned}
e^x=\sum_{i=0}^{\infty} \frac{x^i}{i !} & \\
D_n \sim \frac{n !}{e}\\
\lim _{n \rightarrow \infty} \frac{D_n}{n !}=\frac{1}{e}
\end{aligned}
$$

When $n \to \infty$, the probability of a dearangement is $\frac{1}{e}$.

<span style="color:#eb861c">Proof</span>

$\mathcal{P} = $ permutations of $[n]$

Bad sets: for $i \in [n]$ define: $A_i = $ number of permutations where $i$ is in the $i^{th}$ position. 

Notice that, given $k$-indicies $i_1, \ldots, i_k \in [n]$ all distinct. What is $|A_{i_1} \cap A_{i_2} \cap \cdots \cap A_{i_k}| = (n-k)!$


$$
\begin{align*}
\left|\bigcup_{i=1}^n A_i\right|&= \sum_{i=1}^{n}|A_i| 
- \sum_{\set{i_1,i_2} \in \binom{[n]}{2}} |A_{i_1} \cap A_{i_2}|\\
&+\sum_{\set{i_1,i_2,i_3} \in \binom{[n]}{3}} |A_{i_1} \cap A_{i_2} \cap A_{i_3}|
-\ldots+(-1)^{n+1}|A_1 \cap \cdots \cap A_n|
\end{align*}
$$
Where: 
$$
\sum_{\set{i_1, \ldots, i_k} \in \binom{[n]}{k}}|A_{i_1} \cap \cdots \cap A_{i_k}| = (n-k)! \cdot \binom{n}{k} = \frac{n!}{k!}
$$





