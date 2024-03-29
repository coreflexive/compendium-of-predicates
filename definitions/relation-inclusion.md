# Relation Inclusion

<details>

<summary><span class="math">\textbf{Includes} \; A \; B \; R \; S</span></summary>

***

$$\textbf{Relation} \; A \; B \; R$$

$$\textbf{Relation} \; A \; B \; S$$

$$\forall (x \in A : \forall (y \in B : R.x.y : S.x.y))$$

***

**Notation.**

1. $$\textbf{Includes} \; A \; B \; R \; S$$ can be abbreviated by $$\textbf{Includes} \; R \; S$$when $$A$$ and $$B$$ are clear from the context.
2. $$\textbf{Includes} \; R \; S$$ can be written $$R \subseteq S$$.

***

```
pred Includes(A,B: set univ, R,S: univ->univ) {
  Relation[A,B,R]
  Relation[A,B,S]
  R in S
}
```

</details>

<details>

<summary><span class="math">\textbf{Within} \; A \; B \; R \; S</span></summary>

***

$$\textbf{Includes} \; A \; B \; S \; R$$

***

**Notation.**

1. $$\textbf{Within} \; A \; B \; R \; S$$ can be abbreviated by $$\textbf{Within} \; R \; S$$when $$A$$ and $$B$$ are clear from the context.
2. $$\textbf{Within} \; R \; S$$ can be written $$R \supseteq S$$.

***

```
pred Within(A,B: set univ, R,S: univ->univ) {
  Includes[A,B,S,R]
}
```

</details>
