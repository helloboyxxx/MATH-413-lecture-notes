# Finite Probability

Consider the senario: you have an experiment which, when performed, yields one of a finite number of possible outcomes. 

Let $S$ be the set of all possible outcomes of our experiment. This set is usually called **sample space**.

Suppose that each outcome is **equally** likely. That is, no outcome is more likely to occur than any other. 

Then the probability that a given element $a \in S$ is the outcome of our experiment is: 
$$
\text{Prob}(a) = \frac{1}{|S|}
$$


Consider rolling a 6-side fair dice. What is the probability that the upper face is equal to 6?



An **event** is just a subset $E$ of a sample space $S$. It is usually given descriptively and not by actually listing all the outcomes in $E$. 

The probability of an event $E$ in an experiment with a sample space $S$ is defined to be the proportion of outcomes in $S$ that ???
$$
\text{Prob}(E) = \frac{|E|}{|S|}
$$


The probability of an event $E$ satisfies: $0 \leq \text{Prob}(E) \leq 1$, where $\text{Prob}(E) = 0$ iff $E$ is the empty event $\emptyset$, and $\text{Prob}(E) = 1$ iff $E = S$.

<span style="color:#04c2b2">Exercise</span>

Consider the experiment of tossing a coin four times in a row. Let $E$ be the event that at least two coints come up HEAD. What is the probability that $E$ occurs? 

- $|S| = 2^4$
- $E=$ set of strings with $\geq2$ heads. This is just ${{4} \choose {2}} + {{4} \choose {3}} + {{4} \choose {4}}$















