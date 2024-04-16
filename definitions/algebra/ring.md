# Ring

<details>

<summary><span class="math">\textbf{Ring} \; A \; \otimes \; \oplus \; I</span></summary>

***

$$\textbf{Ringoid} \; A \; \otimes \; \oplus$$

$$\textbf{Group} \; A \; \oplus\; I$$

$$\textbf{Symmetric} \; A \; \oplus$$

$$\textbf{Semigroup} \; A \; \otimes$$

***

```
pred Ring(A: set univ, tms,pls: univ->univ->univ, I: univ){
  Ringoid[A,tms,pls]

  Group[A,pls,I]
  Symmetric[A,pls]

  Semigroup[A,tms]
}
```

</details>
