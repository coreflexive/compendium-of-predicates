# Extremal Elements

### Greatest (Max)

<details>

<summary><span class="math">\textbf{Greatest} \; A \; R \; Y \; x</span></summary>

***

$$\textbf{Preorder} \; A \; R$$

$$\textbf{Includes} \; A \; Y$$

$$x \in Y$$

$$\textbf{Above} \; A \; R \; A \; x$$

***

**Notation.**

1. $$\textbf{Greatest} \; A \; R \; Y \; x$$ can be written $$\textbf{Greatest} \; Y \; x$$ when $$A$$ and $$R$$ are clear from the context.
2. $$\textbf{Greatest} \; Y \; x$$ can be written $$x = \textbf{max} \; Y$$.

```
pred Greatest(A: set univ, R: univ->univ, Y: set univ, x: univ) {
  Preorder[A,R]
  Includes[A,Y]
  x in Y
  Above[A,R,A,x]
}
```

</details>

<details>

<summary><span class="math">\textbf{Greatest} \; A \; R \; Y  := \{\; x : \textbf{Greatest} \; A \; R \; Y \; x\;\}</span></summary>

***

**Notation.**

1. $$\textbf{Greatest} \; A \; R \; Y$$ can be written $$\textbf{Greatest} \; Y$$ when $$A$$ and $$R$$ are clear from the context.
2. $$\textbf{Greatest} \; Y$$ can be written $$\textbf{max} \; Y$$.

***

```
fun Greatest(A: set univ, R: univ->univ, Y: set univ) : set univ {
  { x: Y | Greatest[A,R,Y,x] }
}
```

</details>

### Join (Supremum)

<details>

<summary><span class="math">\textbf{Join} \; A \; R \; S \; x</span></summary>

***

$$\textbf{Above} \; A \; R \; S \; x$$

$$\forall(y :  \textbf{Above} \; A \; R \; S \; y : R.x.y)$$

***

```
pred Join(A: set univ, R: univ->univ, S: set univ, x: univ) {
  Above[A,R,S,x]
  all y: univ | Above[A,R,S,y] implies x->y in R
}
```

</details>

<details>

<summary><span class="math">\textbf{Join} \; A \; R \; S</span></summary>

***

$$\{ \; x : \textbf{Join} \; A \; R \; S \; x \; \}$$

***

```
fun Join(A: set univ, R: univ->univ, S: set univ) : set univ {
  { x: univ | Join[A,R,S,x] }
}
```

</details>

### Extended Join

<details>

<summary><span class="math">\textbf{JoinExt} \; A \; R  \; Z \; Y \; x</span></summary>

***

$$\textbf{Includes} \; Z \; A$$

$$\textbf{Includes} \; Y \; Z$$

$$x \in Z$$

$$\forall(z \in Z :: \textbf{Below} \; A \; R \; Y \; z \equiv R.z.x)$$

***

**Notation.**

1. $$\textbf{JoinExt} \; Z \; Y \; x$$ abbreviates $$\textbf{JoinExt} \; A \; R  \; Z \; Y \; x$$ when $$A$$ and $$R$$ are clear from the context.
2. $$\textbf{JoinExt} \; Z \; Y \; x$$ is denoted by $$x = \sqcup_Z Y$$.

***

```
pred JoinExt(A: set univ, R: univ->univ, Z,Y: set univ, x: univ) {
  Includes[Z,A]
  Includes[Y,Z]
  x in Z
  all z: Z | Above[A,R,Y,z] iff x->z in R
}
```

</details>

<details>

<summary><span class="math">\textbf{JoinExt} \; A \; R  \; Z \; Y := \{\; x :  \textbf{JoinExt} \; A \; R  \; Z \; Y \; x\;\}</span></summary>

***

**Notation.**

1. $$\textbf{JoinExt} \;  Z \; Y$$ abbreviates $$\textbf{JoinExt} \; A \; R \;  Z \; Y$$ when $$A$$ and $$R$$ are clear from the context.
2. $$\textbf{JoinExt} \;  Z \; Y$$is denoted by $$\sqcup_Z Y$$.

***

```
fun JoinExt(A: set univ, R: univ->univ, Z,Y: set univ) : set univ {
  { x: Z | JoinExt[A,R,Z,Y,x] }
}
```

</details>

### Least (Min)

<details>

<summary><span class="math">\textbf{Least} \; A \; R \; Y \; x</span></summary>

***

$$\textbf{Preorder} \; A \; R$$

$$\textbf{Includes} \; Y \; A$$

$$x \in Y$$

$$\textbf{Below} \; A \; R \; A \; x$$

***

**Notation**

1. $$\textbf{Least} \; A \; R \; Y \; x$$ can be abbreviated by $$\textbf{Least} \; Y \; x$$ when $$A$$ and $$R$$ are clear from the context.
2. $$\textbf{Least} \; Y \; x$$ can be written $$x = \textbf{min} \; Y$$.

***

```
pred Least(A: set univ, R: univ->univ, Y: set univ, x: univ) {
  Preorder[A,R]
  Includes[Y,A]
  x in Y
  Below[A,R,A,x]
}
```

</details>

<details>

<summary><span class="math">\textbf{Least} \; A \; R \; Y  := \{ \; x : \textbf{Least} \; A \; R \; Y \; x \; \}</span></summary>

***

**Notation.**

1. $$\textbf{Least} \; A \; R \; Y$$ can be written $$\textbf{Least} \; Y$$when $$A$$ and $$R$$ are clear from the context.
2. $$\textbf{Least} \; Y$$ can be written $$\textbf{min} \; Y$$.

***

```
fun Least(A: set univ, R: univ->univ, Y: set univ) : set univ {
  { x: Y | Least[A,R,Y,x] }
}
```

</details>

### Meet (Infimum)

<details>

<summary><span class="math">\textbf{Meet} \; A \; R \; S \; x</span></summary>

***

$$\textbf{Below} \;A \; R \; S \; x$$

$$\forall(y : \textbf{Below} \;A \; R \; S \; y : R.y.x)$$

***

**Notation.**

1. $$\textbf{Meet} \; S \; x$$ abbreviates $$\textbf{Meet} \; A \; R \; S \; x$$ when $$A$$ and $$R$$​ are clear from the context.
2. $$\textbf{Meet} \; S \; x$$ is abbreviated by $$x = \sqcap \; S$$

***

```
pred Meet(A: set univ, R: univ->univ, S: set univ, x: univ) {
  Below[A,R,S,x]
  all y: univ | Below[A,R,S,y] implies y->x in R
}
```

</details>

<details>

<summary><span class="math">\textbf{Meet} \; A \; R \; S := \{ \; x : \textbf{Meet} \; A \; R \; S \; x \; \}</span></summary>

***

**Notation.**

1. $$\textbf{Meet} \; S$$ abbreviates $$\textbf{Meet} \; A \; R \; S$$ when $$A$$ and $$R$$​ are clear from the context.
2. $$\textbf{Meet} \; S$$ is abbreviated by $$\sqcap \; S$$

***

```
fun Meet(A: set univ, R: univ->univ, S: set univ) : set univ {
  { x : univ | Meet[A,R,S,x] }
}
```

</details>

### Extended Meet

<details>

<summary><span class="math">\textbf{MeetExt} \; A \; R  \; Z \; Y \; x</span></summary>

***

$$\textbf{Includes} \; Z \; A$$

$$\textbf{Includes} \; Y \; Z$$

$$x \in Z$$

$$\forall(z \in Z :: \textbf{Below} \; A \; R \; Y \; z \equiv R.z.x)$$

***

**Notation.**

1. $$\textbf{MeetExt} \; Z \; Y \; x$$ abbreviates $$\textbf{MeetExt} \; A \; R  \; Z \; Y \; x$$ when $$A$$ and $$R$$ are clear from the context.
2. $$\textbf{MeetExt} \; Z \; Y \; x$$ is denoted by $$x = \sqcap_Z Y$$.

***

```
pred MeetExt(A: set univ, R: univ->univ, Z,Y: set univ, x: univ) {
  Includes[Z,A]
  Includes[Y,Z]
  x in Z
  all z: Z | Below[A,R,Y,z] iff z->x in R
}
```

</details>

<details>

<summary><span class="math">\textbf{MeetExt} \; A \; R \;  Z \; Y := \{\; x :  \textbf{MeetExt} \; A \; R \;  Z \; Y \; x\;\}</span></summary>

***

**Notation.**

1. $$\textbf{MeetExt} \;  Z \; Y$$ abbreviates $$\textbf{MeetExt} \; A \; R \;  Z \; Y$$ when $$A$$ and $$R$$ are clear from the context.
2. $$\textbf{MeetExt} \;  Z \; Y$$is denoted by $$\sqcap_Z Y$$.

***

```
fun MeetExt(A: set univ, R: univ->univ, Z,Y: set univ) : set univ {
  { x: univ | MeetExt[A,R,Z,Y,x] }
}
```

</details>
