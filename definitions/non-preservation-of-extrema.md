# Non-Preservation of Extrema

### Generative Effect

<details>

<summary><span class="math">\textbf{HasGenerativeEffect} \; A \; B \; R \; S \; f</span></summary>

***

$$\textbf{MonotoneMap} \; A \; B \; R \; S \; f$$

$$\exists( x,y \in A :: f(\sqcup \{x,y\}) \; \not \cong \; \sqcup \{f.x, f.y \})$$

***

```
pred HasGenerativeEffect(A,B: set univ, R,S,f: univ->univ) {
  MonotoneMap[A,B,R,S,f]
  some x,y: A {
    not Equivalent[
      B,S,
      f[Join[A,R,x+y]],
      Join[B,S,f[x]+f[y]]
    ]
  }
}
```

</details>
