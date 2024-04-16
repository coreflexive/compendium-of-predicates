# Ring

### Zero

<details>

<summary><span class="math">\forall(x \in A :: z \otimes x = z)</span></summary>

***

$$\textbf{Ring} \; A \; \otimes \; \oplus \; z$$

***

```
sig A {
  , tms: A->A
  , pls: A->A
}

sig Zero in A {}

zero: check {
  { Ring[A,tms,pls,Zero]
  } implies {
    Zero[A,tms,Zero]
  }
} for 7
```

</details>
