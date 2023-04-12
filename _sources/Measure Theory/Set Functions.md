
```{index} set function
```
# Set Functions

A **set function**
is a function defined on collection of sets
whose range is usually the union
of non-negative real numbers
and the positive infinity, $\R_{\geq 0} \cup \{\infty\}$.


````{prf:definition}
:label: def:5

```{index} additive set function
```

A set function, $\mu$, defined
on $\mathcal{C} \subseteq \mathcal{P}(\Omega)$ is said to
be **additive**
or **finitely additive**
if
- ➀ $\mu(\emptyset) = 0$, and
- ➁ $\mu \brk{ \biguplus_{i=1}^n A_i } = \sum_{i=1}^n \mu(A_i)$.


````

By the second condition in above definition,
the natural class of sets to consider
is the algebra since we
would want that the class is closed under finite unions of sets.


:::{note}

The condition $\mu(\emptyset) = 0$
is actually redundant in all cases except the one
where $\mu(A) = \infty$ for all $A \in \mathcal{C}$.
To see this, suppose that $\mu(A) < \infty$
for some $A \in \mathcal{C}$.
We have $A = A \uplus \emptyset$.
It then follows from the second condition
that $\mu(A) = \mu(A) + \mu(\emptyset)$,
which further implies $\mu(\emptyset) = 0$
since $\mu(A) < \infty$.

:::

If $A \subseteq B$,
then it is natural to expect that $\mu(A) \leq \mu(B)$.
It is indeed the case.
But the proof is not completely trivial.
We can always write $B = A \uplus (B \setminus A)$.
Then, we have

```{math}
\begin{align*}\mu(B) = \mu(A) + \mu(B \setminus A)
\geq\mu(A)
\end{align*}
```

Note that the above inequality holds
no matter whether $\mu(B \setminus A)$ is finite or not.



````{prf:definition}
:label: def:6

```{index} $\sigma$-additive set function
```

A set function, $\mu$,
defined on $\mathcal{C} \subseteq \mathcal{P}(\Omega)$
is said to be **$\sigma$-additive**
if
- ➀ $\mu(\emptyset) = 0$, and
- ➁ $\mu\brk{ \biguplus_{n=1}^\infty A_n } = \sum_{n=1}^\infty \mu(A_n)$


````

````{prf:example}
:label: eg:2

Let $\Omega = (0, 1)$ and

```{math}
\begin{align*}\mathcal{C} = \set{(a, b]}{0 \leq a < b < 1}\end{align*}
```

Consider the set function $\mu$ on $\mathcal{C}$ given by

```{math}
\begin{align*}\mu(a, b] = \begin{cases}
\infty,
&a = 0 \\
b - a,
&a > 0
\end{cases}\end{align*}
```

We claim that $\mu$ is additive on $\mathcal{C}$.
Suppose that

```{math}
\begin{align*}(a, b]
= \biguplus_{i=1}^n (a_i, b_i]\end{align*}
```

There are two cases.

(Case 1: $a = 0$) If $a = 0$, then $\mu (a, b] = \infty$.
And there exists $i$ such that $a_i = 0$,
which implies $\mu(a_i, b_i] = \infty$.
In this case, we have

```{math}
\begin{align*}\infty = \mu(a, b]
= \sum_{i=1}^n \mu(a_i, b_i] = \infty\end{align*}
```
(Case 2: $a > 0$) Without loss of generality,
we may assume $a_i < a_{i+1}$ for all $i$.
Then it is clear that $a_1 = a$, $b_n = b$, and

```{math}
\begin{align*}
b_i = a_{i+1}\quad\forall i = 1, \ldots, n-1
\end{align*}
```

It follows that

```{math}
\begin{align*}\sum_{i=1}^n \mu(a_i, b_i]
= \sum_{i=1}^n b_i - a_1
= b - a
= \mu(a, b]\end{align*}
```

Therefore, we conclude that $\mu$ is indeed additive.
However, $\mu$ is not $\sigma$-additive.
To see this, we note that

```{math}
\begin{align*}(0, \frac{1}{2}]
= \biguplus_{i = 2}^\infty( \frac{1}{i+1}, \frac{1}{i}]\end{align*}
```

We have

```{math}
\begin{align*}\sum_{i=2}^\infty\mu(\frac{1}{i+1}, \frac{1}{i}]
= \sum_{i=2}^\infty\brk{ -\frac{1}{i+1} + \frac{1}{i}}
= \lim_{n \to \infty}\brk{ \frac{1}{2} - \frac{1}{n+1} }
= \frac{1}{2}\end{align*}
```

whereas

```{math}
\begin{align*}\mu(0, \frac{1}{2}] = \infty\end{align*}
```

Therefore, $\mu$ is not $\sigma$-additive.

````

````{prf:definition}
:label: def:7

```{index} continuity from below
```

```{index} continuity from above
```

Let $\mu$ be a set function
defined on $\mathcal{C} \subseteq \mathcal{P}(\Omega)$.
Then- ➀ $\mu$ is said to
be **continuous from below**
at set $E \in \mathcal{C}$ if

```{math}
\begin{align*}
E_n \in\mathcal{C}, \; E_n \uparrow E
\implies\mu(E_n) \uparrow\mu(E)
\end{align*}
```
- ➁ $\mu$ is said to
be **continuous from above**
at set $E \in \mathcal{C}$ if

```{math}
\begin{align*}
E_n \in\mathcal{C}, \; E_n \downarrow E
\quad\text{and}\quad\exists n_0 \in\N^\ast, \;\mu(E_{n_{0}}) < \infty\implies\mu(E_n) \downarrow\mu(E)
\end{align*}
```


````

The symbol $E_n \uparrow E$ means that

```{math}
\begin{align*}
E_n \subseteq E_{n+1}\quad\forall n \in\N^\ast\quad\text{and}\quad\bigcup_{n = 1}^\infty E_n = E
\end{align*}
```

And by writing $\mu(E_n) \uparrow \mu(E)$,
we mean that
- ➀ $\{\mu(E_n)\}$ is an increasing sequence
(of extended real numbers), and
- ➁ $\lim_{n \to \infty} \mu(E_n) = \mu(E)$.


In fact, in the above definition, we only need to assume
the limit of $\mu(E_n)$ is $\mu(E)$
since we have already noticed that

```{math}
\begin{align*}
A \subseteq B  \implies\mu(A) \leq\mu(B)
\end{align*}
```

Now, we pay attention to the condition in the second statement
of the above definition, i.e.,
the definition of the continuity from above.
Note that comparing to the continuity from below,
we impose an additional requirement that $\mu(E_{n_0})$ is finite
for some index $n_0$.
The reason why we do this is explained through the following example.


````{prf:example}
:label: eg:3

Let $\Omega = \R$ and $E_n = [n, \infty)$.
We would want the length of $E_n$, $\lambda(E_n)$,
to be infinity.
Actually, $\lambda$ is a measure, called Lebesgue measure,
on the Borel $\sigma$-algebra of the real line,
which is a generalization of the concept of length.

Note that $E_n \downarrow \emptyset$.
We have $\lambda(E_n) = \infty$ whereas $\lambda(\emptyset) = 0$.
In this case, $\lambda(E_n)$ does not tend to $\lambda(\emptyset)$
as $n \to \infty$.
If we do not assume $\lambda(E_n)$ is finite for some $n = n_0$,
then we cannot say $\lambda$ is continuous from above at $\emptyset$
in this case.
However, we really want that the measure to be continuous from above
at all sets.
Therefore, it is necessary to impose an additional condition
as in {prf:ref}`def:7`.

````
