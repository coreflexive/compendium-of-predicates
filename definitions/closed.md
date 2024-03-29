# Closed

<details>

<summary><span class="math">\textbf{Closed} \; A \; R \; X</span></summary>

***

$$\textbf{EndoRelation} \; A \; R$$

$$\textbf{PowerSet} \; A \; X$$

$$\forall( x,y \in A : x \in X \wedge R.x.y : y \in X )$$

***

```
pred Closed(A: set univ, R: univ->univ, X: set univ) {
  EndoRelation[A,R]
  X in A
  all x,y: A | x in X and x->y in R implies y in X
}
```

</details>
