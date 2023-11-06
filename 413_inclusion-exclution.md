# Inclusion-Exclution Principle



<span style="color:#04c2b2">Problem</span> Count the number of integers between 1 and 600, inclusive, which are divisible by 2 or 3.

**Solution:** 

$A = \{n : 2 \mid n, n \in [600]\}$

$B = \{n : 3 \mid n, n \in [600]\}$

$|A \cup B| = |A| + |B| - |A \cap B| = 300 + 200 - 100$

<img src='https://raw.githubusercontent.com/helloboyxxx/images-for-notes/master/uPic/Sketch.png' alt='Sketch' style="zoom:50%;" />

### <span style="color:#3c66b5">General form of the Inclusion-Exclusion Principle</span>

Let $A_1,\ldots, A_n$ be a sequence of finite sets. Then,

$$
\begin{align*}
\left| \bigcup_{i=1}^n A_i\right|
&= \sum_{i \in [n]} |A_i|-\sum_{i,j \in \binom{[n]}{2}}|A_i \cap A_j|+\ldots\\
&+(-1)^{n+1}\sum_{i \in \binom{[n]}{n}} |A_1 \cap A_2 \cap \cdots A_n|
\end{align*}
$$

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
Define $k = \# \{i : v \in A_i\} \geq 1$. WLOG, suppose $v \in A_1, \ldots, A_k$ and $v \not \in A_{k+1}, \ldots A_n$.

Pick an example $\sum_{i,j \in \binom{[n]}{2}}1_{v \in A_i \cap A_j}$, whenever $i > k$ or $j > k$, the indicator function $1_{v\in A_i \cap A_j}$ gives us 0. Then the term: $\sum_{i,j \in \binom{[n]}{2}}1_{v \in A_i \cap A_j}$ counts the number of unordered pairs $(i, j)$ such that $i, j \leq k$, which is $\binom{k}{2}$. This works for other terms as well. Also notice that the left side of this equation must be 1.Now the equation becomes: 
$$
\begin{align*}
1 &= \binom{k}{1} - \binom{k}{2} + \binom{k}{3} - \ldots + (-1)^{k+1}\binom{k}{k}\\
\binom{k}{0} + \binom{k}{2} + \binom{k}{4} \ldots &= \binom{k}{1} + \binom{k}{3} + \binom{k}{5} + \ldots
\end{align*}
$$
The second line must be true by a binomial identity we have seen before. This means that the inclusion-exclusion principle can be derived from this identity, thus the principle is true. $\blacksquare$

> I am not 100% sure this proof is correct. Please read book / other prooves if possible.

**There is another form:**

Let $A_1, \ldots A_n$ be a sequence of finite subsets of a finite set then:
$$
|\bar A_1 \cap \bar A_2 \cap \cdots \cap \bar A_n| = |S| - | A_1 \cup  A_2 \cup \cdots \cup A_n|
$$

Also:

$$
\left|\overline{A_1 \cup A_2 \cup \cdots \cup A_n}\right|=|S|-\left|A_1 \cup A_2 \cup \cdots \cup A_n\right|
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

Or by DeMorgan's rules.



<span style="color:#04c2b2">Exercise</span>

How many permutations of the letters M, A, T, H, I, S, F, U, N are there such that none of the words MATH, IS, and FUN occur as consecutive letters?

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
e^x=\sum_{i=0}^{\infty} \frac{x^i}{i !} && \text{by Taylor's Expansion} \\
D_n \sim \frac{n !}{e}\\
\lim _{n \rightarrow \infty} \frac{D_n}{n !}=\frac{1}{e}
\end{aligned}
$$

When $n \to \infty$, the probability of a dearangement is $\frac{1}{e}$.

<span style="color:#eb861c">Proof</span>

$\mathcal{P} = $ permutations of $[n] = n!$

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





---

<span style="color:#04c2b2">Another forbidden position problem</span>

Suppose a class of eight boys takes a walk every day. The students walk in a line of eight so that every boy except the first is preceded by another. In order that a child not see the same person in front of him, on the second day the students decide to switch positions so that no boy is preceded by the same boy who preceded him on the first day. In how many ways can they switch positions?




### <span style="color:#3c66b5">Theorem</span>

Let $Q_n$ denote the number of permutations of $\set{1, 2, \ldots, n}$ in which none of the patterns $12, 23, \ldots, (n-1)n$ occurs. Then, 
$$
Q_n = n! + \sum_{j=1}^{n-1}(-1)^j \binom{n-1}{j}(n-j)!
$$
<span style="color:#eb861c">Proof</span>

We want to find the bad sets: For $i \in \set{1, \ldots, n-1}$, define $A_i = $ permutations of $[n]$ so that the pattern $i,i+1$ shows up. Our goal is to use the inclusion-exclusion principle to calculate $n! - |\bigcup_{i=1}^{n-1}A_i|$.

>Question: What is $|A_i|$? Ans: $(n-1)!$ if we group $i, i+1$ together, then there are $n-1$ objects.

> Questions: What is $|A_i \cap A_j|$? Ans: there are two situations: (1) If they intersect, such as $123$, then we have one object of size three. This is $(n-2)!$. If they don't, we should have two objects of size two, so also $(n-2)!$

Then, let $\set{i_1, \ldots, i_k} \in \binom{[n-1]}{k}$, then we want to show: $|A_{i_1} \cap \cdots \cap A_{i_k}| = (n-k)!$

Suppose that $\set{i_a, i_a+1} \cap \set{i_b, i_b+1} = \varnothing, \forall a \neq b$. Then there are $n-k$ objects. 

Suppose some block has more than two objects, we lose the elements that intersets, but the same amount of elements are set free to be outside the block. (Consider the case (1234) and (5678) becomes (123456)).

Now, the expression: 
$$
\sum_{\set{i_1, \ldots, i_k} \in \binom{[n-1]}{k}}
|A_{i_1} \cap \cdots \cap A_{i_k}| = (n-k)! \cdot \binom{n-1}{k}
$$
Then apply the inclusion-exclution:
$$
\left|\bigcup_{i=1}^{n-1}A_i\right| = \sum_{j=1}^{n-1}(-1)^j \binom{n-1}{j}(n-j)!
$$

---

Another application: 

### <span style="color:#3c66b5">The Euler Function</span>

For $n \in \mathbb{N}$, define $\varphi(n)$ to be the number of positive integers not exceeding $n$ that are relatively prime to $n$. We have: 
$$
\varphi(n) = n\prod_{p \mid n}\left(1 - \frac{1}{p}\right)
$$
Note that the $p$ are the primes that divides $n$. 

Example: $\varphi(6) = |\set{1, 5}| = 2$

<span style="color:#eb861c">Proof</span>

Let $n = p_1^{\alpha_1} p_2^{\alpha_2} \cdots p_k^{\alpha_k}$ where $p_i$ is prime and $\alpha_i \geq 1$

$A_i = \set{m \in [n] : p_i \mid m}$

$\varphi(n) = n - \left|\bigcup_{i=1}^{k} A_i \right|$

==...==



By inclusion-exclusion: 
$$
\varphi(n) = n -
$$

