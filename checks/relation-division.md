---
description: Comparing left and right divisions
---

# Relation Division

### Under versus Over

<details>

<summary><span class="math">X \backslash Y = (Y^\circ / X^\circ)^\circ</span></summary>

***

```
sig A { X: set B }

sig B {}

sig C { Y: set B }

check {
  Under[A,B,C,X,Y] = ~(Over[A,B,C,~Y,~X])
} for 10
```

</details>

### Composition versus Under

<details>

<summary><span class="math">X \circ Z \subseteq Y \equiv Z \subseteq X \backslash Y</span></summary>

***

```
sig A { X: set B }

sig B {}

sig C { Y: set B, Z: set A}

check {
  Z.X in Y iff Z in Under[A,B,C,X,Y]
} for 10
```

</details>

### Composition versus Over

<details>

<summary><span class="math">Z \circ X \subseteq  Y \equiv Z \subseteq Y / X</span></summary>

***

```
sig A { Z: set C}

sig B { X: set A, Y: set C}

sig C {}

check {
  X.Z in Y iff Z in Over[A,B,C,Y,X]
} for 10
```

</details>
