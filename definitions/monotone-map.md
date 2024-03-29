# Monotone Map

<details>

<summary><span class="math">\textbf{MonotoneMap} \; A \; B \; R \; S \; f</span></summary>

***

$$\textbf{Preorder} \; A \; R$$

$$\textbf{Preorder} \; B \; S$$

$$\textbf{Function A B} \; f$$

$$\forall( x, y \in A : R.x.y : S.(fx).(fy))$$

***

```
pred MonotoneMap(A,B: set univ, R,S,f: univ->univ) {
  Preorder[A,R]
  Preorder[B,S]
  Function[A,B,f]
  all x,y: A | x->y in R implies f[x]->f[y] in S
}
```

</details>
