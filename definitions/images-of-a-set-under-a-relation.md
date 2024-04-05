# Images of a set under a relation

### Direct Image

<details>

<summary><span class="math">R(A) := \{\; y \in B : \exists(x \in A :: (x,y) \in R) \; \}</span></summary>

***

$$\textbf{Relation} \; X \; Y \; R$$

$$\textbf{Includes} \; A \; X$$

***

&#x20;Alloy provides syntax for the direct image. $$R(A)$$ is written in Alloy as `A.R`

</details>

### Images according to De Baets and Kerr

#### Typing

All images have the same basic type requirements, the details of which I will place in a predicate called $$\textbf{BKType}$$.&#x20;

<details>

<summary><span class="math">\textbf{BKType} \; X \; Y \; R \; A \; y</span></summary>

***

$$\textbf{Relation} \; X \; Y \; R$$

$$A \subseteq X$$

$$y \in Y$$

***

```
pred BKType(X,Y: set univ, R: univ->univ, A: set univ, y: univ) {
  R in X->Y
  A in X
  y in Y
}
```

</details>

Furthermore, I have chosen to extract the range of each set comprehension to its own (characteristic) predicate.

#### Sub-direct Image

<details>

<summary><span class="math">\textbf{SubDI} \; X \; Y \; R \; A := \{\; y \in Y : \empty \subset A \subseteq Ry \; \}</span></summary>

***

**Notation.**

1. $$\textbf{SubDI} \; X \; Y \; R \; A$$ can be written $$\textbf{SubDI} \; R \; A$$ when $$X$$ and $$Y$$ are clear from the context.
2. $$\textbf{SubDI} \; R \; A$$ is written in symbols as $$R^{\vartriangleleft}(A)$$

***

```
fun SubDI(X,Y: set univ, R: univ->univ, A: univ) : set univ {
  { y: Y | SubDI[X,Y,R,A,y] }
}

pred SubDI(X,Y: set univ, R: univ->univ, A: set univ, y: univ) {
  BKType[X,Y,R,A,y]

  some A
  A in R.y
}
```

</details>

#### Super-direct Image

<details>

<summary><span class="math">\textbf{SupDI} \; X \; Y \; R \; A  =  \{\; y \in Y : \empty \subset Ry \subseteq A  \; \}</span></summary>

***

**Notation.**

1. $$\textbf{SupDI} \; X \; Y \; R \; A$$ can be written $$\textbf{SupDI} \; R \; A$$ when $$X$$ and $$Y$$ are clear from the context.
2. $$\textbf{SupDI} \; R \; A$$ is written in symbols as $$R^{\vartriangleright}(A)$$

***

```
fun SupDI(X,Y: set univ, R: univ->univ, A: univ) : set univ {
  { y: Y | SupDI[X,Y,R,A,y] }
}

pred SupDI(X,Y: set univ, R: univ->univ, A: set univ, y: univ) {
  BKType[X,Y,R,A,y]

  some R.y
  R.y in A
}
```

</details>

#### Square Image

<details>

<summary><span class="math">\textbf{SqrI} \; X \; Y \; R \; A  =  \{\; y \in Y : \empty \subset A = Ry  \; \}</span></summary>

***

**Notation.**

1. $$\textbf{SqrI} \; X \; Y \; R \; A$$ can be written $$\textbf{SqrI} \; R \; A$$ when $$X$$ and $$Y$$ are clear from the context.
2. $$\textbf{SqrI} \; R \; A$$ is written in symbols as $$R^{\diamond}(A)$$

***

```
fun SqrI(X,Y: set univ, R: univ->univ, A: univ) : set univ {
  { y: B | SqrI[X,Y,R,A,y] }
}

pred SqrI(X,Y: set univ, R: univ->univ, A: set univ, y: univ) {
  BKType[X,Y,R,A,y]

  some A
  A = R.y
}
```

</details>
