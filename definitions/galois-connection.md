# Galois Connection

<details>

<summary><span class="math">\textbf{GaloisConnection} \; A \; B \; R \; S \; f \; g</span></summary>

***

$$\textbf{Preorder} \; A \; R$$

$$\textbf{Preorder} \; B \; S$$

$$\textbf{Function} \; A \; B \; f$$

$$\textbf{Function} \; B \; A \; g$$

$$f  ; S = R \; ; ~g^{\circ}$$

***

```
pred GaloisConnection(A,B: set univ, R,S,f,g: univ->univ) {
  Preorder[A,R]
  Preorder[B,S]
  Function[A,B,f]
  Function[B,A,g]
  f.S = R.~g
}
```

</details>
