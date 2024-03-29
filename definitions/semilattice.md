# Semilattice

### Order Theoretic Definition

<details>

<summary><span class="math">\textbf{AllJoins} \; A \; R</span></summary>

***

$$\forall(x,y \in A :: \exists(z \in A:: \textbf{Join} \; A \; R \; \{x, y\} \; z))$$

***

```
pred AllJoins(A: set univ, R: univ -> univ) {
  all x,y: A | some z: A | Join[A,R,x+y,z]
}
```

</details>

<details>

<summary><span class="math">\textbf{AllMeets} \; A \; R</span></summary>

***

$$\forall(x,y \in A :: \exists(z :: \textbf{Meet} \; A \; R \; \{x,y\} \; z))$$

***

```
pred AllMeets(A: set univ, R: univ->univ) {
  all x,y: A | some z: A | Meet[A,R,x+y,z]
}
```

</details>

<details>

<summary><span class="math">\textbf{JoinSemilattice} \; A \; R</span></summary>

***

$$\textbf{PartialOrder} \; A \; R$$

$$\textbf{AllJoins} \; A \; R$$

***

```
pred JoinSemilattice(A: set univ, R: univ -> univ) {
  PartialOrder[A,R]
  AllJoins[A,R]
}
```

</details>

<details>

<summary><span class="math">\textbf{Lattice} \; A \; R</span></summary>

***

$$\textbf{JoinSemilattice} \; A \; R$$

$$\textbf{MeetSemilattice} \; A \; R$$

***

```
pred Lattice(A: set univ, R: univ->univ) {
  JoinSemilattice[A,R]
  MeetSemilattice[A,R]
}
```

</details>

<details>

<summary><span class="math">\textbf{MeetSemilattice} \; A \; R</span></summary>

***

$$\textbf{PartialOrder} \; A \; R$$

$$\textbf{AllMeets} \; A \; R$$

***

```
pred MeetSemilattice(A: set univ, R: univ -> univ) {
  PartialOrder[A,R]
  AllMeets[A,R]
}
```

</details>

### Algebraic Definition

<details>

<summary><span class="math">\textbf{Absorbs} \; A \; \otimes \; \oplus </span></summary>

***

$$\textbf{Magma} \; A \; \otimes$$

$$\textbf{Magma} \; A \; \oplus$$

$$\forall( x,y \in A ::  x \otimes (x \oplus y) = x)$$

***

```
pred Absorbs(A: set univ, f,g: univ->univ->univ) {
  Magma[A,f]
  Magma[A,g]
  all: x,y: A | f[x,g[x,y]] = x
}
```

</details>

<details>

<summary><span class="math">\textbf{Lattice} \; A \; \otimes \; \oplus</span></summary>

***

$$\textbf{Semilattice} \; A \; \otimes$$

$$\textbf{Semilattice} \; A \; \oplus$$

$$\textbf{Absorbs} \; A \; \otimes \; \oplus$$

$$\textbf{Absorbs} \; A \; \oplus \; \otimes$$

***

```
pred Lattice(A: set univ, cap, cup: univ->univ->univ) {
  Semilattice[A,cap]
  Semilattice[A,cup]
  Absorbs[A,cap,cup]
  Absorbs[A,cup,cap]
}
```

</details>

<details>

<summary><span class="math">\textbf{Semilattice} \; A \; \otimes </span></summary>

***

$$\textbf{Idempotent} \; A \; \otimes$$

$$\textbf{Symmetric} \; A \;  \otimes$$

$$\textbf{Semigroup} \; A \; \otimes$$

***

```
pred Semilattice(A: set univ, op: univ->univ->univ) {
  Idempotent[A,op]
  Symmetric[A,op]
  Semigroup[A,op]
}
```

</details>
