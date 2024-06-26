# Magma

<details>

<summary><span class="math">\textbf{Magma} \; A \; \otimes</span></summary>

***

$$\textbf{Function} \; (A \times A) \; A \; \otimes$$

***

```
pred Magma(A: set univ, op: univ->univ->univ) {
  op in (A->A)-> one A
}
```

</details>

<details>

<summary><span class="math">\textbf{AutoInverse} \; A \; f \; I</span></summary>

***

$$\textbf{Unital} \; A \; f\; I$$

$$\forall(x \in A ::f(x,x) = I)$$

***

```
pred AutoInverse(A: set univ, f: univ->univ->univ, I: univ) {
  Unital[A,f,I]
  all x: A | f[x,x] = I
}
```

</details>

<details>

<summary><span class="math">\textbf{Idempotent} \; A \; \otimes</span></summary>

***

$$\textbf{Magma} \; A \; \otimes$$

$$\forall(a \in A :: a \otimes a = a)$$

***

```
pred Idempotent(A: set univ, op: univ->univ->univ) {
  Magma[A,op]
  all a: A | op[a,a] = a
}
```

</details>

<details>

<summary><span class="math">\textbf{Inverse} \; A \; f \; I \; y \; x</span></summary>

***

$$\textbf{LeftInverse} \; A \; f \; I \; y \; x$$

$$\textbf{RightInverse} \; A \; f \; I \; y \; x$$

***

```
pred Inverse(A: set univ, f: univ->univ->univ, I,y,x: univ) {
  LeftInverse[A,f,I,y,x]
  RightInverse[A,f,I,y,x]
}
```

</details>

<details>

<summary><span class="math">\textbf{LeftInverse} \; A \; f \; I \; y \; x</span></summary>

***

$$\textbf{Unital} \; A \; f \; I$$

$$f(L,x) = I$$

***

```
pred LeftInverse(A: set univ, f: univ->univ->univ, I,L,x: univ) {
  Unital[A,f,I]
  f[L,x] = I
}
```

</details>

<details>

<summary><span class="math">\textbf{LeftUnit} \; A \; \otimes \; I</span></summary>

***

$$\textbf{Magma} \; A \; \otimes$$

$$I \in A$$

$$\forall(x \in A :: I \otimes x = x )$$

***

```
pred LeftUnit(A: set univ, op: univ->univ->univ, I: univ) {
  Magma[A,op]
  I in A
  all x: A | op[I,x] = x
}
```

</details>

<details>

<summary><span class="math">\textbf{LeftZero} \; A \; f \; Z</span></summary>

***

$$\textbf{Magma} \; A \; \otimes$$

$$I \in A$$

$$\forall(x \in A :: f(Z,x) = Z)$$

***

```
pred LeftZero(A: set univ, f: univ->univ->univ, Z: univ) {
  Magma[A,f]
  Z in A
  all x: A | f[Z,x] = Z
}
```

</details>

<details>

<summary><span class="math">\textbf{RightInverse} \; A \; f \; I \; y \; x</span></summary>

***

$$\textbf{Unital} \; A \; f \; I$$

$$f(x,R) = I$$

***

```
pred RightInverse(A: set univ, f: univ->univ->univ, I,R,x: univ) {
  Unital[A,f,I]
  f[x,R] = I
}
```

</details>

<details>

<summary><span class="math">\textbf{RightUnit} \; A \; \otimes \; I</span></summary>

***

$$\textbf{Magma} \; A \; \otimes$$

$$I \in A$$

$$\forall(x \in A :: x = x \otimes I )$$

***

```
pred RightUnit(A: set univ, op: univ->univ->univ, I: univ) {
  Magma[A,op]
  I in A
  all x: A | x = op[x,I]
}
```

</details>

<details>

<summary><span class="math">\textbf{RightZero} \; A \; f \; Z</span></summary>

***

$$\textbf{Magma} \; A \; \otimes$$

$$I \in A$$

$$\forall(x \in A :: f(x,Z) = Z)$$

***

```
pred RightZero(A: set univ, f: univ->univ->univ, Z: univ) {
  Magma[A,f]
  Z in A
  all x: A | f[x,Z] = Z
}
```

</details>

<details>

<summary><span class="math">\textbf{Symmetric} \; A \; \otimes</span></summary>

***

$$\textbf{Magma} \; A \; \otimes$$

$$\forall(x,y \in A :: x \otimes y = y \otimes x)$$

***

```
pred Symmetric(A: set univ, op: univ->univ->univ) {
  Magma[A,op]
  all x,y: A | op[x,y] = op[y,x]
}
```

</details>

<details>

<summary><span class="math">\textbf{Unital} \; A \; \otimes \; I</span></summary>

***

$$\textbf{LeftUnit} \; A \; \otimes \; I$$

$$\textbf{RightUnit} \; A \; \otimes \; I$$

***

```
pred Unital(A: set univ, op: univ->univ->univ, I: univ) {
  LeftUnit[A,op,I]
  RightUnit[A,op,I]
}
```

</details>

<details>

<summary><span class="math">\textbf{Zero} \; A \; f \; Z</span></summary>

***

$$\textbf{LeftZero} \; A \; f \; Z$$

$$\textbf{RightZero} \; A \; f \; Z$$

***

```
pred Zero(A: set univ, f: univ->univ->univ, Z: univ) {
  LeftZero[A,f,Z]
  RightZero[A,f,Z]
}
```

</details>
