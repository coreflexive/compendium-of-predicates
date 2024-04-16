# Ringoid

<details>

<summary><span class="math">\textbf{Ringoid} \; A \; \otimes \; \oplus</span></summary>

***

$$\textbf{Distl} \; A \; \otimes \; \oplus$$

$$\textbf{Distr} \; A \; \otimes \; \oplus$$

***

```
pred Ringoid(A: set univ, tms,pls: univ->univ->univ){
  Distl[A,tms,pls]
  Distr[A,tms,pls]
}
```

</details>

<details>

<summary><span class="math">\textbf{Distl} \; A \; \text{f} \; \text{g}</span></summary>

***

$$\textbf{Magma} \; A \; f$$

$$\textbf{Magma} \; A \; g$$

$$\forall(x,y,z \in A :: f(x,g(y,z)) = g(f(x,y),f(x,z))$$

***

```
pred Distl(A: set univ, f,g: univ->univ->univ) {
  Magma[A,f]
  Magma[A,g]

  all x,y,z: A {
    f[x,g[y,z]] = g[f[x,y],f[x,z]]
  }
}
```

</details>

<details>

<summary><span class="math">\textbf{Distr} \; A \; \text{f} \; \text{g}</span></summary>

***

$$\textbf{Magma} \; A \; f$$

$$\textbf{Magma} \; A \; g$$

$$\forall(x,y,z \in A :: f(g(y,z),x) = g(f(y,x),f(z,x))$$

***

```
pred Distr(A: set univ, f,g: univ->univ->univ) {
  Magma[A,f]
  Magma[A,g]

  all x,y,z: A {
    f[g[y,z],x] = g[f[y,x],f[z,x]]
  }
}
```

</details>
