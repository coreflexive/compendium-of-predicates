# Preservation of Extrema

### Meet Preserving

<details>

<summary><span class="math">\textbf{MeetPreserving} \; A \; B \; R \; S \; f</span></summary>

***

$$\textbf{MonotoneMap} \; A \; B \; R \; S \; f$$

$$\forall( x,y \in A :: f(\sqcap \{x,y\}) \; \cong \; \sqcap \{f.x, f.y \})$$

***

```
pred MeetPreserving(A,B: set univ, R,S,f: univ->univ) {
  MonotoneMap[A,B,R,S,f]
  all x,y: A {
    Equivalent[
      B,S,
      f[Meet[A,R,x+y]],
      Meet[B,S,f[x]+f[y]]
    ]
  }
}
```

</details>

### Join Preserving

<details>

<summary><span class="math">\textbf{JoinPreserving} \; A \; B \; R \; S \; f</span></summary>

***

$$\textbf{MonotoneMap} \; A \; B \; R \; S \; f$$

$$\forall( x,y \in A :: f(\sqcup \{x,y\}) \; \cong \; \sqcup \{f.x, f.y \})$$

***

```
pred JoinPreserving(A,B: set univ, R,S,f: univ->univ) {
  MonotoneMap[A,B,R,S,f]
  all x,y: A {
    Equivalent[
      B,S,
      f[Join[A,R,x+y]],
      Join[B,S,f[x]+f[y]]
    ]
  }
}
```

</details>
