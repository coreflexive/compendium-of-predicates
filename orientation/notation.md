---
description: Where I explain why I write the way I do
---

# ✒️ Notation

Mathematical notation is elegant, but only because context and conventions allow us to hide references to dependencies. When writing Alloy, we do not have such a luxury. These pages are concerned with presenting definitions of mathematical objects in a manner which is easy to translate into Alloy syntax. So, don't expect traditional mathematical notation to be the first thing you see when you navigate these pages. Instead, you'll see familiar names followed by parameter lists that are perhaps longer than you are used to. For example, within the pages describing **Extremal Elements**, you'll see expandable content like this:

<details>

<summary><span class="math">\textbf{Meet} \; A \; R \; S \; x</span></summary>

***

$$\textbf{Below} \;A \; R \; S \; x$$

$$\forall(y : \textbf{Below} \;A \; R \; S \; y : R.y.x)$$

***

**Notation.**

1. $$\textbf{Meet} \; S \; x$$ abbreviates $$\textbf{Meet} \; A \; R \; S \; x$$ when $$A$$ and $$R$$​ are clear from the context.
2. $$\textbf{Meet} \; S \; x$$ is abbreviated by $$x = \sqcap \; S$$

***

```
pred Meet(A: set univ, R: univ->univ, S: set univ, x: univ) {
  Below[A,R,S,x]
  all y: univ | Below[A,R,S,y] implies y->x in R
}
```

</details>

The first section in that container tells us the names of a predicate and its parameters.  This one is called $$\textbf{Meet}$$, which has four parameters $$A$$, $$R$$, $$S$$ and $$x$$. The next section tells us the conditions that the parameters must meet for the predicate to be evaluated as true.  There is a traditional math notation for this predicate:

$$
x = \sqcap \; S
$$

, which is read: $$x$$ is the meet of the set $$S$$ with respect to the preorder $$R$$ on the set $$A$$. That being such a mouthful is the motivation for not mentioning $$A$$ and $$R$$ in the notation. This definition has a **Notation** section where I explain how the translation works. Finally, I show how to translate the predicate into Alloy syntax

> This way of presenting definitions was inspired by Ralph Back's _Structured Derivations_. I highly recommend you check out his books: "Teaching Mathematics in the Digital Age" and "Refinement Calculus: A Systematic Introduction".

This is somewhat unusual compared to the Alloy specifications in the wild. Typically, the context I declare as predicate parameters is declared using signatures instead. Supplying context via predicate parameters means those parameter lists can grow long. For example, the predicate I wrote defining a **Galois Connection** has six parameters! If that makes you uncomfortable, please know that those lengthy lists have a definite advantage: they are honest. They are also reminiscent of how mathematics is formalised in type theories like those presented in Nederpelt and Geuver's book "Type Theory and Formal Proof" or Bill Farmer's "Alonzo". It's not just a quirk.

There is one big problem with that Alloy above, though. Where have I defined the predicate called **Below**? It's on another page, which will be defined according to the same structure as above: predicate and parameter names, conditions and Alloy.

> GitBook's search feature will help you discover exactly where a definition lives.

Also, where are the types of parameters constrained?  Dig deep enough into the definitions, and you'll find out!

You'll likely hate how I've separated the predicates from their dependencies.  But please give it a chance!  I wouldn't say I liked it too, at first.  All the toing and froing I've done copying and pasting predicates into my models has had the wonderful side-effect of burning these definitions into my memory.\
