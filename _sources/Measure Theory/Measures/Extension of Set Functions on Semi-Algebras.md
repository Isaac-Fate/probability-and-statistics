# Extension of Set Functions on Semi-Algebras
````{prf:theorem}
:label: thm:1
Let $\SSS$ be a semi-algebra on $\Omega$, and $\mu: \SSS\to[0, \infty]$ a nonnegative additive (resp. $\sigma$-additive) set function. Then $\mu$ can be extended uniquely to an additive (resp. $\sigma$-additive) function $\nu$ on $\A(\SSS)$. That is, $\exists! \nu: \A(\SSS) \to[0, \infty]$ such that
1. $\nu$ is additive (resp. $\sigma$-additive), and 
2. $\restr{\nu}{\SSS} = \mu$.
\
To be specific, this extension $\nu$ is given by 
```{math}
\begin{align*}
\nu(A) = \sum_{i=1}^n \mu(E_i)
\end{align*}
```
where $\left\{E_1, \ldots, E_n\right\}$ is a family of mutually disjoint sets in $\SSS$ satisfying $A = \biguplus_{i=1}^n E_i$.
````
