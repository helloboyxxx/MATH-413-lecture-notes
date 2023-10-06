# Lower Bound of Ramsey Number


### <span style="color:#3c66b5">Theorem</span>

==Lower bound...????== $R(k) \geq 2^{k/2}$


For every $k \in \mathbb{N}$, we have $R(k)\ge 2^{k}$


Before we start the proof, let's look at 3 ingredients we need: 

- The probabilistic method
- The union bound 
- The binomial estimate

#### <span style="color:#599eff">The probabilistic method</span>

Let $\Omega$ be the set of all possible outcomes of an experiment. Suppose that each outcome is equally likely. Let $A \subseteq \Omega$ be an event.
$$
\text{If } \operatorname{Prob}(A) < 1 \text{, then } \operatorname{Prob}(A^c) > 0
$$
**Our setting:**

Let $n \in \mathbb{N}$ to be chosen later. 

Experiment: colro each edge of $K_n$ uniformly at random with red or blue. 

Set of all poss==ible outcome is:== 
$$
\Omega = \{\text{red, blue}\}^{{n} \choose {k}}
$$

#### <span style="color:#599eff">Union Bound</span>

Let $\Omega$ be the set of all possible outcome of an experiment. Suppose that each outcome is equally likely. Let $A_1, \ldots, A_t \subseteq \Omega$ be some events. Then: 
$$
\operatorname{Prob}(A_1 \cup A_2 \cup \cdots A_t) \leq \sum_{i=1}^{t}\operatorname{Prob}(A_i)
$$
<span style="color:#eb861c">Proof</span>

Consider the sets: 
$$
\begin{align*}
B_1 &= A_1\\
B_2 &= A_2 \setminus A_1\\
B_3 &= A_3 \setminus (A_1 \cup A_2)\\
&\vdots\\
B_t &= A_t \setminus (A_1 \cup \cdots \cup A_t)\\
\end{align*}
$$
Notice that: 

- $B_i \cap B_j = \varnothing, \forall i \neq j$
- $B_i \subseteq A_i, \forall i$
- $A_1 \cup \cdots \cup A_t = B_1 \cup \cdots \cup B_t$

<img src="https://github.com/helloboyxxx/images-for-notes/blob/master/uPic/image-20231004160227017.png?raw=true" alt="venn" style="zoom:25%;" />

These implies that: 
$$
\mathbb{P}(A_1 \cup \cdots \cup A_t) = \sum_{i=1}^{t}\mathbb{P}(B_i) \leq \sum_{i=1}^{t}\mathbb{P}(A_i)
$$


**Our setting:**

Label all the copies of $K_k$inside $K_n$. There are ${{n} \choose {k}}$ of them. 

Our events will be of the following form: 
$$
A_i = \{i^{th} \text{ clique is monochromatic}\}
$$



#### <span style="color:#599eff">A binomial estimate</span>

$$
\text{If } 1 \leq k \leq n, \text{ then } {{n} \choose {k}} \leq \left(\frac{ne}{k}\right)^k
$$

<span style="color:#eb861c">Proof</span>

We simply use that $1+x \leq e^x$ for all $x \in \mathbb{R}$. 

> To see why this "fact" holds, consider the tangent line of the function $f(x) = e^x$ at $x=0$.

Trial: Use the binomial theorem
$$
\left( 1 + \frac{k}{n} \right)^k = \sum_{i=0}^{n}\left(\frac{k}{n}\right)^i{{n} \choose {i}} \geq ...
$$








<span style="color:#eb861c">Proof</span> of $R(k)\geq 2^{k/2}$

==...==



---



# Unimodality of binomial coefficients

If we examine the binomial coefficients in a row of Pascal's triangle, we notice that the numbers increase for a while and then decrease. A sequence of numbers with this property is called **unimodal**. 

### <span style="color:#3c66b5">Theorem</span>

Let $n$ be a positive integer. THe sequence of binomial coefficients
$$
{{n} \choose {0}}, {{n} \choose {1}}, \ldots, {{n} \choose {n}}
$$
is a unimodal sequence. Mor precisely, 
$$
{{n} \choose {0}} < {{n} \choose {1}} < \ldots < {{n} \choose {\lfloor n/2\rfloor}}
$$
and 
$$
{{n} \choose {\lceil n/2 \rceil}} > \ldots {{n} \choose {n-1}} > {{n} \choose {n}}
$$


<span style="color:#eb861c">Proof</span>

$k \in \{0, \ldots, n\}$

Compare ${{n} \choose {k}}$ to ${{n} \choose {k-1}}$ by using division: 
$$
\frac{{{n} \choose {k}}}{{{n} \choose {k-1}}} = \frac{n-k+1}{k} < 1 \iff n-k+1 < k \iff \frac{n+1}{2} < k
$$
When $n$ is odd: $\frac{n+1}{2}$ gives us $\lceil \frac{n}{2} \rceil$

$\implies$ ${{n} \choose {k}} < {{n} \choose {k-1}} \iff k > {\lceil n / 2\rceil}$

and also ${{n} \choose {k}} > {{n} \choose {k-1}} \iff k < {\lceil n / 2\rceil}$

Note that: ${{n} \choose {k}} = {{} \choose {}}$





We want to use this theorem to prove Sperner's theorem. But we need some definition first.



<span style="color:#28a745">Definition</span> (Chain)

==...== Chain of proper subset...



<span style="color:#28a745">Definition</span> (antichain)

==...==

Example: $\{\{1,2\}, \{2,3\}, \{3,4\}\}$



> Question: Let $S$ be a set of $n$ elements. What is the maximum size of a antichain on $S$?

$S = \{1, 2, \ldots, n\}$

$\mathcal{C} = \{A \subset S : |A| = {\lfloor n/2\rfloor}\}$

$\mathcal{P} = \{(\mathcal{C}, A): A \in \mathcal{F}, A \in \mathcal{C} \text{ and  } \mathcal{C} \text{ is the maximal chain in }S\}$















