
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

Let $\Omega = (0, 1]$ and

```{math}
\begin{align*}\mathcal{S} = \set{(a, b]}{0 \leq a < b \leq 1}\uplus\{\emptyset\}\end{align*}
```

First, check that $\mathcal{S}$ is a semi-algebra.
Consider the set function $\mu$ on $\mathcal{S}$ given by

```{math}
\begin{align*}\mu(\emptyset) = 0
\quad\text{and}\quad\mu(a, b] = \begin{cases}
\infty,
&a = 0 \\
b - a,
&a > 0
\end{cases}\end{align*}
```

We claim that $\mu$ is additive on $\mathcal{S}$.
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
Then
- ➀ $\mu$ is said to
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

:::{note}

In what follows, by saying $\mu$ is continuous from below (or above)
without specifying a practical set,
we mean that $\mu$ is continuous from below (or above) at every set
in the given class of sets in the context.
And we say $\mu$ is continuous if it is continuous
both from below and above.

:::

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

The next lemma shall be useful in many proofs.


````{prf:lemma}
:label: lem:1

Let $\mathcal{A}$ be an algebra on $\Omega$.
Suppose $\mu$ is an additive set function defined on $\mathcal{A}$.
Then we have the following:
- ➀ If $\mu$ is $\sigma$-additive,
then $\mu$ is continuous.
- ➁ If $\mu$ is continuous from below,
then $\mu$ is $\sigma$-additive.
- ➂ If $\mu$ is continuous from above at $\emptyset$
and $\mu$ is finite,
then $\mu$ is $\sigma$-additive.


````

Since the proof of each statement is
quite long, and each deserves some additional comments,
we shall present the proofs separately.

Proof of 1 of {prf:ref}`lem:1`:


````{prf:proof}
(Continuity from Below)
Suppose $E_n, E \in \mathcal{A}$ and $E_n \uparrow E$.
Let

```{math}
\begin{align*}
F_n = E_{n}\setminus E_{n-1}\quad\forall n \in\N^\ast\end{align*}
```

where $E_0 = \emptyset$.
Note that
- ➀ $E_n = \biguplus_{i=1}^n F_i$, and
- ➁ $\biguplus_{n=1}^\infty F_n = \bigcup_{n=1}^\infty E_n = E$.


Because $\mu$ is additive, we have

```{math}
:label: eq:2
\begin{align}\mu(E_n) = \sum_{i=1}^n \mu(F_i)
\end{align}
```

And by further exploiting the fact that $\mu$ is $\sigma$-additive,
we have

```{math}
:label: eq:3
\begin{align}\mu(E) = \mu(\biguplus_{n=1}^\infty F_n)
= \sum_{n=1}^\infty\mu(F_n)
\end{align}
```

Letting $n \to \infty$ on both sides of {eq}`eq:2`,
we find

```{math}
\begin{align*}\lim_{n \to \infty}\mu(E_n)
= \sum_{i=1}^\infty\mu(F_i)
= \mu(E)
\end{align*}
```

where the last equality follows from {eq}`eq:3`.
Therefore, $\mu$ is continuous from below.

(Continuity from Above)
To prove the continuity from below,
we are going to exploit the result that $\mu$
is continuity from above, which we have just proved.
Suppose that $E_n, E \in \mathcal{A}$, $E_n \downarrow E$,
and $\mu(E_N) < \infty$ for some $N \in \N^\ast$.

:::{note}

In order to apply the result that $\mu$
is continuous from below,
we need to construct
a sequence of increasing sets out of $E_n$'s.

:::

Let

```{math}
\begin{align*}
F_n = E_N \setminus E_n
\quad\forall n \in\N^\ast\end{align*}
```

Note that
- ➀ $F_n \in \mathcal{A}$,
- ➁ $F_n \subseteq F_{n+1}$, and
- ➂ $\bigcup_{n=1}^\infty F_n = E_N \setminus \bigcap_{n=1}^\infty E_n = E_N \setminus E$.


Hence, indeed $F_n \uparrow E_N \setminus E$.
It then follows that $\mu(F_n) \uparrow \mu(E_N \setminus E)$.
Since $\mu$ is of course increasing,
what matters is the following:

```{math}
:label: eq:4
\begin{align}\lim_{n \to \infty}\mu(F_n) = \mu(E_N \setminus E)
\end{align}
```

Note that we have

```{math}
\begin{align*}\mu(F_n) + \mu(E_n) &= \mu(E_N) \\\mu(E_N \setminus E) + \mu(E) &= \mu(E_N)
\end{align*}
```

Equating the right-hand sides yields

```{math}
\begin{align*}\mu(F_n) + \mu(E_n)
= \mu(E_N \setminus E) + \mu(E)
\end{align*}
```

Letting $n \to \infty$, we find

```{math}
\begin{align*}\lim_{n \to \infty}\mu(F_n) + \lim_{n \to \infty}\mu(E_n)
= \mu(E_N \setminus E) + \mu(E)
\end{align*}
```

Plugging in the value of $\lim_{n \to \infty} \mu(F_n)$
using {eq}`eq:4`, we obtain

```{math}
:label: eq:5
\begin{align}\mu(E_N \setminus E) + \lim_{n \to \infty}\mu(E_n)
= \mu(E_N \setminus E) + \mu(E)
\end{align}
```

Because $\mu(E_N \setminus E)$ is finite since $\mu(E_N)$ is,
we are allowed to cancel this term on both sides of {eq}`eq:5`.

:::{note}

As we can see, it is necessary to assume $\mu(E_n)$
in the definition of continuity from above
for we need to subtract a finite number on
both side of {eq}`eq:5`
to obtain the desired result.

:::

Therefore,

```{math}
\begin{align*}\lim_{n \to \infty}\mu(E_n)
= \mu(E)
\end{align*}
```

which shows $\mu$ is indeed continuous from above.

````

Note that in the above proof, we always
consider the addition of two set functions
instead of subtraction.
For example,
we write

```{math}
\begin{align*}\mu(E_N \setminus E_n) + \mu(E_n) = \mu(E_N)
\end{align*}
```

where $E_N \setminus E_n = F_n$, instead of

```{math}
:label: eq:6
\begin{align}\mu(E_N \setminus E_n) = \mu(E_N) - \mu(E_n)
\end{align}
```

though it is more tempting to write {eq}`eq:6`.
The reason is that {eq}`eq:6` may not be valid in general
for chances are that $\mu(E_n) = \infty$.

Therefore, we must be very careful
and first ensure that $\mu(B) < \infty$
before writing down

```{math}
\begin{align*}\mu(A \setminus B) = \mu(A) - \mu(B)
\end{align*}
```

Proof of 2 of {prf:ref}`lem:1`:


````{prf:proof}

It is given that $\mu$ is additive,
continuous from below,
we want to show that it is $\sigma$-additive.
Suppose $E_n, E \in \mathcal{A}$
and $E = \biguplus_{n=1}^\infty E_n$.
Let

```{math}
\begin{align*}
F_n = \biguplus_{i=1}^n E_i
\end{align*}
```

It is clear that $F_n \uparrow E$.
Hence, $\mu(F_n) \uparrow \mu(E)$
since $\mu$ is continuous from below.
Exploiting the fact that $\mu$ is additive, we have

```{math}
\begin{align*}\mu(F_n) = \mu(\biguplus_{i=1}^n E_i)
= \sum_{i=1}^n \mu(E_i)
\end{align*}
```

Therefore,

```{math}
\begin{align*}\sum_{i=1}^\infty\mu(E_i) = \mu(E)
\end{align*}
```

since we have already known the limit of $\mu(F_n)$ is $\mu(E)$.
This shows that $\mu$ is indeed $\sigma$-additive.

````

Proof of 3 of {prf:ref}`lem:1`:


````{prf:proof}

Suppose that $\mu$ is additive,
continuous from above at $\emptyset$,
and $\mu$ is finite.
We want to show $\mu$ is $\sigma$-additive.
Suppose $E_n, E \in \mathcal{A}$
and $E = \biguplus_{n=1}^\infty E_n$.
Construct a sequence of sets $F_n$ as follows:

```{math}
\begin{align*}
F_n = E \setminus\biguplus_{i=1}^{n-1} E_i
\end{align*}
```

Because $F_n \downarrow \emptyset$
and $\mu(F_1) < \infty$(actually $\mu(F_n) < \infty$ for all $n$),
we have $\mu(F_n) \downarrow 0$
by the definition of continuity from above.
Since $\mu$ is finite and additive, we can write

```{math}
\begin{align*}\mu(F_n) = \mu(E) - \mu(\biguplus_{i=1}^{n-1} E_i)
= \mu(E) - \sum_{i=1}^{n-1}\mu(E_i)
\end{align*}
```

Therefore, letting $n \to \infty$ yields

```{math}
\begin{align*}\sum_{i=1}^\infty\mu(E_i) = \mu(E)
\end{align*}
```

This implies $\mu$ is $\sigma$-additive.

````

As the reader might notice, $\mu$ is assumed finite
in the third statement of {prf:ref}`lem:1`.
We shall use an example (see {prf:ref}`eg:4`) to address that
we really need this assumption.
But before showing this example,
we must first study how to extend a set function
from a semi-algebra to the algebra generated by it.



````{prf:example}
:label: eg:4

Recall {prf:ref}`eg:2`
where $\Omega = (0, 1]$,

```{math}
\begin{align*}\mathcal{S} = \set{(a, b]}{0 \leq a < b \leq 1}\uplus\{\emptyset\}\end{align*}
```

is a semi-algebra, and $\mu$ is a set function
on $\mathcal{S}$ given by

```{math}
\begin{align*}\mu(\emptyset) = 0
\quad\text{and}\quad\mu(a, b] = \begin{cases}
\infty,
&a=0 \\
b - a,
&a > 0
\end{cases}\end{align*}
```

We have shown in {prf:ref}`eg:2` that $\mu$ is additive
but not $\sigma$-additive.

````
