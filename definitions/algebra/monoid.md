# Monoid

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
