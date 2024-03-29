---
description: Among the great enablers of concise reasoning
---

# Indirect Equality and Inclusion

<details>

<summary><span class="math">\forall(x,y :: x = y \equiv \forall(z :: R.z.x \equiv R.z.y))</span></summary>

***

$$\textbf{Reflexive} \; A \; R$$

$$\textbf{Antisymmetric} \; A \; R$$

***

{% code fullWidth="false" %}
```
sig A { R: set A }

check {
  { Reflexive[A,R]
    Antisymmetric[A,R]
  } implies {
    all x,y: A | x = y iff (all z: A | z->x in R iff z->y in R)
  }
} for 10 expect 0
```
{% endcode %}

</details>

<details>

<summary><span class="math">\forall(x,y :: x = y \equiv \forall(z :: R.x.z \equiv R.y.z))</span></summary>

***

$$\textbf{Reflexive} \; A \; R$$

$$\textbf{Antisymmetric} \; A \; R$$

***

```
sig A { R: set A }

check {
  { Reflexive[A,R]
    Antisymmetric[A,R]
  } implies {
    all x,y: A | x = y iff (all z: A | x->z in R iff y->z in R)
  }
} for 10 expect 0
```

</details>

<details>

<summary><span class="math">\forall(x,y :: R.x.y \equiv \forall(z :: R.z.x \Rightarrow R.z.y))</span></summary>

***

$$\textbf{Reflexive} \; A \; R$$

$$\textbf{Transitive} \; A \; R$$

***

```
sig A { R: set A }

check {
  { Reflexive[A,R]
    Transitive[A,R]
  } iff {
    all x,y: A | x->y in R iff (all z: A | z->x in R implies z->y in R)
  }
} for 10 expect 0
```

</details>

<details>

<summary><span class="math">\forall(x,y :: R.x.y \equiv \forall(z :: R.x.z \Leftarrow R.y.z))</span></summary>

***

$$\textbf{Reflexive} \; A \; R$$

$$\textbf{Transitive} \; A \; R$$

***

```
sig A { R: set A }

check {
  { Reflexive[A,R]
    Transitive[A,R]
  } iff {
    all x,y: A | x->y in R iff (all z: A | y->z in R implies x->z in R)
  }
} for 10 expect 0
```

</details>
