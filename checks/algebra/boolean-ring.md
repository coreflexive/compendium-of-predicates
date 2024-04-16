# Boolean Ring

### Has Zero Divisors

<details>

<summary><span class="math">\exists(p,q \in A - \text{Zero}: p \neq q : p \otimes q = \text{Zero})</span></summary>

***

$$\textbf{BooleanRing} \; A \; \otimes \; \oplus \; \text{Zero} \; \text{One}$$

$$#A > 2$$

***

```
sig A {
  , tms: A->A
  , pls: A->A
}

sig Zero, One in A {}

has_zero_divisors: check {
  { BooleanRing[A,tms,pls,Zero,One]
    #A > 2
  } implies {
    some disj p,q: A-Zero {
      tms[p,q] = Zero
    }
  }
} for 10
```

</details>
