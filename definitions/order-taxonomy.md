---
coverY: 0
layout:
  cover:
    visible: false
    size: full
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# Order Taxonomy

<details>

<summary><span class="math">\textbf{Antisymmetric} \; A \; R</span></summary>

***

$$\textbf{EndoRelation} \; A \; R$$

$$\forall ( x,y \in A : R.x.y \wedge R.y.x : x = y )$$

***

```
pred Antisymmetric(A: set univ, R: univ->univ) {
  EndoRelation[A,R]
  all x,y: A | x->y in R and y->x in R implies x = y
}
```

</details>

<details>

<summary><span class="math">\textbf{CoDiscrete} \; A \; R</span></summary>

***

$$\textbf{EndoRelation} \; A \; R$$

$$\forall( x,y \in A :: R.x.y )$$

***

```
pred CoDiscrete(A: set univ, R: univ->univ) {
  EndoRelation[A,R]
  all x,y: A | x->y in R
}
```

</details>

<details>

<summary><span class="math">\textbf{Connected} \; A \; R</span></summary>

***

$$\textbf{EndoRelation} \; A \; R$$

$$\forall ( x,y \in A : : R.x.y \vee R.y.x )$$

***

```
pred Connected(A: set univ, R: univ->univ) {
  EndoRelation[A,R]
  all x,y: A | x->y in R or y->x in R
}
```

</details>

<details>

<summary><span class="math">\textbf{Discrete} \; A \; R</span></summary>

***

$$\textbf{EndoRelation} \; A \; R$$

$$\forall( x,y \in A :: R.x.y \equiv x = y )$$

***

```
pred Discrete(A: set univ, R: univ->univ) {
  EndoRelation[A,R]
  all x,y: A | x->y in R iff x = y
}
```

</details>

<details>

<summary><span class="math">\textbf{Equivalence} \; A \; R</span></summary>

***

$$\textbf{Preorder} \; A \; R$$

$$\textbf{Symmetric} \; A \; R$$

***

```
pred Equivalence(A: set univ, R: univ->univ) {
  Preorder[A,R]
  Symmetric[A,R]
}
```

</details>

<details>

<summary><span class="math">\textbf{PartialOrder} \; A \; R</span></summary>

***

$$\textbf{Preorder} \; A \; R$$

$$\textbf{Antisymmetric} \; A \; R$$

***

```
pred PartialOrder(A: set univ, R: univ->univ) {
  Preorder[A,R]
  Antisymmetric[A,R]
}
```

</details>

<details>

<summary><span class="math">\textbf{Per} \; A \; R</span></summary>

***

$$\textbf{Symmetric} \; A \; R$$

$$\textbf{Transitive} \; A \; R$$

***

```
pred Per(A: set univ, R: univ->univ) {
  Symmetric[A,R]
  Transitive[A,R]
}
```

</details>

<details>

<summary><span class="math">\textbf{Preorder} \; A \; R</span></summary>

***

$$\textbf{Reflexive} \; A \; R$$

$$\textbf{Transitive} \; A \; R$$

***

```
pred Preorder(A: set univ, R: univ->univ) {
  Reflexive[A,R]
  Transitive[A,R]
}
```

</details>

<details>

<summary><span class="math">\textbf{Reflexive} \; A \; R</span></summary>

***

$$\textbf{EndoRelation} \; A \; R$$

$$\forall ( x \in A : : R.x.x )$$

***

```
pred Reflexive(A: set univ, R: univ -> univ) {
  EndoRelation[A,R]
  all x: A | x->x in R
}
```

</details>

<details>

<summary><span class="math">\textbf{Symmetric} \; A \; R</span></summary>

***

$$\textbf{EndoRelation} \; A \; R$$

$$\forall ( x,y \in A : R.x.y : R.y.x )$$

***

```
pred Symmetric(A: set univ, R: univ->univ) {
  EndoRelation[A,R]
  all x,y: A | x->y in R implies y->x in R
}
```

</details>

<details>

<summary><span class="math">\textbf{Tolerance} \; A \; R </span></summary>

***

$$\textbf{Symmetric} \; A \; R$$

$$\textbf{Reflexive} \; A \; R$$

***

```
pred Tolerance(A: set univ, R: univ->univ) {
  Symmetric[A,R]
  Reflexive[A,R]
}
```

</details>

<details>

<summary><span class="math">\textbf{Transitive} \; A \; R</span></summary>

***

$$\textbf{EndoRelation} \; A \; R$$

$$\forall ( x,y,z \in A : R.x.y \wedge R.y.z : R.x.z )$$

***

```
pred Transitive(A: set univ, R: univ -> univ) {
  EndoRelation[A,R]
  all x,y,z: A | x->y in R and y->z in R implies x->z in R
}
```

</details>
