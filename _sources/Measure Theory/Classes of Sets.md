# Classes of Sets

````{prf:definition}
:label: def:1

```{index} semi-algebra
```

A collection of subsets of $\Omega$, $\mathcal{S}$,
is a **semi-algebra**
if it satisfies the following properties:
- ➀ $\Omega \in \mathcal{S}$
- ➁ $A, B \in \mathcal{S} \implies A \cap B \in \mathcal{S}$
- ➂ The complement of every set in $\mathcal{S}$ can be
written as a finite disjoint union
of sets in $\mathcal{S}$.
Formally, $\forall A \in \mathcal{S}, \; \exists E_1, \ldots, E_n \in \mathcal{S}$
such that $A^\complement = \biguplus_{i=1}^n E_i$


````

````{prf:example}
:label: eg:1

Let $\Omega = \R$.
Suppose $\mathcal{S}$ is a collection of subsets in $\R$
consisting of intervals of the following forms:
- ➀ $(a, b]$
- ➁ $(-\infty, b]$
- ➂ $(a, \infty)$
- ➃ $(-\infty, \infty) = \R$


One may check that $\mathcal{S}$ is indeed a semi-algebra by definition.
And it is by studying this type of collection of sets that
the definition of semi-algebra arises.

````

````{prf:definition}
:label: def:2

```{index} algebra
```

A collection of subsets of $\Omega$, $\mathcal{A}$,
is called an **algebra** if
- ➀ $\Omega \in \mathcal{A}$
- ➁ $A, B \in \mathcal{A} \implies A \cap B \in \mathcal{A}$
- ➂ $A \in \mathcal{A} \implies A^\complement \in \mathcal{A}$


````

````{prf:proposition}
:label: pro:1

Let $\{\mathcal{A}_\alpha\}_{\alpha \in \Lambda}$
be a collection of algebras in $\Omega$
where $\Lambda$ is any index set,
then

```{math}
\begin{align*}\bigcap_{\alpha \in \Lambda}\mathcal{A}_{\alpha}\end{align*}
```

is also an algebra.

````

````{prf:proof}

TODO

````

````{prf:definition}
:label: def:3

```{index} $\sigma$-algebra
```

A collection of subsets of $\Omega$, $\mathcal{F}$,
is called a **$\sigma$-algebra** if
- ➀ $\Omega \in \mathcal{F}$
- ➁ $\mathcal{F}$ is closed under countable intersections,
i.e,. $A_n \in \mathcal{F} \; \forall n \in \N^\ast \implies \bigcap_{n=1}^\infty A_n \in \mathcal{F}$
- ➂ $A \in \mathcal{F} \implies A^\complement \in \mathcal{F}$


````

Of course, a $\sigma$-algebra is also closed under finite intersections
(and unions)
since we can always write

```{math}
\begin{align*}\bigcap_{n=1}^m A_n
= \bigcap_{n=1}^m A_n \cap\bigcap_{n=m+1}^\infty\Omega
= \bigcap_{n=1}^\infty A_n
\quad\text{where $A_n = \Omega$ for $n \geq m+1$}\end{align*}
```

Therefore, the $\sigma$-algebra is of course an algebra.

Analogous to {prf:ref}`pro:1`, any intersections of $\sigma$-algebras
is also itself a $\sigma$-algebra.


````{prf:proposition}
:label: pro:2

Let $\{\mathcal{F}_\alpha\}_{\alpha \in \Lambda}$
be a collection of $\sigma$-algebras in $\Omega$
where $\Lambda$ is any index set,
then

```{math}
\begin{align*}\bigcap_{\alpha \in \Lambda}\mathcal{F}_{\alpha}\end{align*}
```

is also a $\sigma$-algebra.

````

Having proved {prf:ref}`pro:1` and {prf:ref}`pro:2`,
we may introduce the algebra and $\sigma$-algebra
generated by a class of subsets in $\Omega$.


````{prf:definition}
:label: def:4

```{index} algebra generated by class of sets
```

Let $\mathcal{C}$ be a class of subsets in $\Omega$.
The **algebra generated by $\mathcal{C}$**,
is defined by

```{index} $\sigma$-algebra generated by class of sets
```

```{math}
\begin{align*}\mathcal{A}(\mathcal{C})
:= \bigcap_{
\text{$\mathcal{A}$ is an algebra, }\mathcal{A}
\supseteq \mathcal{C}
}\mathcal{A}\end{align*}
```

That is, it is the intersection of all algebras
containing $\mathcal{C}$.
Similarly, the **$\sigma$-algebra generated by $\mathcal{C}$**
is defined by

```{math}
\begin{align*}\sigma(\mathcal{C})
:= \bigcap_{
\text{$\mathcal{F}$ is a $\sigma$-algebra, }\mathcal{F}
\supseteq \mathcal{C}
}\mathcal{F}\end{align*}
```

````

Note that the set

```{math}
\begin{align*}\set{\mathcal{A} \subset \mathcal{P}(\Omega)}{\text{$\mathcal{A}$ is an algebra, }\mathcal{A} \supseteq \mathcal{C}}\end{align*}
```

is clearly nonempty since the power set, $\mathcal{P}(\Omega)$,
itself is one of its element.
And then by {prf:ref}`pro:1`, $\mathcal{A}(\mathcal{C})$
is indeed well-defined, and so is $\sigma(\mathcal{C})$.

One important property for $\mathcal{A}(\mathcal{C})$(resp. $\sigma(\mathcal{C})$) is that
it is the *smallest* algebra (resp. $\sigma$-algebra)
containing $\mathcal{C}$, as stated in the following proposition.


````{prf:proposition}
:label: pro:3

Let $\mathcal{C} \subseteq \mathcal{P}(\Omega)$.
We have the following:
- ➀ If $\mathcal{A}$ is an algebra containing $\mathcal{C}$,
then $\mathcal{A} \supseteq \mathcal{A}(\mathcal{C})$.
- ➁ If $\mathcal{F}$ is a $\sigma$-algebra containing $\mathcal{C}$,
then $\mathcal{F} \supseteq \sigma(\mathcal{C})$.


````

As we see in {prf:ref}`eg:1`,
it is easy to describe the elements in a semi-algebra
directly in terms of subsets of $\Omega$.
However, it is difficult in general to describe
the elements in an algebra,
and it is even more difficult to do the same
for the $\sigma$-algebra.

It is because there is no explicit form of
describing a $\sigma$-algebra in terms of subsets in $\Omega$
that makes the extension of a measure (or any properties) from
the semi-algebra to $\sigma$-algebra extremely difficult.
As we shall see in many proofs,
we will exploit the property of a $\sigma$-algebra
in an *inductive* way rather than a *constructive* one.

Fortunately, we do have an explicit form for the algebra generated
by a semi-algebra $\mathcal{S}$, $\mathcal{A}(\mathcal{S})$,
in terms of sets in $\mathcal{S}$.
It turns out that it is simply the collection
of all finite disjoint unions of sets in $\mathcal{S}$.


````{prf:theorem}
:label: thm:2

Let $\mathcal{S}$ be a semi-algebra on $\Omega$.
Then

```{math}
:label: eq:1
\begin{align}
A \in\mathcal{A}(\mathcal{S})
\iff\exists E_1, \ldots, E_n \in\mathcal{S}, \;
A = \biguplus_{i=1}^n E_i
\end{align}
```

````

:::{note}

Note that the integer $n$ in {eq}`eq:1` is not fixed.
That is the choice of $n$ may vary for different set $A$.

:::

````{prf:proof}
(Proof of $\impliedby$) The reverse direction of {eq}`eq:1`
is easy to prove.
Suppose $A = \biguplus_{i=1}^n E_i$ where each $E_i \in \mathcal{S}$.
Then clearly $A \in \mathcal{A}(\mathcal{S})$
since the algebra is closed under finite unions.

(Proof of $\implies$)
The proof of the forward direction is more interesting.

:::{note}

Note that given $A \in \mathcal{A}(\mathcal{S})$,
it is tempting and yet difficult
to find a representation of $A$
as the right-hand side of {eq}`eq:1`.
Hence, we shall prove this in an indirect way.
Instead of finding a specific representation of $A$,
we shall look at all representations described by {eq}`eq:1`.
That is, we consider the collection, say $\mathcal{C}$,
of all finite disjoint unions of sets in $\mathcal{S}$.
And then we show
that $\mathcal{A}(\mathcal{S}) \subseteq \mathcal{C}$.

:::

Define

```{math}
\begin{align*}\mathcal{C}
= \set{E \subseteq \Omega}{
\exists E_1, \ldots, E_n \in \mathcal{S}, \;
E = \biguplus_{i=1}^n E_i
}\end{align*}
```

The goal is to show that this collection $\mathcal{C}$
is actually an algebra containing $\mathcal{S}$.

It is clear that $\mathcal{C} \supseteq \mathcal{S}$
by the definition of $\mathcal{C}$.
What remains to show is that $\mathcal{C}$
is an algebra.
We need to check whether it satisfies
each of the three properties one after another.

First, note that $\Omega \in \mathcal{C}$
since $\Omega \in \mathcal{S}$
and we have seen that $\mathcal{C} \supseteq \mathcal{S}$.

Now, we show $\mathcal{C}$ is closed under intersections.
Let $E, F \in \mathcal{C}$.
By definition, $E$ and $F$ can be written as

```{math}
\begin{align*}
E = \biguplus_{i=1}^n E_i
\quad\text{and}\quad
F = \biguplus_{j=1}^m F_j
\end{align*}
```

where $E_i, F_j \in \mathcal{S}$.
It then follows that

```{math}
\begin{align*}
E \cap F
= \biguplus_{i=1}^n \brk{
E_i \cap \biguplus_{j=1}^m F_j
}
= \biguplus_{i=1}^n \biguplus_{j=1}^m \brk{E_i \cap F_j}\end{align*}
```

Note that $E_i \cap F_j \in \mathcal{S}$.
Hence, we have $E \cap F \in \mathcal{C}$
since the above equation says $E \cap F$
is a finite disjoint union of sets, $(E_i \cap F_j)$'s,
in $\mathcal{S}$.

We also need to show $\mathcal{C}$ is closed under complements.
Let $E \in \mathcal{C}$.
The set $E$ can be written as

```{math}
\begin{align*}
E = \biguplus_{i=1}^n E_i
\end{align*}
```

where $E_i \in \mathcal{S}$.
Then, the complement of $E$,

```{math}
\begin{align*}
E^\complement = \bigcap_{i=1}^n E^\complement_i
\end{align*}
```

By the property of semi-algebra,
each $E^\complement_i$ can be written as

```{math}
\begin{align*}
E^\complement_i = \biguplus_{j=1}^{m_i} F_{i,j}\end{align*}
```

where $F_{i,j} \in \mathcal{S}$.
Therefore, $E^\complement_i \in \mathcal{C}$
by the definition of $\mathcal{C}$.
And then $E^\complement \in \mathcal{C}$
since we have already shown
that $\mathcal{C}$ is closed under finite intersections.

In summary, we have proved so far that $\mathcal{C}$
is indeed an algebra containing $\mathcal{S}$.
It then follows that $\mathcal{A}(\mathcal{S}) \subseteq \mathcal{C}$
since $\mathcal{A}(\mathcal{S})$
is the smallest algebra containing $\mathcal{S}$.
Therefore, for each $A \in \mathcal{A}(\mathcal{S})$, $A$
can always be written as a finite disjoint
union of sets in $\mathcal{S}$
by the definition of $\mathcal{C}$.

````