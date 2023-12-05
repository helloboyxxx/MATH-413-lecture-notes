<span style="color:#04c2b2">Example 1</span>

Find the general solution of the recurrence relation: 
$$
h_n = 4h_{n-1} - 4h_{n-2}
$$
where $h_0 = 1, h_1 = 3$. Show that $h_c = c2^n$ is not a general solution of the given recurrence relation.

**Solution**

We first try: $h_n = q^n$.
$$
\begin{align*}
q^n &= 4q^{n-1} - 4q^{n-2}\\
&q^2 - 4q + 4 = 0\\
&(q-2)^2 = 0 \implies q = 2
\end{align*}
$$
Putting $q=2$ back to recurrence, we guess $h_n = 2^n$. Also, multiplying a constant $c$ everywhere gives us that it is possible to have $h_n = c \cdot 2^n$. But this gives us a contradiction it we try to satisfy $h_0 = 1, h_1 = 3$. Thus this trial fails.



Then, try: $h_n = n \cdot 2^n$. Goal: show that $h_n$ satisfies the recurrence relation.

In this case, we want to know if the following equivalence holds:
$$
n \cdot 2^n \overset{?}{=} 4(n-1)2^{n-1} - 4 (n-2)2^{n-2}
$$

We can try from the right side: 
$$
\begin{align*}
&4(n-1)2^{n-1} - 4 (n-2)2^{n-2}\\
&= 2^{n-2}\cdot \left( 8(n-1) - 4(n-2) \right)\\
&= 2^{n-2}(8n-8-4n+8)\\
&= 2^{n-2}(4n) = n \cdot 2n = \text{left side}
\end{align*}
$$
Yes, our guess is valid !

Observe that $h_n = c_1\cdot 2^n + c_2 \cdot n \cdot 2^n$ is also a solution of the recurrence relation $\forall c_1, c_2 \in \mathbb{R}$. 

> This is taking a linear combination.

We need: 
$$
\begin{cases}
h_0 = 1 = c_1\\
h_1 = 3 = c_1 \cdot 2 + c_2 \cdot 1 \cdot 2
\end{cases}
\implies c_2 = \frac{1}{2}
$$
Conclusion: 

$h_n = 2^n + \frac{1}{2}n2^n$ is a solution of this recurrence relation. $\blacksquare$



> We have a more general theorem for this example

### <span style="color:#3c66b5">Theorem</span>

Let $P$ be the characteristic polynomial of a homogeneous linear recurrence. If $r$ is a root of $P(x)=0$ with multiplicity $k$, then 

$$
r^n, nr^n, n^2r^n,\ldots,n^{k-1}r^n
$$

are all solutions to the recurrence.

<span style="color:#eb861c">Proof</span>

We first need some tools:

**First tool: decomposition**
$$
P(x)=\left(x-q_1\right)^{i_1} \cdot\left(x-q_2\right)^{i_2} \cdots\left(x-q_d\right)^{i_d}
$$
where $i_1+\cdots+i_d=k$, $i$'s are multiplicities. This decomposition is always possible. 

**Second Tool: Claim**
Let $Q$ be a polynomial. Suppose that $(x-q)^i \mid Q(x)$, for some $i \geqslant 1$.
Then, $(x-q)^{i-1} \mid Q^{\prime}(x)$
**proof:** $Q(x)=(x-q)^i \cdot P(x)$ for some polynomial $P(x)$. By product rule in Calculus, we have: 
$$
\begin{aligned}
Q^{\prime}(x) & =i(x-q)^{i-1} \cdot P(x)+(x-q)^i P^{\prime}(x) \\
& =(x-q)^{i-1} \cdot \underbrace{\left( i P(x)+(x-q) P^{\prime}(x)\right)}_{\text {also a poly }} \\
& \Rightarrow(x-q)^{i-1} \mid Q^{\prime}(x)
\end{aligned}
$$
Moreover, by applying these rules multiple times, we also have: 
$$
(x-q)^{i-j} \mid Q^{(j)}(x) \quad \forall j \leqslant i-1
$$


<span style="color:#3c66b5">Corollary</span> Let $Q$ be a polynomial. Then, if $r$ is a root of $Q$ with multiplicity $i$, then $Q^{(j)}(r)=0 \quad \forall j \leq i-1$ 

**proof:** by claim, we have:
$$
Q^{(j)}(x)=(x-r)^{i-j} \cdot P_j(x)
$$
for some polynomial $P_j$. Plug $x=r$, this gives us 0.

⚠️NOW, back to the proof of the theorem.

Consider
$$
h_n=a_1 h_{n-1}+a_2 h_{n-2}+\cdots+a_k h_{n-k}
$$

Note that $h_n=q^n$ is a solution of the relation if
$$
\begin{aligned}
& q^n=a_1 q^{n-1}+\cdots+a_k q^{n-k} \\
\Leftrightarrow & \underbrace{q^k-a_1 q^{k-1}-\cdots-a_{k-1} q-a_k=0}_{\text {by def of characteristic polynomial } P(q)} \\
\Rightarrow & P(q)=0
\end{aligned}
$$
Then the goal is to find the root for the polynomial
$$
Q(x)=x^n-a_1 x^{n-1}-a_2 x^{n-2}-\cdots-a_k x^{n-k}
$$
????? I need some help...









