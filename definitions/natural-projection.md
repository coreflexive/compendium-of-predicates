# Natural Projection

<details>

<summary><span class="math">\textbf{NaturalProjection} \; A \; \theta \; \eta</span></summary>

***

$$\textbf{Equivalence} \; A \; \theta$$

$$\textbf{EndoFunction} \; A \; \eta$$

$$\textbf{ker} \; \eta = \theta$$

$$\eta \subseteq \textbf{ker} \; \eta$$

***

**Notation:** $$\eta \in A \to \theta / A$$ denotes $$\textbf{NaturalProjection} \; A \; \theta \; \eta$$

***

```
pred NaturalProjection(A: set univ, Theta,eta: univ->univ) {
  Equivalence[A,Theta]
  EndoFunction[A,eta]
  eta.~eta = Theta
  eta in eta.~eta
}
```

</details>
