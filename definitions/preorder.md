# Preorder

<details>

<summary><span class="math">\textbf{Above} \; A \; R \; S \; y</span></summary>

***

$$\textbf{Preorder} \; A \; R$$

$$\textbf{Includes} \; S \; A$$

$$y \in S$$

$$\forall(s : s \in S : R.s.y)$$

***

**Notation.**

1. $$\textbf{Above} \; S \; y$$ abbreviates $$\textbf{Above} \; A \; R \; S \; y$$ when $$A$$ and $$R$$ are clear from the context.
2. $$\textbf{Above} \; S \; y$$ is abbreviated by $$S \sqsubseteq y$$.

***

```
pred Above(A: set univ, R: univ->univ, S: set univ, y: univ) {
  Preorder[A,R]
  S in A
  y in A
  all s: univ | s in S implies s->y in R 
}
```

</details>

<details>

<summary><span class="math">\textbf{Above} \; A \; R \; S := \{ \; y : \textbf{Above} \; A \; R \; S \; y \; \}</span></summary>

***

```
fun Above(A: set univ, R: univ->univ, S: set univ) : set univ {
  { y: univ | Above[A,R,S,y] }
}
```

</details>

<details>

<summary><span class="math">\textbf{Below} \; A \; R \; S \; y</span></summary>

***

$$\textbf{Preorder} \; A \; R$$

$$\textbf{Includes} \; S \; A$$

$$y \in A$$

$$\forall(s : s \in S : R.y.s)$$

***

**Notation.**

1. $$\textbf{Below} \; S \; y$$ abbreviates $$\textbf{Below} \; A \; R \; S \; y$$ when $$A$$ and $$R$$ are clear from the context.
2. $$\textbf{Below} \; S \; y$$ is abbreviated by $$S \sqsupseteq y$$.

***

```
pred Below(A: set univ, R: univ->univ, S: set univ, y: univ) {
  Preorder[A,R]
  S in A
  y in A
  all s: univ | s in S implies y->s in R 
}
```

</details>

<details>

<summary><span class="math">\textbf{Below} \; A \; R \; S := \{ \; y : \textbf{Below} \; A \; R \; S \; y \; \}</span></summary>

***

```
fun Below(A: set univ, R: univ->univ, S: set univ) : set univ {
  { y: univ | Below[A,R,S,y] }
}
```

</details>

<details>

<summary><span class="math">\textbf{Equivalent} \; A \; R \; x \; y</span></summary>

***

$$\textbf{Preorder} \; A \; R$$

$$x \in A$$

$$y \in A$$

$$R.x.y \wedge R.y.x$$

***

**Notation.**

1. $$\textbf{Equivalent} \; x \; y$$ abbreviates $$\textbf{Equivalent} \; A \; R \; x \; y$$ when $$A$$ and $$R$$ are clear from the context.
2. $$\textbf{Equivalent} \; x \; y$$ is abbreviated by $$x \cong y$$.

***

```
pred Equivalent(A: set univ, R: univ->univ, x,y: univ) {
  Preorder[A,R]
  x in A
  y in A
  x->y in R and y->x in R
}
```

</details>

<details>

<summary><span class="math">\textbf{Opposite} \; A \; R := \{ x,y \in A : R.x.y : \textbf{pair} \; y \; x \}</span></summary>

***

$$\textbf{Preorder} \; A \; R$$

</details>

<details>

<summary><span class="math">\textbf{Product} \; A \; B \; R \; S := \{ \; p,q \in A \times B : R.(\textbf{fst}.p).(\textbf{fst}.q) : S.(\textbf{snd}.p).(\textbf{snd}.q) : \textbf{pair} \; p \; q \; \}</span></summary>

***

$$\textbf{Preorder} \; A \; R$$

$$\textbf{Preorder} \; B \; S$$

***

**Notation.**

1. $$\textbf{Product} \; R \; S$$ abbreviates $$\textbf{Product} \; A \; B \; R \; S$$ when $$A$$ and $$B$$ are clear from the context.
2. $$\textbf{Product} \; R \; S$$ can be written $$R \times S$$.

</details>
