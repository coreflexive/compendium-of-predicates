# Complement

<details>

<summary><span class="math">\textbf{Complement} \; A \; B \; R := \top_{A,B} - R</span></summary>

***

$$\textbf{Relation} \; A \; B \; R$$

***

**Notation.**

1. $$\textbf{Complement} \; A \; B \; R$$ can be written $$\textbf{Complement} \; R$$ when $$A$$ and $$B$$are clear from the context.
2. $$\textbf{Complement} \; R$$ can be written symbolically as $$\neg R$$ or $$\overline{R}$$.

***

```
fun Co(A,B: set univ, R: A->B) : A->B {
  (A->B) - R
}
```

</details>
