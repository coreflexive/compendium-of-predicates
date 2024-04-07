---
description: Defined to "improve" on the definitions of Bandler and Kohout
---

# De Baets and Kerre Products of Relations

### Sub Product

<details>

<summary><span class="math">\textbf{SubPrd} \; X \; Y \; Z \;R \; S := R \circ S \cap \{ \; x,z : xR \subseteq Sz \; \}</span></summary>

***

$$\textbf{Relation} \; X \; Y \; R$$

$$\textbf{Relation} \; Y \; Z \; S$$

***

**Notation.**

1. $$\textbf{SubPrd} \; X \; Y \; Z \; R \; S$$ can be written $$\textbf{SubPrd} \; R \; S$$ when $$X$$, $$Y$$ and $$Z$$ are clear from the context.
2. $$\textbf{SubPrd} \; R \; S$$ can be written in symbols as $$R \vartriangleleft S$$.

***

```
fun SubPrd(X,Y,Z: set univ, R: X->Y, S: Y->Z) : X->Z {
  R.S & { x: X, z: Z | x.R in S.z }
}
```

</details>

### Super Product

<details>

<summary><span class="math">\textbf{SupPrd} \; X \; Y \; Z \; R \; S := R \circ S \cap \{ \; x,z : xR \supseteq Sz \; \}</span></summary>

***

$$\textbf{Relation} \; X \; Y \; R$$

$$\textbf{Relation} \; Y \; Z \; S$$

***

**Notation.**

1. $$\textbf{SupPrd} \; X \; Y \; Z \; R \; S$$ can be written $$\textbf{SupPrd} \; R \; S$$ when $$X$$, $$Y$$ and $$Z$$ are clear from the context.
2. $$\textbf{SupPrd} \; R \; S$$ can be written in symbols as $$R \vartriangleright S$$.

***

```
fun SupPrd(X,Y,Z: set univ, R: X->Y, S: Y->Z) : X->Z {
  R.S & { x: X, z: Z | S.z in x.R }
}
```

</details>

### Square Product

<details>

<summary><span class="math">\textbf{SqrPrd} \; X \; Y \; Z \; R \; S := R \circ S \cap \{ \; x,z : xR = Sz \; \}</span></summary>

***

$$\textbf{Relation} \; X \; Y \; R$$

$$\textbf{Relation} \; Y \; Z \; S$$

***

**Notation.**

1. $$\textbf{SqrPrd} \; X \; Y \; Z \; R \; S$$ can be written $$\textbf{SqrPrd} \; R \; S$$ when $$X$$, $$Y$$ and $$Z$$ are clear from the context.
2. $$\textbf{SqrPrd} \; R \; S$$ can be written in symbols as $$R \diamond S$$.

***

```
fun SqrPrd(X,Y,Z: set univ, R: X->Y, S: Y->Z) : X->Z {
  R.S & { x: X, z: Z | x.R = S.z }
}
```

</details>
