# Below

<details>

<summary>One point</summary>

***

$$\textbf{Below} \; A \; R \; \{ x \}\; y  \equiv R.y.x$$

***

```
sig A { R: set A }

check {
  { Preorder[A,R]
  } implies {
    all x,y: A {
      Below[A,R,x,y]
      iff
      y->x in R
    }
  }
} for 10 expect 0
```

</details>

<details>

<summary>Range Disjunction</summary>

***

$$\textbf{Below} \; A \; R \; (S \cup T) \; y \equiv \textbf{Below} \; A \; R \; S  \; y \wedge \textbf{Below} \; A \; R \; T \; y$$

***

```
sig A { R: set A }

sig S,T in A {}

check {
  { Preorder[A,R]
  } implies {
    all y: A {
      Below[A,R,S+T,y]
      iff
      Below[A,R,S,y] and Below[A,R,T,y]
    }
  }
} for 10 expect 0
```

</details>

<details>

<summary>Empty Range</summary>

***

$$\textbf{Below} \; A \; R \; \empty \; y \equiv  \textbf{true}$$

***

```
sig A { R: set A }

check {
  { Preorder[A,R]
  } implies {
    all y: A {
      Below[A,R,none,y]
    }
  }
} for 10 expect 0
```

</details>
