# Galois Connection

<details>

<summary><span class="math">\textbf{GaloisConnection} \; A \; B \; R \; S \; f \; g</span></summary>

***

$$\textbf{Preorder} \; A \; R$$

$$\textbf{Preorder} \; B \; S$$

$$\textbf{Function} \; A \; B \; f$$

$$\textbf{Function} \; B \; A \; g$$

$$\forall(a,b :: R.(f.p).q) \equiv S.p.(g.q))$$

***

```
pred GaloisConnection(A,B: set univ, R,S,f,g: univ->univ) {
  Preorder[A,R]
  Preorder[B,S]
  Function[A,B,f]
  Function[B,A,g]
  all a: A, b: B | f[a]->b in S iff a->g[b] in R
}
```

</details>
