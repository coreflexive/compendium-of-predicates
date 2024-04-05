---
description: Families of relations and sets
---

# Indexed Union and Intersection

### Warning

Please pay attention to the **type of the** $$F$$ **parameter** in each definition. &#x20;

The math notation (as is typical) hides the typing and leaves it for the reader to determine on their own.  As such, it can be challenging to know whether you are indexing a family of sets or relations.  Hopefully, this page will help clear that up.

### Indexed Union

#### Family of Relations

<details>

<summary><span class="math">\textbf{Cup} \; I \; A \; B \; F  := \{\;  x \in A, y \in B :  \exists(i \in I :: (x,y) \in F[i]) \;\}</span></summary>

***

$$I, A, B \in \textbf{Set}$$

$$F \in (A \to B)^I$$

***

**Notation.**

1. $$\textbf{Cup} \; I \; A \; B \; F$$ can be written as $$\textbf{Cup} \; I \; F$$ when $$A$$ and $$B$$ are clear from the context.
2. $$\textbf{Cup} \; I \; F$$ is written with symbols as $$\bigcup_{i \in I} F_i$$
3. $$\bigcup_{i \in I} F_i$$ can be written as $$\bigcup( i : i \in I: F.i)$$

***

```
fun Cup(I,A,B: set univ, F: I->A->B) : A->B {
  { x: A, y: B | some i: I | x->y in i.F }
}
```

</details>

#### Family of Sets

<details>

<summary><span class="math">\textbf{Cup} \; I \; A \; F  := \{\;  x \in A :  \exists(i \in I :: x \in F[i]) \;\}</span></summary>

***

$$I, A \in \textbf{Set}$$

$$F \in I \to A$$

***

**Notation.**

1. $$\textbf{Cup} \; I \; A \; F$$ can be written as $$\textbf{Cup} \; I \; F$$ when $$A$$ is clear from the context.
2. $$\textbf{Cup} \; I \; F$$ is written with symbols as $$\bigcup_{i \in I} F_i$$
3. $$\bigcup_{i \in I} F_i$$ can be written as $$\bigcup( i : i \in I: F.i)$$

***

```
fun Cup(I,A: set univ, F: I->A) : set A {
  { x: A | some i: I | x in i.F }
}
```

</details>

### Indexed Intersection

#### Family of Relations

<details>

<summary><span class="math">\textbf{Cap} \; I \; A \; B \; F  := \{\;  x \in A, y \in B :  \forall(i \in I :: (x,y) \in F[i]) \;\}</span></summary>

***

$$I, A, B \in \textbf{Set}$$

$$F \in (A \to B)^I$$

***

**Notation.**

1. $$\textbf{Cap} \; I \; A \; B \; F$$ can be written as $$\textbf{Cap} \; I \; F$$ when $$A$$ and $$B$$ are clear from the context.
2. $$\textbf{Cap} \; I \; F$$ is written with symbols as $$\bigcap_{i \in I} F_i$$
3. $$\bigcap_{i \in I} F_i$$ can be written as $$\bigcap( i : i \in I: F.i)$$

***

```
fun Cap(I,A,B: set univ, F: I->A->B) : A->B {
  {x: A, y: B | all i: I | x->y in i.F }
}
```

</details>

#### Family of Sets

<details>

<summary><span class="math">\textbf{Cap} \; I \; A \; F  := \{\;  x \in A :  \forall(i \in I :: x \in F[i]) \;\}</span></summary>

***

$$I, A \in \textbf{Set}$$

$$F \in I \to A$$

***

**Notation.**

1. $$\textbf{Cap} \; I \; A \; F$$ can be written as $$\textbf{Cap} \; I \; F$$ when $$A$$ is clear from the context.
2. $$\textbf{Cap} \; I \; F$$ is written with symbols as $$\bigcap_{i \in I} F_i$$
3. $$\bigcap_{i \in I} F_i$$ can be written as $$\bigcap( i : i \in I: F.i)$$

***

```
fun Cap(I,A: set univ, F: I->A) : set A {
  { x: A | all i: I | x in i.F }
}
```

</details>
