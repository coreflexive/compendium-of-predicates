---
description: Closed sets are elegantly described using coreflexives and inclusion
---

# Closed

<details>

<summary><span class="math">\textbf{Closed} \; A \; R \; X</span></summary>

***

$$\textbf{EndoRelation} \; A \; R$$

$$\textbf{PowerSet} \; A \; X$$

$$\Phi_X ; R \subseteq R ; \Phi_X$$

***

```
pred Closed(A: set univ, R: univ->univ, X: set univ) {
  EndoRelation[A,R]
  X in A
  X<:R in R:>X
}
```

</details>
