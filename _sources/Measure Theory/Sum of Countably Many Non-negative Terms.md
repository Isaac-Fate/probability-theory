# Sum of Countably Many Non-negative Terms

````{prf:definition}
:label: def:9

Let $A$ be a family of
countably infinitely many
non-negative terms in extended real numbers.
Formally,

```{math}
\begin{align*}
A = \set{a_\alpha \in \overline{\R}_{\geq 0} }{\alpha \in \Lambda}\end{align*}
```

where $\Lambda$ is a countably infinite index set.
Then the sum of terms in $A$ is defined by
the sum of the series

```{math}
\begin{align*}\sum_{n=1}^\infty a_{\sigma(n)}\end{align*}
```

where $\sigma: \N^\ast \to \Lambda$ is a bijection.

````

````{prf:definition}
:label: def:8

Let $\{a_n\}$ be a sequence,
and $\sigma: \N^\ast \to \N^\ast$
a bijection.
Let $\hat{a}_n$ be given by

```{index} rearrangement of a sequence
```

```{math}
\begin{align*}\hat{a}_n := a_{\sigma(n)},
\quad n \in\N^\ast\end{align*}
```

Then sequence $\sigma$
is said to be an **rearrangement**
of $\{a_n\}$ into sequence $\{\hat{a}_n\}$.

````

````{prf:theorem}
:label: thm:4

Let $\{a_n\}$ be a sequence of complex numbers,
and $\sigma$ an rearrangement.
If the series $\sum a_n$ converges absolutely to sum $s$,
then $\sum a_{\sigma(n)}$ also converges absolutely to $s$.

````

````{prf:corollary}
:label: cor:1

Let $\{a_n\}$ be a sequence consisting
of non-negative terms in extended real numbers,
possibly including infinity,
and $\sigma$ be an rearrangement.
Then

```{math}
:label: eq:12
\begin{align}\sum_{n=1}^\infty a_{\sigma(n)}
= \sum_{n=1}^\infty a_n
\end{align}
```

````

:::{note}

Equation {eq}`eq:12` should be understood
as a compact expression containing
the following two meanings.
- ➀ If $\sum a_n$ converges to a (non-negative)
sum $s$,
then $\sum a_{\sigma(n)}$ also converges to $s$.
- ➁ If $\sum a_n$ diverges to infinity
(either $a_n$'s are all finite numbers
and the series diverges to infinity
or there exists $\infty$ among $a_n$'s),
then $\sum a_{\sigma(n)}$ also diverges to infinity.


:::

````{prf:definition}
:label: def:10

```{index} double sequence
```

A **double sequence**
is in general any function whose domain is $\N^\ast \times \N^\ast$.
In this book, we are particularly interested in
the function whose values are complex numbers,
or non-negative extended real numbers.
The double sequence is denoted by $\{a_{m,n}\}$
where the function variables $m, n \in \N^\ast$
are referred to as indices,
and the function value $a_{m,n}$
is called term.

````

:::{note}

Concerning the usual notation for a function in above definition,
the double sequence should be written as $f(m, n)$
where $m, n \in \N^\ast$.
However, we adopt the notation $a_{m,n}$
to emphasize that the function values, or terms,
are indexed by two natural numbers.

:::

````{prf:definition}
:label: def:11

Let $\{a_{m,n}\}$ be a double sequence,
and $\{s_{p,q}\}$ be another double sequence defined by

```{index} double series
```

```{math}
\begin{align*}
s_{p,q} = \sum_{m=1}^p \sum_{n=1}^q a_{m,n}\end{align*}
```

The pair $(\{a_{m,n}\}, \{s_{p,q}\})$
is called the **double series**,
and is denoted by $\sum_{m,n} a_{m,n}$.
The sequence $\{s_{p,q}\}$ is referred to as
the $(p,q)$-th partial sum of $\sum_{m,n} a_{m,n}$.

````
