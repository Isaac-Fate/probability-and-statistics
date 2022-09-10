# Measures
\ 
A **set function** is a function that maps from collections of subsets of $\Omega$ to the extended real numbers $\R\cup\left\{\pm\infty\right\}$.
\ 
We say a set function $\mu$ is **finitely additive** if 
```{math}
\begin{align*}
\mu(A \uplus B) = \mu(A) + \mu(B)
\end{align*}
```
The above equation also holds for finitely many disjoint unions of sets, that is, 
```{math}
:label: eq:1
\begin{align}
\mu\left(\biguplus_{i=1}^n A_i\right)= \sum_{i=1}^n \mu(A_i)
\end{align}
```
which can be proved by the mathematical induction.
\ 
If {eq}`eq:1` holds for countably infinite disjoint unions of sets, i.e., 
```{math}
\begin{align*}
\mu\left(\biguplus_{i=1}^n A_i\right)= \sum_{i=1}^\infty\mu(A_i)
\end{align*}
```
Then we say $\mu$ is **$\sigma$-additive**. 
````{prf:definition}
Let $(\Omega, \F)$ be a measurable space. A set function $\mu: \F\to[0, \infty]$ is called a **measure** if
1. $\mu(\emptyset) = 0$, and 
2. $\mu$ is $\sigma$-additive.
The triplet $(\Omega, \F, \mu)$ is then called a **measure space**.
````
\ 
If $\mu$ is only finitely additive, we say that $\mu$ is a **finitely additive measure**. 
````{prf:remark}
If we assume $\mu: \F\to[0, \infty]$ is $\sigma$-additive, and there exists some set $A \in\F$ such that $\mu(A) < \infty$, then $\mu(\emptyset) = 0$ holds naturally and hence condition 1 is redundant. To see this, we note that $\mu(A) = \mu(A \uplus\emptyset) = \mu(A) + \mu(\emptyset)$, which implies $\mu(\emptyset) = 0$ provided that $\mu(A)$ is finite.
````
\ 
The following proposition shows the monotonicity of a measure.
````{prf:proposition}
:label: pro:2
Let $(\Omega, \F, \mu)$ be a measure space. For $A, B \in\F$, we have
```{math}
:label: eq:2
\begin{align}
A \subset B \implies\mu(A) \leq\mu(B)
\end{align}
```
Moreover, if $\mu(A) < \infty$ in {eq}`eq:2`, we have 
```{math}
\begin{align*}
\mu(B \setminus A) = \mu(B) - \mu(A)
\end{align*}
```
````
````{prf:proof}
Suppose $A \subset B$. We have 
```{math}
\begin{align*}
B = A \uplus(B \setminus A)
\end{align*}
```
By the $\sigma$-additivity (or weaker, the finite additivity), it follows that 
```{math}
\begin{align*}
\mu(B) = \mu(A) + \mu(B \setminus A)
\end{align*}
```
{eq}`eq:2` follows since $\mu(B \setminus A) \geq 0$. If $\mu(A) < \infty$, by subtracting $\mu(A)$ from both sides of the above equation, we obtain
```{math}
\begin{align*}
\mu(B) - \mu(A) = \mu(B \setminus A)
\end{align*}
```
````
\ 
Given a sequence of sets $\left\{A_k\right\}$, we need this sequence of sets to be mutually disjoint in order to apply the $\sigma$-additivity of a measure. However, it is not the case in general. But we can easily construct another sequence of mutually disjoint sets from $\left\{A_k\right\}$ while keeping the union of first $n$ sets unchanged. The procedure is illustrated in the following proposition.
````{prf:proposition}
:label: pro:1
Let $\left\{A_k\right\}_{k\in\Ns}$ be sequence of subsets of $\Omega$. Let $B_k$ be given by 
```{math}
\begin{align*}
B_k = A_k \setminus\bigcup_{i=1}^{k-1} A_i
\end{align*}
```
where $A_0 := \emptyset$. Then $\left\{ B_k \right\}$ is a family of mutually disjoint sets, and 
```{math}
\begin{align*}
\biguplus_{k=1}^n B_k 
= \bigcup_{k=1}^n A_k
\quad\forall n \in\Ns\end{align*}
```
Specially, 
```{math}
\begin{align*}
\biguplus_{k=1}^\infty B_k 
= \bigcup_{k=1}^\infty A_k
\end{align*}
```
````
````{prf:remark}
This technique will be frequently used in the proofs of upcoming propositions and theorem.
````
````{prf:proof}
TODO
````
````{prf:proposition}
Let $(\Omega, \F, \mu)$ be a measure space, and $\left\{A_k\right\}$ a sequence of sets in $\F$. We have 
```{math}
:label: eq:3
\begin{align}
\mu\left(\bigcup_{k=1}^\infty A_k\right)\leq\sum_{k=1}^\infty\mu(A_k)
\end{align}
```
````
````{prf:remark}
If a set function satisfies {eq}`eq:3`, we say that it is **$\sigma$-subadditive**.
````
````{prf:proof}
Let $B_k$ be given by 
```{math}
\begin{align*}
B_k = A_k \setminus\bigcup_{i=1}^{k-1} A_i
\end{align*}
```
as in {prf:ref}`pro:1`. Then we have 
```{math}
\begin{align*}
\mu\left(\bigcup_{k=1}^\infty A_k\right)        = \mu\left(\biguplus_{k=1}^\infty B_k\right)        = \sum_{k=1}^\infty\mu(B_k)
\leq\sum_{k=1}^\infty\mu(A_k)
\end{align*}
```
The last inequality follows from {prf:ref}`pro:2`.
````
````{prf:proposition}
:label: pro:3
TODO
````
