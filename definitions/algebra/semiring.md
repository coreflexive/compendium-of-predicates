# Semiring

<details>

<summary><span class="math">\textbf{Semiring} \; A \; \otimes \; \oplus</span></summary>

***

$$\textbf{Ringoid} \; A \; \otimes \; \oplus$$

$$\textbf{Semigroup} \; A \; \oplus$$

$$\textbf{Symmetric} \; A \; \oplus$$

$$\textbf{Semigroup} \; A \; \otimes$$

***

```
pred Semiring(A: set univ, tms,pls: univ->univ->univ){
  Ringoid[A,tms,pls]
  
  Semigroup[A,pls]
  Symmetric[A,pls]

  Semigroup[A,tms]
}
```

</details>
