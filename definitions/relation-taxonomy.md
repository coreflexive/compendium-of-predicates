---
description: Be careful with these
---

# Relation Taxonomy

I present two Alloy translations for each of the definitions on this page.  The first translations are hugely instructive and are taken from J. N. Oliveira's work on relational methods in software engineering.  They present to you in black and white how the various relation classes form a taxonomy.  However, using them in your specifications will likely inflate the state space the analyser must explore.  That's where the second translation comes in.  I took these from Alcino Cunha's writings on Alloy.  He calls it the "Relation Bestiary".  They'll not explode your state space, but they make it harder to see how the taxonomy is formed. You should be fluent in both translations.

<details>

<summary><span class="math">\textbf{Abstraction} \; A \; B \; R</span></summary>

***

$$\textbf{Simple} \; A \; B \; R$$

$$\textbf{Surjective} \; A \; B \; R$$

***

```
pred Abstraction(A,B: set univ, R: univ->univ) {
  Simple[A,B,R]
  Surjective[A,B,R]
}
```

```
pred Abstraction(A,B: set univ, R: univ->univ) {
  R in A some -> lone B
}
```

</details>

<details>

<summary><span class="math">\textbf{Bijection} \;A \; B \; R</span></summary>

***

$$\textbf{Injection} \; A \; B \; R$$

$$\textbf{Surjection} \; A \; B \; R$$

***

```
pred Bijection(A,B: set univ, R: univ->univ) {
  Injection[A,B,R]
  Surjection[A,B,R]
}
```

```
pred Bijection(A,B: set univ, R: univ->univ) {
  R in A one -> one B
}
```

</details>

<details>

<summary><span class="math">\textbf{EndoFunction} \; A \; R</span></summary>

***

$$\textbf{Function} \; A \; A \; R$$

***

```
pred EndoFunction(A: set univ, R: univ->univ) {
  Function[A,A,R]
}
```

</details>

<details>

<summary><span class="math">\textbf{EndoRelation} \; A \; R</span></summary>

***

$$\textbf{Relation} \; A \; A \; R$$

***

```
pred EndoRelation(A: set univ, R: univ->univ) {
  Relation[A,A,R]
}
```

</details>

<details>

<summary><span class="math">\textbf{Entire} \; A \; B \; R</span></summary>

***

$$\textbf{Relation} \; A \; B \; R$$

$$\forall(a \in A : : \exists( b \in B : : R.a.b ))$$

***

```
pred Entire(A,B: set univ, R: univ->univ) {
  Relation[A,B,R]
  all a: A | some b: B | a->b in R
}
```

```
pred Entire(A,B: set univ, R: univ->univ) {
  R in A -> some B
}
```

</details>

<details>

<summary><span class="math">\textbf{Function} \; A \; B \; R</span></summary>

***

$$\textbf{Entire} \; A \; B \; R$$

$$\textbf{Simple} \; A \; B \; R$$

***

```
pred Function(A,B: set univ, R: univ->univ) {
  Entire[A,B,R]
  Simple[A,B,R]
}
```

```
pred Function(A,B: set univ, R: univ->univ) {
  R in A -> one B
}
```

</details>

<details>

<summary><span class="math">\textbf{Injection} \; A \; B \; R</span></summary>

***

$$\textbf{Injective} \; A \; B \; R$$

$$\textbf{Function} \; A \; B \; R$$

***

```
pred Injection(A,B: set univ, R: univ->univ) {
  Injective[A,B,R]
  Function[A,B,R]
}
```

```
pred Injection(A,B: set univ, R: univ->univ) {
  R in A lone -> one B
}
```

</details>

<details>

<summary><span class="math">\textbf{Injective} \; A \; B \; R</span></summary>

***

$$\textbf{Relation} \; A \; B \; R$$

$$\forall( x \in B : : \forall( y,z \in A : R.y.x \wedge R.z.x : y = z ) )$$

***

```
pred Injective(A,B: set univ, R: univ->univ) {
  Relation[A,B,R]
  all x: B | all y,z: A | y->x in R and z->x in R implies y = z
}
```

```
pred Injective(A,B: set univ, R: univ->univ) {
  R in A lone -> B
}
```

</details>

<details>

<summary><span class="math">\textbf{Relation} \; A \; B \; R</span></summary>

***

$$R \subseteq A \times B$$

***

```
pred Relation(A,B: set univ, R: univ->univ) {
  R in A->B
}
```

</details>

<details>

<summary><span class="math">\textbf{Representation} \; A \; B \; R</span></summary>

***

$$\textbf{Injective} \; A \; B \; R$$

$$\textbf{Entire} \; A \; B \; R$$

***

```
pred Representation(A,B: set univ, R: univ->univ) {
  Injective[A,B,R]
  Entire[A,B,R]
}
```

```
pred Representation(A,B: set univ, R: univ->univ) {
  R in A lone -> some B
}
```

</details>

<details>

<summary><span class="math">\textbf{Simple} \; A \; B \; R</span></summary>

***

$$\textbf{Relation} \; A \; B \; R$$

$$\forall( x \in A : : \forall( y,z \in B : R.x.y \wedge R.x.z : y = z ) )$$

***

```
pred Simple(A,B: set univ, R: univ->univ) {
  Relation[A,B,R]
  all x: A | all y,z: B | x->y in R and x->z in R implies y = z
}
```

```
pred Simple(A,B: set univ, R: univ->univ) {
  R in A -> lone B
}
```

</details>

<details>

<summary><span class="math">\textbf{Surjection} \; A \; B \; R</span></summary>

***

$$\textbf{Function} \; A \; B \; R$$

$$\textbf{Surjective} \; A \; B \; R$$

***

```
pred Surjection(A,B: set univ, R: univ->univ) {
  Function[A,B,R]
  Surjective[A,B,R]
}
```

```
pred Surjection(A,B: set univ, R: univ->univ) {
  R in A some -> one B
}
```

</details>

<details>

<summary><span class="math">\textbf{Surjective} \; A \; B \; R</span></summary>

***

$$\textbf{Relation} \; A \; B \; R$$

$$\forall(b \in B : : \exists( a \in A : : R.a.b ))$$

***

```
pred Surjective(A,B: set univ, R: univ->univ) {
  Relation[A,B,R]
  all b: B | some a: A | a->b in R
}
```

```
pred Surjective(A,B: set univ, R: univ->univ) {
  R in A some -> B
}
```

</details>
