# Boolean Group

<details>

<summary><span class="math">\textbf{BooleanGroup} \; A \; \otimes \; E</span></summary>

***

$$\textbf{Group} \; A \; \otimes \; E$$

$$\textbf{AutoInverse} \; A \; \otimes \; E$$

***

```
pred BooleanGroup(A: set univ, f: univ->univ->univ, E: univ) {
  Group[A,f,E]
  AutoInverse[A,f,E]
}
```

</details>
