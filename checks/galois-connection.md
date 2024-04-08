---
description: Here's where quantifiers obstruct beauty
---

# Galois Connection

### Duality

<details>

<summary><span class="math">\textbf{GaloisConnection} \; A \; B \; R \; S \; f \; g \equiv \textbf{GaloisConnection} \; B \; A \; S^{\circ} \; R^{\circ} \; g \; f</span></summary>

***

```
sig A { R: set A, f: B }

sig B { S: set B, g: A }

check {
  GaloisConnection[A,B,R,S,f,g]
  iff
  GaloisConnection[B,A,~S,~R,g,f]
} for 10 expect 0
```

</details>

### Cancellation

<details>

<summary><span class="math">\forall(a : : a \mathrel{R} (g(f(a)))</span></summary>

***

$$\textbf{GaloisConnection} \; A \; B \; R \; S \; f \; g$$

***

```
sig A { R: set A, f: B }

sig B { S: set B, g: A }

check {
  { GaloisConnection[A,B,R,S,f,g]
  } implies {
    all a: A | a->g[f[a]] in R
  }
} for 10 expect 0
```

</details>

<details>

<summary><span class="math">\forall(b :: (f(g(b)))\mathrel{S} b)</span></summary>

***

$$\textbf{GaloisConnection} \; A \; B \; R \; S \; f \; g$$

***

```
sig A { R: set A, f: B }

sig B { S: set B, g: A }

check {
  { GaloisConnection[A,B,R,S,f,g]
  } implies {
    all b: B | f[g[b]]->b in S
  }
} for 10 expect 0
```

</details>

### Monotonicity

<details>

<summary><span class="math">\textbf{MonotoneMap} \; A \; B \; R \; S \; f</span></summary>

***

$$\textbf{GaloisConnection} \; A \; B \; R \; S \; f \; g$$

***

```
sig A { R: set A, f: B }

sig B { S: set B, g: A }

check {
  { GaloisConnection[A,B,R,S,f,g]
  } implies {
    MonotoneMap[A,B,R,S,f]
  }
} for 10 expect 0
```

</details>

<details>

<summary><span class="math">\textbf{MonotoneMap} \; B \; A \; S \;  R \; g</span></summary>

***

$$\textbf{GaloisConnection} \; A \; B \; R \; S \; f \; g$$

***

```
sig A { R: set A, f: B }

sig B { S: set B, g: A }

check {
  { GaloisConnection[A,B,R,S,f,g]
  } implies {
    MonotoneMap[B,A,S,R,g]
  }
} for 10 expect 0
```

</details>

### Some Equivalences

<details>

<summary>The following are equivalent:</summary>

1. $$R.x.(g.y)$$
2. $$S.(f.x).(f(g.y))$$
3. $$S.(f.x).y$$
4. $$R.(g(f.x)).(g.y)$$

***

$$\textbf{GaloisConnection} \; A \; B \; R \; S \; f \; g$$

***

```
sig A { R: set A, f: B }

sig B { S: set B, g: A }

check {
  { GaloisConnection[A,B,R,S,f,g]
  } implies {
    all x: A, y: B {
      x->g[y] in R implies f[x]->f[g[y]] in S
      f[x]->f[g[y]] in S implies f[x]->y in S
      f[x]->y in S implies g[f[x]]->g[y] in R
      g[f[x]]->g[y] in R implies x->g[y] in R
    }
  }
} for 10 expect 0
```

</details>

<details>

<summary>The following are equivalent:</summary>

1. $$R.(g.x).(g.y)$$
2. $$S.(f(g.x)).(f(g.y))$$
3. $$S.(f(g.x)).(y)$$

for all $$x,y \in B$$.

***

$$\textbf{GaloisConnection} \; A \; B \; R \; S \; f \; g$$

***

```
sig A { R: set A, f: B }

sig B { S: set B, g: A }

check {
  { GaloisConnection[A,B,R,S,f,g]
  } implies {
    all x,y: B {
      g[x]->g[y] in R implies f[g[x]]->f[g[y]] in S
      f[g[x]]->f[g[y]] in S implies f[g[x]]->y in S
      f[g[x]]->y in S implies g[x]->g[y] in R
    }
  }
} for 10 expect 0
```

</details>
