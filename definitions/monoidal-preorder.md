# Monoidal Preorder

<details>

<summary><span class="math">\textbf{MonoidalPreorder} \; X \; R \; \otimes \; I</span></summary>

***

$$\textbf{Preorder} \; X \; R$$

$$\textbf{Monoid} \; X \; \otimes \; I$$

$$\forall (x_1, x_2, y_1, y_2 \in X : x_1 \leq x_2 \wedge y_1 \leq y_2 : x_1 \otimes x_2 \leq y_1 \otimes y_2)$$

***

```
pred MonoidalPreorder(X: set univ, R: univ->univ, op: univ->univ->univ, I: univ) {
  Preorder[X,R]
  Monoid[X,op,I]
  all x1,x2,y1,y2 | x1->x2 in R and y1->y2 in R implies op[x1,x2] -> op[y1,y2] in R
}
```

</details>
