<span style="color:#28a745">Definition</span> Linear recurrence relation

A linera recurrence relation is an equation that defines the $n^{th}$ term in a sequence in terms of the $k^{th}$ previous terms in the sequence, for some $k$. That is, a linear recurrence relations is of the form:
$$
h_n = c_1h_{n-1} + c_2h_{n-2} + \ldots + c_kh_{n-k}
$$


### <span style="color:#3c66b5">Arithmetic progressions</span>

$(a_i)_{i=0}^{\infty}$ is an arithmetic progression if there exists $q$ so that: 
$$
a_{n+1} = a_n + q
$$
for all $n \geq 1$.

**Problem 1:** find the general term of an arithmetic progression. 

> We want to formally go through the solution so that it applies to other problems. 

$$
\begin{align*}
a_0 &= a_0\\
a_1 &= a_0 + q\\
a_2 &= a_1 + q = a_0 + 2q\\
a_3 &= a_2 + q = a_0 + 3q\\
\end{align*}
$$

Take a guess and describe it: 

<span style="color:#599eff">Lemma</span> $a_i = a_0 + iq, \forall i \geq 0$.

<span style="color:#eb861c">Proof</span> by induction: 

Bases of induction: $a_0 = a_0 + 0 \cdot q$. Induction hypothesis: assume that $a_i = a_o + iq$ for some $i$. Let's show that $a_{i+1} = a_0 + (i+1)q$: 
$$
a_{i+1} = a_i + q = a_0 + qi + q = a_0 + (i+1)q
$$


---

<span style="color:#599eff">Lemma</span>
$$
\sum_{i=0}^{n}a_i = \frac{(a_0 + a_n) \cdot (n+1)}{2}
$$
<span style="color:#eb861c">Proof</span>
$$
\begin{align*}
s &= a_0 + a_1 + \ldots + a_n\\
s &= a_n + a_{n-1} + \ldots + a_1\\
\end{align*}
$$
Note that:
$$
\begin{align*}
a_i + a_{n-i} &= (a_0 + iq) + (a_0 + (n-i)q) \\
&= a_0 + a_0 + nq = a_0 + a_n
\end{align*}
$$
$\Rightarrow$
$$
\begin{align*}
2s &= (a_0 + a_n) + (a_1 + a_{n-1}) + \ldots + (a_n + a_1)\\
2s &= (n+1)(a_0 + a_n)
\end{align*}
$$
$\blacksquare$

---

### <span style="color:#3c66b5">Geometric progression</span>

$(a_i)_{i=0}^{\infty}$ is an arithmetic progression if there exists $q$ so that: 
$$
a_{n+1} = a_n \cdot q
$$
for all $n \geq 1$.

<span style="color:#eb861c">Proof</span> similar to the arithmetic progression.

---

<span style="color:#599eff">Lemma</span>
$$
\sum_{i=0}^{n}a_i = \frac{a_0(q^{n+1}-1)}{q-1}
$$
<span style="color:#eb861c">Proof</span>


$$
\begin{align*}
S &= a_0 + a_1 + \ldots + a_n\\
qS &= a_0q + a_1q + \ldots + a_nq\\
&= a_1 + a_2 + \ldots + a_nq\\
&= S - a_0 + a_nq\\
\Rightarrow\\
&qS - S = S\cdot(q-1) = a_nq - a_0 = q^{n+1}a_0 - a_0
\end{align*}
$$



### <span style="color:#3c66b5">Fact</span>

Let $k$ be a constant and let $(h_n)_{n=0}^{\infty}$ be a sequence which satisfies the following linear recurrence relation: $$h_n = c_1h_{n-1}+c_2h_{n-2}+\ldots+c_kh_{n-k}.$$

Let $(h'_n)_n$ be a sequence satisfying the same recurrence relation above and suppose that $h_i = h_i'$ for all $i \in \{1,\ldots,k\}$. Then,
$$h_i = h'_i \text{ for all } i \ge 1.$$



<span style="color:#28a745">Definition</span> Fibonacci Sequence

The sequence of numbers $f_0,f_1,f_2,f_3,\ldots$ satisfying the recurrence relation and initial conditions 
$$
\begin{cases}f_n = f_{n-1} + f_{n-2} \phantom{iii} (n \ge 2) \\ f_0 = 0, f_1 = 1 \end{cases}
$$

### <span style="color:#3c66b5">Theorem</span>

The Fibonacci numbers satisfy the formula: 
$$
f_n = \frac{1}{\sqrt{5}} \left( \frac{1+\sqrt{5}}{2} \right)^n
- \frac{1}{\sqrt{5}} \left( \frac{1-\sqrt{5}}{2} \right)^n
$$

> We want to talk about how to come up with this complicated expression from nowhere 😊

**First step:** guessing a solution. 

Let $(a_i)_{i=0}^{\infty}$ be a sequence given by $a_i = q^i$. Suppose that $(a_i)_{i=0}^{\infty}$ satisfies the recurrence relation: $a_n = a_{n-1} + a_{n-2}$.

> Question: What should be $q$?

Answer: we should have 
$$
\begin{align*}
q^n = q^{n-1} \cdot q^{n-2}\\
q^2 = q+1\\
q^2 - q - 1 = 0\\
q = \frac{1\pm \sqrt 5}{2}
\end{align*}
$$
<span style="color:#599eff">Lemma</span> Let $(a_i)_{i=0}^{\infty}$ and $(b_i)_{i=0}^{\infty}$ be sequences given by: 
$$
\begin{align*}
(a_i)_{i=0}^{\infty} = \left( \frac{1 + \sqrt 5}{2} \right)^i\\
(b_i)_{i=0}^{\infty} = \left( \frac{1 - \sqrt 5}{2} \right)^i\\
\end{align*}
$$
Then $(a_i)_i$ and $(b_i)_i$ satisfies:
$$
\begin{cases}
a_n = a_{n-1} + a_{n-2}\\
b_n = b_{n-1} + b_{n-2}
\end{cases}
$$


<span style="color:#599eff">Lemma</span> Let $c_1, c_2 \in \mathbb{R}$. $(a_i)_i, (b_i)_i$ as before. 

Then the sequence: $d_i = c_1a_i + c_2b_i$ satisfies: $d_n = d_{n-1} + d_{n-2}$

<span style="color:#eb861c">Proof</span>
$$
\begin{align*}
d_{n-1} &= c_1a_{n-1} + c_2b_{n-2}\\
d_{n-2} &= c_1a_{n-2} + c_2b_{n-2}\\
d_{n-1} + d_{n-2} &= c_1a_n + c_2b_n = d_n
\end{align*}
$$
$\blacksquare$

Now the goal is to find some $c_1, c_2$ such that $d_0 = 0, d_1 = 1$. (JUST GUESSSSSSS!!!!)
$$
\begin{align*}
&\begin{cases}
d_0 = c_1 a_0 + c_2 b_0\\
d_1 = c_1 a_1 + c_2 b_1\\
\end{cases}
&\Rightarrow
&\begin{cases}
d_0 &= c_1 \cdot 1 + c_2 \cdot 1 = 0\\
d_1 &= c_1 \cdot \left( \frac{1 + \sqrt 5}{2} \right)^1 
+ c_2 \cdot \left( \frac{1 + \sqrt 5}{2} \right)^1 = 1
\end{cases}
\end{align*}
$$

Solving this linear system gives us the result: 
$$
\begin{cases}
c_1 = \frac{1}{\sqrt 5}\\
c_2 = -\frac{1}{\sqrt 5}
\end{cases}
$$


---

### Tower of Hanoi

> OK, we all know what this is... Let's see what are the differences in the context of combinatorics. 

### <span style="color:#3c66b5">Theorem</span>

The minimal number of moves requried to solve a Tower of Hanoi puzzle is $2^n - 1$, where $n$ is the number of disks.

<span style="color:#eb861c">Proof</span>

By induction.

<img src="https://raw.githubusercontent.com/helloboyxxx/images-for-notes/master/uPic/image-20231023112446979.png" alt="image-20231023112446979" style="zoom:50%;" />



