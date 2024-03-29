# Galois Connection

<details>

<summary><span class="math">\textbf{GaloisConnection} \; A \; B \; R \; S \; f \; g</span></summary>

***

$$\textbf{MonotoneMap} \; A \; B \; R \; S \; f$$

$$\textbf{MonotoneMap} \; B \; A \; S \; R \; g$$

$$\forall(a,b :: R.(f.p).q) \equiv S.p.(g.q))$$

***

```
pred GaloisConnection(A,B: set univ, R,S,f,g: univ->univ) {
  --MonotoneMap[A,B,R,S,f]
  --MonotoneMap[B,A,S,R,g]
  Preorder[A,R]
  Preorder[B,S]
  Function[A,B,f]
  Function[B,A,g]
  all a: A, b: B | f[a]->b in S iff a->g[b] in R
}
```

</details>
