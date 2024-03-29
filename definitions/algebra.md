# Algebra

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

<summary><span class="math">\textbf{LeftUnit} \; A \; \otimes \; I</span></summary>

***

$$\textbf{Magma} \; A \; \otimes$$

$$I \in A$$

$$\forall(x \in A :: I \otimes x = x )$$

***

```
pred LeftUnit(A: set univ, op: univ->univ->univ, I: univ) {
  Magma[X,op]
  I in A
  all x: A | op[I,x] = x
}
```

</details>

<details>

<summary><span class="math">\textbf{Monoid} \; A \; \otimes \; I</span></summary>

***

$$\textbf{Semigroup} \; A \; \otimes$$

$$\textbf{Unital} \; A \; \otimes \; I$$

***

```
pred Monoid(A: set univ, op: univ->univ->univ, I: univ) {
  Semigroup[A,op]
  Unital[A,op,I]
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

<summary><span class="math">\textbf{Semigroup} \; A \; \otimes</span></summary>

***

$$\textbf{Magma} \; A \; \otimes$$

$$\forall(x,y,z \in X : (x \otimes y) \otimes z = x \otimes (y \otimes z))$$

***

```
pred Semigroup(A: set univ, op: univ->univ->univ) {
  Magma[A,op]
  all x,y,z: A | op[op[x,y],z] = op[x,op[y,z]]
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
pred Symmetric(X: set univ, op: univ->univ->univ) {
  BinaryOperator[X,op]
  all x,y: X | op[x,y] = op[y,x]
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
