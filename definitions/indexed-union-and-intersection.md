# Indexed Union and Intersection

### Indexed Union

#### Family of Relations

<details>

<summary><span class="math">\textbf{Cup} \; I \; A \; B \; F  := \{\;  x \in A, y \in B :  \exists(i \in I :: (x,y) \in F[i]) \;\}</span></summary>

***

$$I, A, B \in \textbf{Set}$$

$$F \in (A \to B)^I$$

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

```
fun Cap(I,A: set univ, F: I->A) : set A {
  { x: A | all i: I | x in i.F }
}
```

</details>
