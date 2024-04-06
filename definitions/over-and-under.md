---
description: Relation division
---

# Over and Under

### Right division (Over)

<details>

<summary><span class="math">\textbf{Over} \; A \; B \; C \; X \; Y := \{\; a \in A, c \in C : \forall( b\in B : (b,a) \in Y : (b,c) \in X) : (a,c) \;\}</span></summary>

***

$$\textbf{Relation} \; B \; A \; X$$

$$\textbf{Relation} \; B \; C \; Y$$

***

**Notation.**

1. $$\textbf{Over} \; A \; B \; C \; X \; Y$$ can be written $$\textbf{Over} \;  X \; Y$$ when $$A$$, $$B$$ and $$C$$ are clear from the context.
2. $$\textbf{Over} \;  X \; Y$$ is written in symbols as $$X / Y$$.

***

```
fun Over(A,B,C: set univ, X: B->C, Y: B->A) : A->C {
  { a: A, c: C | all b: B | b->a in Y implies b->c in X }
}
```

</details>

### Left division (Under)

<details>

<summary><span class="math">\textbf{Under} \; A \; B \; C \; X \; Y := \{\; c \in C, a \in A : \forall( b\in B : (a,b) \in X : (c,b) \in Y ) : (c,a)\;\}</span></summary>

***

$$\textbf{Relation} \; A \; B \; X$$

$$\textbf{Relation} \; C \; B \; Y$$

***

**Notation.**

1. $$\textbf{Under} \; A \; B \; C \; X \; Y$$can be written $$\textbf{Under} \; X \; Y$$when $$A$$, $$B$$ and $$C$$ are clear from the context.
2. $$\textbf{Under} \;  X \; Y$$ is written in symbols as $$X \backslash Y$$.

***

```
fun Under(A,B,C: set univ, X: A->B, Y: C->B) : C->A {
  { c: C, a: A | all b: B | a->b in X implies c->b in Y }
}
```

</details>
