# Boolean Group

### Symmetric

<details>

<summary><span class="math">\textbf{Symmetric} \; A \; \otimes</span></summary>

***

$$\textbf{BooleanGroup} \; A \; \otimes \; E$$

***

```
sig A {
  , f: A->A
}

sig E in A {}

check {
  { BooleanGroup[A,f,E]
  } implies {
    Symmetric[A,f]
  }
} for 10
```

</details>
