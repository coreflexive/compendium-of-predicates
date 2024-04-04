---
description: Better known as Vectors and Points
---

# Row Constant Relations

<details>

<summary><span class="math">\textbf{RowConstant} \; A \; B \; R</span></summary>

***

$$\textbf{Relation} \; A \; B \; R$$

***

```
pred RowConstant(A,B,C: set univ, R: univ->univ) {
  Relation[A,B,R]
  R = R.(B->C)
}
```

</details>

<details>

<summary><span class="math">\textbf{Point} \; A \; B \; R</span></summary>

***

$$\textbf{RowConstant} \; A \; B \; R$$

$$\textbf{Injective} \; A \; B \; R$$

$$\textbf{Surjective} \; A \; B \; R$$

***

```
pred Point(A,B: set univ, R: univ->univ) {
  RowConstant[A,B,B,R]
  Injective[A,B,R]
  Surjective[A,B,R]
}
```

</details>
