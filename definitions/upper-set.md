# Upper Set

<details>

<summary><span class="math">\textbf{UpperSet} \; A \; R \; X</span></summary>

***

$$\textbf{Preorder} \; A \; R$$

$$\textbf{Closed} \; A \; R \; X$$

***

```
pred UpperSet(A: set univ, R: univ->univ, X: set univ) {
  Preorder[A,R]
  Closed[A,R,X]
}
```

</details>

<details>

<summary><span class="math">\textbf{AtMost} \; B \; R \; U \; H</span></summary>

***

$$\textbf{UpperSet} \; B \; R \; U$$

$$\textbf{UpperSet} \; B \; R \; H$$

$$\textbf{Includes} \; U \; H$$

***

```
pred AtMost(B: set univ, R: univ -> univ, U: set univ, H: set univ) {
  UpperSet[B,R,U]
  UpperSet[B,R,H]
  U in H
}
```

</details>
