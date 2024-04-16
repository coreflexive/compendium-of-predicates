# Boolean Ring

<details>

<summary><span class="math">\textbf{BooleanRing} \; A \; \otimes \; \oplus \; I \; U</span></summary>

***

$$\textbf{UnitRing} \; A \; \otimes \; \oplus \; I \; U$$

$$\textbf{Idempotent} \; A \; \otimes$$

***

```
pred BooleanRing(A: set univ, tms,pls: univ->univ->univ, I,U: univ) {
  UnitRing[A,tms,pls,I,U]
  Idempotent[A,tms]
}
```

</details>
