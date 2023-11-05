<span style="color:#04c2b2">Example 1</span>

Find the general solution of the recurrence relation: 
$$
h_n = 4h_{n-1} + 4h_{n-2}
$$
where $h_0 = 1, h_1 = 3$. Show that $h_c = c2^n$ is not a general solution of the given recurrence relation.

**Solution**

We first try: $h_n = q^n$.
$$
\begin{align*}
q^n &= 4q^{n-1} + 4q^{n-2}\\
&q^2 - 4q + 4 = 0\\
&(q-2)^2 = 0 \implies q = 2
\end{align*}
$$
Putting $q=2$ back to recurrence, we guess $h_n = 2^n$. Also, multiplying a constant $c$ everywhere gives us that it is possible to have $h_n = c \cdot 2^n$. But this gives us a contradiction it we try to satisfy $h_0 = 1, h_1 = 3$. Thus this trial fails.



Then, try: $h_n = n \cdot 2^n$. Goal: show that $h_n$ satisfies the recurrence relation.

In this case, if 
$$
\begin{align*}
n \cdot 2^n \quad ?&==? \quad  4(n-1)2^{n-1} - 4 (n-2)2^{n-2}\\
&=2^{n-2}(...)
\end{align*}
$$


Observe that $h_n = c_1\cdot 2^n + c_2 \cdot n \cdot 2^n$ is also a solution of the recurrence relationi $\forall c_1, c_2 \in \mathbb{R}$. 

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

==...==

hand written notes















