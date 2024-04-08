# Monotone Map

<details>

<summary><span class="math">\textbf{MonotoneMap} \; A \; B \; R \; S \; f</span></summary>

***

$$\textbf{Preorder} \; A \; R$$

$$\textbf{Preorder} \; B \; S$$

$$\textbf{Function A B} \; f$$

$$R;f \subseteq f ; S$$

***

```
pred MonotoneMap(A,B: set univ, R,S,f: univ->univ) {
  Preorder[A,R]
  Preorder[B,S]
  Function[A,B,f]
  R.f in f.S
}
```

</details>
