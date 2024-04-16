# Unit Ring

<details>

<summary><span class="math">\textbf{UnitRing} \; A \; \otimes \; \oplus \; I \; U</span></summary>

***

$$\textbf{Ring} \; A \; \otimes \; \oplus \; I$$

$$\textbf{RightUnit} \; A \; \otimes \; U$$

***

```
pred UnitRing(A: set univ, tms,pls: univ->univ->univ, I,U: univ){
  Ring[A,tms,pls,I]

  RightUnit[A,tms,U]
}
```

</details>
