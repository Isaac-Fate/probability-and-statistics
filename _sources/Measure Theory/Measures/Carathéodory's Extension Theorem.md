# Carathéodory's Extension Theorem

````{prf:definition}
:label: def:1

An **outer measure** on $\Omega$ is a set function $\mu^\ast : \Pow(\Omega) \to[0, \infty]$ such that it
1.  assumes zero at empty set, i.e., $\mu^\ast(\emptyset) = 0 $, and

2.  is $\sigma$-subadditive, i.e., $ E \subset\bigcup_{i=1}^\infty{E_i}, \;\mu^\ast(E) \leq\sum_{i=1}^\infty{\mu^\ast(E_i)}$


````

````{prf:definition}

Suppose that $\mu^\ast$ is an outer measure on $\Omega$. The collection of **measurable sets** with respect to $\mu^\ast$ is defined by 

```{math}
\begin{align*}
\M = \set{A \subset \Omega}{\forall E \subset \Omega, \; \mu^\ast(E) = \mu^\ast(E \cap A) + \mu^\ast(E \cap A^\complement)}\end{align*}
```

Sometimes, we also say the sets in $\M$ are $\mu^\ast$-measurable.

````

````{prf:theorem}
:label: thm:4

Let $\mu^\ast$ be an outer measure on $\Omega$ and $\M$ the collection of $\mu^\ast$-measurable sets. We claim that 
1. $\M$ is a $\sigma$-algebra, and

2. $\restr{\mu^\ast}{\M}$ is $\sigma$-additive.



````


Consider the equality 

```{math}
\begin{align*}
\mu^\ast(E) = \mu^\ast(E \cap A) + \mu^\ast(E \cap A^\complement)
\end{align*}
```

in the definition of $\M$. Note that it always holds that 

```{math}
\begin{align*}
\mu^\ast(E) \leq\mu^\ast(E \cap A) + \mu^\ast(E \cap A^\complement)
\end{align*}
```

because $ E \subset(E\cap A) \cup(E \cap A^\complement) $ and $\mu^\ast$ is an outer measure and hence $\sigma$-subadditive. Therefore, in the following proofs, we only need to show  

```{math}
\begin{align*}
\mu^\ast(E) \geq\mu^\ast(E \cap A) + \mu^\ast(E \cap A^\complement)
\end{align*}
```

in order to prove the equality.



Before proving that $\M$ is a $\sigma$-algebra, we first show that it is an algebra.

````{prf:proof}

We shall check each condition in the definition of an algebra.



(Containment of the Empty Set) Note that 

```{math}
\begin{align*}
\mu^\ast(E \cap\Omega) + \mu^\ast(E \cap\Omega^\complement) = \mu^\ast(E) + 0 = \mu^\ast(E)
\end{align*}
```

Therefore, clearly $\Omega\in\M$.



(Closure under Complements) Suppose $ A \in\M$, then $\forall E \subset\Omega$, we have

```{math}
\begin{align*}
\mu^\ast(E) = \mu^\ast(E \cap A) + \mu^\ast(E \cap A^\complement) = \mu^\ast(E \cap(A^\complement)^\complement) + \mu^\ast(E \cap A^\complement)
\end{align*}
```

The last equality above implies that $ A^\complement\in\M$.



(Closure under Finite Intersections) Suppose $ A_1, A_2 \in\M$. Let $ E \subset\Omega$ be arbitrary, then 

```{math}
:label: eq:18
\begin{alignat}
3\mu^\ast(E)
&=& \;& \mu^\ast(E \cap A_1) + \mu^\ast(E \cap{A_1}^\complement) &\quad&\text{since $ A_1 \in \M $}\nonumber\\&=& \;& \mu^\ast(E \cap A_1 \cap A_2) + \mu^\ast(E \cap A_1 \cap{A_2}^\complement) + \mu^\ast(E \cap{A_1}^\complement) &\quad&\text{since $ A_2 \in \M $}\end{alignat}
```

On the other hand, consider $\mu^\ast(E \cap{(A_1 \cap A_2)}^\complement) $. We have 

```{math}
:label: eq:19
\begin{alignat}
3\mu^\ast(E \cap{(A_1 \cap A_2)}^\complement)
&=& \;& \mu^\ast((E \cap{A_1}^\complement) \cup(E \cap{A_2}^\complement)) &\quad& \nonumber\\&=& \;& \mu^\ast(E \cap A_1 \cap{A_2}^\complement) + \mu^\ast(E \cap{A_1}^\complement) &\quad&\text{since $ A_1 \in \M $}\end{alignat}
```

Combining equations {eq}`eq:18` and {eq}`eq:19`, we obtain

```{math}
\begin{align*}
\mu^\ast(E) = \mu^\ast(E \cap A_1 \cap A_2) + \mu^\ast(E \cap{(A_1 \cap A_2)}^\complement)
\end{align*}
```

Therefore, $ A_1 \cap A_2 \in\M$.


````


In the following, we show that $\restr{\mu^\ast}{\M}$ is $\sigma$-additive.

````{prf:proof}

We prove this by first showing $\mu^\ast$ is additive on $\M$ and then applying {prf:ref}`pro:3` to conclude that $\mu^\ast$ is actually $\sigma$-additive on $\M$.



(Additivity) First, clearly $\mu^\ast(\emptyset) = 0 $ since $\mu^\ast$ is an outer measure. Suppose $ A_1, A_2 \in\M$ and $ A = A_1 \uplus A_2 $. Note that $ A \in\M$ since we have shown that $\M$ is an algebra. It follows that 

```{math}
\begin{align*}
\mu^\ast(A) = \mu^\ast(A \cap A_1) + \mu^\ast(A \cap{A_1}^\complement)
\end{align*}
```

Note that $ A \cap A_1 = A_1 $ and $ A \cap{A_1}^\complement = A_2 $. Therefore,

```{math}
\begin{align*}
\mu^\ast(A) = \mu^\ast(A_1) + \mu^\ast(A_2)
\end{align*}
```

Then by induction, we can show that for $ A_i \in\M$,

```{math}
\begin{align*}
\mu^\ast\left(\biguplus_{i=1}^n {A_i}\right)= \sum_{i=1}^n {\mu^\ast(A_i)}\end{align*}
```


($\sigma$-Additivity) Note that $\mu^\ast$ is $\sigma$-subadditive on $\Pow(\Omega) $(and of course it is also $\sigma$-subadditive on $\M$) because $\mu^\ast$ is an outer measure. Moreover, we have already shown that $\mu^\ast$ is also additive on $\M$. Then {prf:ref}`pro:3` immediately implies that $\mu^\ast$ is $\sigma$-additive.

````


Finally, we show that $\M$ is actually a $\sigma$-algebra. 

````{prf:proof}

Recall that we have already shown $\M$ is an algebra. Hence, we only need to show that $\M$ is closed under countable unions. Suppose that $ A_i \in\M$ and $ A = \bigcup_{i=1}^\infty{A_i}$. Fix a set $ E \subset\Omega$. Note that $\bigcap_{i=1}^n {A_i}\in\M$ since $\M$ is an algebra. It then follows that 

```{math}
\begin{alignat*}
2\mu^\ast(E)
&=& \;& \mu^\ast\left( E \cap\bigcap_{i=1}^n {A_i}\right)+ \mu^\ast\left( E \cap\left(\bigcap_{i=1}^n {A_i}\right)^\complement\right)\\&=&& \mu^\ast\left( E \cap\bigcap_{i=1}^n {A_i}\right)+ \mu^\ast\left( E \cap\bigcup_{i=1}^n {{A_i}^\complement}\right)\end{alignat*}
```

And since $ E \cap\bigcap_{i=1}^n {A_i}\supset E \cap\bigcap_{i=1}^\infty{A_i} = E \cap A $, we have 

```{math}
:label: eq:20
\begin{align}
\mu^\ast(E) \geq\mu^\ast(E \cap A) + \mu^\ast\left( E \cap\bigcup_{i=1}^n {{A_i}^\complement}\right)\end{align}
```

For the convenience of the notations, we denote

```{math}
\begin{align*}

F_i = E \cap\bigcup_{j=1}^i {{A_j}^\complement}\end{align*}
```

Define sets $ G_i $ as follows.

```{math}
\begin{align*}

G_1 &= F_1 & G_i &= F_i \setminus\bigcup_{j=1}^{i-1}{F_j}\quad  i \geq 2
\end{align*}
```

One can show that all $ G_i $'s are mutually disjoint and $\bigcup_{i=1}^n {G_i} = \bigcup_{i=1}^n {F_i}$. It is also true that $\bigcup_{i=1}^\infty{G_i} = \bigcup_{i=1}^\infty{F_i}$. In summary,

```{math}
\begin{align*}
\biguplus_{i=1}^n {G_i}&= \bigcup_{i=1}^n {F_i}& \biguplus_{i=1}^\infty{G_i}&= \bigcup_{i=1}^\infty{F_i} = E \cap A^\complement\end{align*}
```

Applying the additivity of $\mu^\ast$(this is valid because $ G_i \in\M$) to inequality {eq}`eq:20`, we obtain

```{math}
\begin{align*}
\mu^\ast(E) \geq\mu^\ast(E \cap A) + \mu^\ast\left(\biguplus_{i=1}^n G_i\right)= \mu^\ast(E \cap A) + \sum_{i=1}^n {\mu^\ast(G_i)}\end{align*}
```

Letting $ n \to\infty$, 

```{math}
\begin{align*}
\mu^\ast(E) \geq\mu^\ast(E \cap A) + \sum_{i=1}^\infty{\mu^\ast(G_i)}\end{align*}
```

Then we apply the $\sigma$-subadditivity of $\mu^\ast$,

```{math}
\begin{align*}
\mu^\ast(E) \geq\mu^\ast(E \cap A) + \sum_{i=1}^\infty{\mu^\ast(G_i)}\geq\mu^\ast(E \cap A) + \mu^\ast\left(\biguplus_{i=1}^\infty{G_i}\right)= \mu^\ast(E \cap A) + \mu^\ast(E \cap A^\complement)
\end{align*}
```

Therefore, we have shown that 

```{math}
\begin{align*}
\mu^\ast(E) \geq\mu^\ast(E \cap A) + \mu^\ast(E \cap A^\complement)
\end{align*}
```

In fact, the inequality above can be replaced by equality as we have explained before. Therefore, $ A \in\M$ and hence $\M$ is indeed a $\sigma$-algebra.

````


The following theorem extends a pre-measure, i.e., a $\sigma$-additive nonnegative set function on an algebra $\A$ to a measure on the $\sigma$-algebra generated by $\A$.


````{prf:theorem}
:label: thm:2

Let $\A$ be an algebra on $\Omega$, and $\mu_0$ a pre-measure on $\A$. Then $\mu_0$ can be extended to a measure $\mu$ on $\F = \sigma(\A)$, i.e., there exists a measure $\mu: \F\to[0, \infty]$ such that $\restr{\mu}{\A} = \mu_0$. Furthermore, if $\mu_0$ is $\sigma$-fintie, then the extension is unique.

````

````{prf:proof}
TODO
````

````{prf:theorem}
:label: thm:3

Let $\SSS$ be a semi-algebra on $\Omega$, and $\nu: \SSS\to[0, \infty]$ a $\sigma$-additive set function. Then, $\nu$ can be first uniquely extended to a pre-measure $\mu_0$ on $\A(\SSS)$. After that, if $\mu_0$ is $\sigma$-fintie, it can be extended uniquely to a measure $\mu$ on $\sigma(\SSS)$. (Note that $\sigma(\A(\SSS)) = \sigma(\SSS)$).

````
