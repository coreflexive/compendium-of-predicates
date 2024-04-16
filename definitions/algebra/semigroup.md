# Semigroup

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
