# Symmetric Monoidal Preorder

<details>

<summary><span class="math">\textbf{SymmetricMonoidalPreorder} \; X \; R \; \otimes \; I</span></summary>

***

$$\textbf{MonoidalPreorder} \; X \; R \; \otimes \; I$$

$$\textbf{Symmetric} \; X \; \otimes$$

***

```
pred SymmetricMonoidalPreorder(X: set univ, R: univ->univ, op: univ->univ->univ, I: univ) {
  MonoidalPreorder[X,R,op,I]
  Symmetric[X,op]
}
```

</details>

