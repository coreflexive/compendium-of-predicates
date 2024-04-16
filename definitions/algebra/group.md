# Group

<details>

<summary><span class="math">\textbf{Group} \; A \; \otimes \; E</span></summary>

***

$$\textbf{Monoid} \; A \; \otimes \; E$$

***

```
pred Group(A: set univ, f: univ->univ->univ, E: univ) {
  Monoid[A,f,E]
  all x: A | some y: A | Inverse[A,f,E,y,x]
}
```

</details>
