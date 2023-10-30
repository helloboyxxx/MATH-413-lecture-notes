# Generating Functions

Generating functions can be regarded as algebraic objects whose formal manipulation allows us to count the number of possibilities for a problem by means of algebra. 

On another level, generating functions are Taylor series (power series expansions) of infinitely differentiable functions. If we can find the function and its Taylor series, then the coefficients of the Taylor series give the solution to the problem.

<span style="color:#28a745">Definition</span>

Let $h_0, h_1, h_2, h_3, \ldots$ be an infinite sequence of numbers. Its generating function is defined to be the infinite series: 
$$
g(x) = h_0 + h_1x + h_2x^2 + \cdots + h_nx^n + \cdots
$$


<span style="color:#04c2b2">Example 1</span>

The generating function of the infinite sequence $1, 1, 1, \ldots$ is: 
$$
g(x) = 1 + x + x^2 + x^3 + \cdots
$$
for $|x| < 1$. This generating function $g(x)$ is the sum of a geometric series with value: 
$$
g(x) = \frac{1}{1-x}
$$
**Solution**

$|x| < 1$,
$$
\begin{align*}
(1-x)(1 + x + x^2 + x^3 + \cdots + x^n) &= 1 - x^{n+1}\\
\Rightarrow\\
\lim_{n \to \infty}(1-x)(1 + x + x^2 + x^3 + \cdots + x^n)
&= \lim_{n \to \infty}(1 - x^{n+1}) = 1\\
\Rightarrow\\
\sum_{j=0}^{\infty}x^j = \frac{1}{x-1}
\end{align*}
$$
<span style="color:#04c2b2">Example 2</span>

Let $m$ be a positive integer. The generating function for the binomial coefficients: 
$$
\binom{m}{0}, \binom{m}{1}, \ldots, \binom{m}{m}
$$
**Solution**
$$
g(x) = \binom{m}{0}x + \binom{m}{1}x^2+ \ldots+ \binom{m}{m}x^m = (1+x)^m
$$
By the binomial theorem

<span style="color:#04c2b2">Example 3</span>


Let $k$ be an integer, and let the sequence $h_0, h_1, h_2, \ldots$ be defined by letting $h_n$ equal the number of nonnegative integeral solutions of  $x_1+x_2+\cdots+x_k = n.$

The generating function of this sequence is equal to 
$$g(x) = \dfrac{1}{(1-x)^k}.$$

**Solution**

==...==



<span style="color:#04c2b2">Example 4</span>

For what sequence is $(1+x+x^2+x^3+x^4+x^5)(1+x+x^2)(1+x+x^2+x^3+x^4)$ the generating function?

**Solution**

==...==



---

<span style="color:#04c2b2">Example 5</span>

Determine the generating functino for the number of $n$-combinations of apples, bananas, oranges, and pears, where in each $n$-combination, the number of apples is even, the number of bananas is odd, the number of oranges is between $0$ and $4$, and there is at least one pear.

**Solution**

Intuition is to come up to a multiplication of generating functions, where each generating function corresponds to one fruit.

Consider: 

$(1 + x^2 + x^4 + \ldots) \to $ Apples

$(x + x^3 + x^5 + \ldots) \to $ Bananas

$(1 + x + x^2 + x^3 + x^4) \to $ Oranges

$(x + x^2 + x^3 + \ldots) \to $ Pears

Note that the coeff of $x^n$ is the number of $n$-combinations of fruits.

If we expand the multiplication of these four terms, we get: 
$$
g(x) = \sum_{e_1,\ldots, e_4}x^{e_1} \cdot x^{e_2} \cdot x^{e_3} \cdot x^{e_4} = \sum_{n \geq 0}h^nx^n
$$
The last expression above is what we want / is what we are asked for. We may first notice that finding the correct coefficients is the goal, then we try to construct the generating functions that satisfies the properties. 

Apples $ = \frac{1}{1-x^2}$ by replacing $x$ by $x^2$.

Bananas $=\frac{x}{1-x^2}$ by multiplying apple by $x$.

Oranges $= \frac{1-x^5}{1-x}$ since $(1-x^5) = (1-x)(1 + x + x^3 + x^4)$

Pears $= (\frac{1}{1-x}-1) = \frac{x}{1-x}$

Then we take the multiplication. $\blacksquare$



<span style="color:#04c2b2">Example 6</span>

Find the number $h_n$ of bags of fruit that can be made out of apples, bananas, oranges, and pears, where, in each bag, the number of apples is even, the number of bananas is a multiple of five, the number of oranges is at most 4, and the number of pears is 0 or 1.

**Solution**

Similar to Example 5: 
$$
g(x) = (1 + x^2 + x^4 + \ldots) (1 + x^5 + x^{10} + \ldots)(1 + x + x^2 + x^3 + x^4) (1+x)
$$
Simplify it to get: 
$$
g(x) = \frac{1}{(1-x)^2}
$$
We can actually calculate $h_n$ from this by using Taylor expansion:

⚠️ Calc review: 
$$
\begin{aligned}
& f \in \mathcal{C}^{\infty}, 0 \in \operatorname{Domain}(f) \\
& f(x)=f(0)+\frac{f^{\prime}(0)}{1 !} \cdot x+\frac{f^{\prime \prime}(0)}{2 !} \cdot x^2+\ldots \\
& f(x)=\frac{1}{(1-x)^2} \\
& f^{\prime}(x)=\frac{2}{(1-x)^3} \\
& f^{\prime \prime}(x)=\frac{2 \cdot 3}{(1-x)^4} \\
& f^{(n)}(x)=\frac{2 \cdot 3 \cdots(n+1)}{(1-x)^{n+2}}\\
& f^{(n+1)}(x)=\frac{2 \cdot 3 \cdot(n+1)(n+2)}{(1-x)^{n+3}} \\
&
\end{aligned}
$$
For $n \in \mathbb{N}$
$$
\begin{aligned}
& f^{(n)}(0)=(n+1) ! \\
& f(x)=1+\frac{2 !}{1 !} x+\frac{3 !}{2 !} x^2+\cdots \\
& =1+\sum_{n \geqslant 1} \frac{f^{(n)}(0) x^n}{n !}=1+\sum_{n \geqslant 1}^1(n+1) x^n
\end{aligned}
$$
Then our answer is simply $h_n = n+1$. $\blacksquare$

**OR**

We can solve this in another way:
$$
\begin{align*}
\left(\frac{1}{1-x}\right)^\prime &= (1 + x + x^2 + \ldots)^\prime\\
\frac{1}{(1-x)^2} &= 0 + 1 + 2x + 3x^2 + \ldots
\end{align*}
$$
Then we find out that $h_n = n+1$. $\blacksquare$

---

### Exponential generating functions

==...==

FACT: In the Taylor series: 

==...==



<span style="color:#04c2b2">Example</span>

Let $n$ be a positive integer. Determine the exponential generating function for the sequence of numbers: 
$$
P(n, 0), P(n, 1), P(n, 2), \ldots, P(n, n)
$$
where $P(n, k)$ denotes the number of $k$-permutations of an $n$ element set.

**Solution**
$$
\sum_{k=0}^{n} = \frac{P(n,k)x^k}{k!} = \sum_{k=0}^{n} \frac{n!}{k!(n-k)!} \cdot x! = \sum_{k=0}^{n}\binom{n}{k}x^k = (1+x)^n
$$


<span style="color:#04c2b2">Example</span>

Let $a$ be any real number. Determine the exponential generating function for the sequence $a_0, a_1, a_2, \ldots$

**Solution**
$$
\sum_{k=0}^{n} = \frac{a^kx^k}{k!} = e^{ax}
$$



<span style="color:#599eff">Lemma</span>

Let $S$ be the multiset $\{n_1 \cdot a_1, n_2 \cdot a_2, \ldots ,n_k \cdot a_k\}$, where $n_1, n_2, \ldots ,n_k$ are nonnegative integers. 

Let $h_n$ be the number of $n$-permutations of $S$. Then, the exponential generating function $g^{(e)}$ for the sequence $(h_n)_{n \ge 0}$ is given by
$$
g^{(e)}(x) = f_{n_1}(x)f_{n_2}(x)\cdots f_{n_k}(x).
$$

where, for $i = 1,2, \ldots ,k$,

$$
f_{n_i}(x) = 1 + x + \dfrac{x^2}{2!}+ \cdots + \dfrac{x^{n_i}}{n_i!}.
$$


<span style="color:#eb861c">Proof</span>

An $n$-permutation of $S$ is a string of the form: 

$T = t_1 \cdots t_n$, where $t_i \in S,\forall i \in [n]$ and the number of $a_i$'s in $T \leq n_i, \forall i \in [k]$.

Denote: $P_n = $ number of $n$-permutation of $S$.  To count $P_n$:

- Choose the multiplicities of each $a_i$ in our string: $j_i$ $a_1$\'s, $j_2$ $a_2$\'s, ..., $j_k$ $a_k$\'s
- Restriction: $j_1 + \ldots + j_k = n, j_i \in [n_i], \forall i \in [k]$

The number of $n$-permutations with $j_i$ $a_1$\'s, $j_2$ $a_2$\'s, ..., $j_k$ $a_k$\'s is:
$$
\frac{n!}{j_1! \cdots j_k!}
$$

$$
\begin{align*}
\implies P_n = \sum_{(j_1, \ldots,j_k): \text{restriction}}\frac{n!}{j_1! \cdots j_k!}
\end{align*}
$$
Consider the function: 
$$
g(x) = \left( \sum_{j_1 = 0}^{n_1} \frac{x^{j_1}}{j_1} \right) \cdots 
\left( \sum_{j_k = 0}^{n_k} \frac{x^{j_k}}{j_k} \right)
$$
Goal: to show that the coef of $x_n$ in $g$ is equal to $P_n / n!$
$$
\begin{align*}
g(x) &= \sum_{0\leq j_i \leq n_i}\frac{x^{j_1}}{j_1!} \cdots\frac{x^{j_k}}{j_k!}\\
&=\sum_{n=0}^{n_1+\ldots + n_k} \left( \sum_{(j_1,\ldots,j_k):\text{restriction}} \frac{1}{j_1! \cdots j_k!}\right)\cdot x^n
\end{align*}
$$
This whole thing gives us:
$$
g(x) = \sum_{n=0}^{n_1 + \ldots + n_k} \frac{P_n}{n!}x^n
$$


<span style="color:#04c2b2">Example</span>

Let $h_n$ denote ==...==

**Solution**
$$
\begin{align*}
g^{(e)}(x) &= \left( 1 + \frac{x^2}{2!} + \frac{x^4}{4!} + \ldots \right) && \text{choice of num of 1's}\\
&\cdot \left( \frac{x^3}{3!} + \frac{x^4}{4!} + \frac{x^5}{5!} + \ldots \right) && \text{choice of num of 2's}\\
&\cdot \left( 1 + x + \frac{x^2}{2!} + \frac{x^3}{3!} + \ldots \right)&& \text{choice of num of 3's}
\end{align*}
$$
The expansion becomes:
$$
g^{(e)}(x) = \sum \frac{x^{a_1}x^{a_2}x^{a_3}}{a_1!a_2!a_3!}
$$


Coefficient of $x^n$ in $g^{(e)}(x)=$
$$
\sum_{}^{} \frac{1}{a_1!a_2!a_3!} = \frac{h_n}{n!}
$$


How can we simplify this:
$$
\left( 1 + \frac{x^2}{2!} + \frac{x^4}{4!} + \ldots \right) = 
\frac{e^x + e^{-x}}{2}
$$

and

$$
\left( \frac{x^3}{3!} + \frac{x^4}{4!} + \frac{x^5}{5!} + \ldots \right) = e^x - 1 - x - \frac{x^2}{2}
$$



<span style="color:#04c2b2">Example</span>

Determine the number of ways to color the squares of a 1-by-$n$ chessboard, using the colors, red, white, and blue. Also, an even number of squares are to be colored red.

**Solution**
$$
g^{(e)}(x) = e^x \cdot e^x \cdot \left( \frac{e^x + x^{-x}}{2} \right) = \frac{x^{3x}}{2}
$$
Using a same reasoning.





