# Extremal Elements

The various extrema must participate in certain relationships predicted by order theory.

<details>

<summary>Absorption</summary>

***

$$\textbf{Join} \; A \; R \; \{  x, (\textbf{Meet} \; A \; R \; \{ x,y\})\} \cong x$$

***

```
sig A { R: set A }

check {
  { Preorder[A,R]
  } implies {
    all x,y: A {
      Equivalent[A,R,Join[A,R,x+Meet[A,R,x+y]],x]
    }
  }
} for 10 expect 0
```

</details>

<details>

<summary>Absorption</summary>

***

$$\textbf{Join} \; A \; R \; \{  x, (\textbf{Meet} \; A \; R \; \{ x,y\})\} \cong x$$

***

```
sig A { R: set A }

check {
  { Preorder[A,R]
  } implies {
    all x,y: A {
      Equivalent[A,R,Meet[A,R,x+Join[A,R,x+y]],x]
    }
  }
} for 10 expect 0
```

</details>

***

<details>

<summary>Join as Meet of Above</summary>

***

$$\textbf{Join} \; A \; R \; S = \textbf{Meet} \; A \; R \; (\textbf{Above} \; A \; R \; S)$$

***

```
sig A { R: set A }

sig S in A {}

check {
  Join[A,R,S] = Meet[A,R,Above[A,R,S]]
} for 10 expect 0
```

</details>

<details>

<summary>Meet as Join of Below</summary>

***

$$\textbf{Meet} \; A \; R \; S = \textbf{Join} \; A \; R \; (\textbf{Below} \; A \; R \; S)$$

***

```
sig A { R: set A }

sig S in A {}

check {
  Meet[A,R,S] = Join[A,R,Below[A,R,S]]
} for 10 expect 0
```

</details>

***

<details>

<summary>Join versus JoinExt</summary>

***

$$\textbf{JoinExt} \; A \; R\;  A \; Y = \textbf{Join} \; A \; R \; Y$$

***

```
sig A { R: set A }

sig Y in A {}

check {
  { some Join[A,R,Y]
  } implies {
    JoinExt[A,R,A,Y] = Join[A,R,Y]
  }
} for 10 expect 0
```

</details>

<details>

<summary>Max versus Join</summary>

***

$$\textbf{Greatest} \; A \; R \; Y \; x  \equiv x \in Y \wedge  \textbf{Join} \; A \; R \; Y \; x$$

***

```
sig A { R: set A }

sig Y in A {}

check {
  { some Greatest[A,R,Y]
  } implies {
    all x: A {
      Greatest[A,R,Y,x]
      iff
      x in Y and Join[A,R,Y,x]
    }
  }
} for 10 expect 0
```

</details>

<details>

<summary>Max vs JoinExt</summary>

***

$$\textbf{Greatest} \; A \; R \; Y = \textbf{JoinExt} \; A \; R \;  Y \; Y$$

***

```
sig A { R: set A }

sig Y in A {}

check {
  Greatest[A,R,Y] = JoinExt[A,R,Y,Y]
} for 10 expect 0
```

</details>

***

<details>

<summary>MeetExt versus Meet</summary>

***

$$\textbf{MeetExt} \; A \; R\;  A \; Y = \textbf{Meet} \; A \; R \; Y$$

***

```
sig A { R: set A }

sig Y {}

check {
  { some Meet[A,R,Y]
  } implies {
    MeetExt[A,R,A,Y] = Meet[A,R,Y]
  }
} for 10 expect 0
```

</details>

<details>

<summary>Min versus Meet</summary>

***

$$\textbf{Least} \; A \; R \; Y \; x  \equiv x \in Y \wedge  \textbf{Meet} \; A \; R \; Y \; x$$

***

```
sig A { R: set A }

sig Y in A {}

check {
  all x: A {
    Least[A,R,Y,x]
    iff
    x in Y and Meet[A,R,Y,x]
  }
} for 10 expect 0
```

</details>

<details>

<summary>Min versus MeetExt</summary>

***

$$\textbf{Least} \; A \; R \; Y = \textbf{MeetExt} \; A \; R \;  Y \; Y$$

***

```
sig A { R: set A }

sig Y in A {}

check {
  { some Least[A,R,Y]
  } implies {
    Least[A,R,Y] = MeetExt[A,R,Y,Y]
  }
} for 10 expect 0
```

</details>

### Meet

<details>

<summary><span class="math">\textbf{Below} \; A \; R \; S \; (\textbf{Meet} \; A \; R \; S)</span></summary>



</details>

<details>

<summary>Empty Range</summary>

***

$$\textbf{Below} \; A \; R \; (\textbf{Meet} \; A \; R \; \empty )  \; y$$

***

```
sig A { R: set A }

check {
  { Preorder[A,R]
  } implies {
    all y: A {
      Below[A,R,Meet[A,R,none],y]
    }
  }
} for 10 expect 0
```

</details>

<details>

<summary>One-point</summary>

***

$$\textbf{Meet} \; A \; R \; \{x\} \cong x$$

***

```
sig A { R: set A }

check {
  { Preorder[A,R]
  } implies {
    all x: A {
      Equivalent[A,R,Meet[A,R,x],x]
    }
  }
} for 10 expect 0
```

</details>

<details>

<summary>Range Disjunction</summary>

***

$$\textbf{Meet} \; A \; R \; (S \cup T) \cong \textbf{Meet} \; A \; R \; ({\textbf{Meet} \; A \; R \; S, \textbf{Meet} \; A \; R \; T})$$

***

```
sig A { R: set A }

sig S, T in A {}

check {
  { Preorder[A,R]
    some Meet[A,R,S+T]
    some Meet[A,R,S]
    some Meet[A,R,T]
  } implies {
    Equivalent[A,R,
      Meet[A,R,S+T],
      Meet[A,R,Meet[A,R,S]+Meet[A,R,T]]
    ]
  }
} for 10 expect 0
```

Alternatively:

```
sig A { R: set A }

sig S, T in A {}

check {
  { AllMeets[A,R]
  } implies {
    Equivalent[A,R,
      Meet[A,R,S+T],
      Meet[A,R,Meet[A,R,S]+Meet[A,R,T]]
    ]
  }
} for 10 expect 0
```

</details>

#### Binary Operator

<details>

<summary>Associativity</summary>

***

$$\textbf{Meet} \; A \; R \; (\{\textbf{Meet} \; A \; R \; \{ x,y \}, z \})  =  \textbf{Meet} \; A \; R \; (\{ x,\textbf{Meet} \; A \; R \; \{ y, z \} \})$$

***

```
sig A { R: set A }

associativity: check {
  { AllMeets[A,R]
  } implies {
    all x,y,z: A {
      Meet[A,R,Meet[A,R,x+y]+z] = Meet[A,R,x+Meet[A,R,y+z]]
    }
  }
} for 10 expect 0
```

</details>

<details>

<summary>Correspondence</summary>

***

$$R.x.y \equiv x = \textbf{Meet} \; A \; R \; \{x, y \}$$

***

```
sig A { R: set A }

check {
  { Preorder[A,R]
  } implies {
    all x,y: A {
      x->y in R
      iff
      Meet[A,R,x+y,x]
    }
  }
} for 10 expect 0
```

</details>

<details>

<summary>Idempotence</summary>

***

$$\textbf{Meet} \; A \; R \; \{x, x\} \cong x$$

***

```
sig A { R: set A }

check {
  { Preorder[A,R]
  } implies {
    all x: A {
      Equivalent[A,R,Meet[A,R,x+x],x]
    }
  }
} for 10 expect 0
```

</details>

<details>

<summary>Symmetry</summary>

***

$$\textbf{Meet} \; A \; R \; \{x, y\} = \textbf{Meet} \; A \; R \; \{y, x\}$$

***

```
sig A { R: set A }

check {
  { Preorder[A,R]
  } implies {
    all x,y: A {
      Meet[A,R,x+y] = Meet[A,R,y+x]
    }
  }
} for 10 expect 0
```

</details>

<details>

<summary></summary>



</details>

### Join

<details>

<summary><span class="math">\textbf{Above} \; A \; R \; S \; (\textbf{Join} \; A \; R \; S)</span></summary>

***

```
sig A { R: set A }

check {
  { Preorder[A,R]
  } implies {
    Above[A,R,S, Join[A,R,S]]
  }
} for 10 expect 0
```

</details>

<details>

<summary>Empty Range</summary>

***

$$\textbf{Above} \; A \; R \; (\textbf{Join} \; A \; R \; \empty )  \; y$$

***

```
sig A { R: set A }

check {
  { Preorder[A,R]
  } implies {
    all y: A {
      Above[A,R,Join[A,R,none],y]
    }
  }
} for 10 expect 0
```

</details>

<details>

<summary>One Point</summary>

***

$$\textbf{Join} \; A \; R \; \{x\} \cong x$$

***

```
sig A { R: set A }

check {
  { Preorder[A,R]
  } implies {
    all x: A {
      Equivalent[A,R,Join[A,R,x],x]
    }
  }
} for 10 expect 0
```

</details>

<details>

<summary>Range Disjunction</summary>

***

$$\textbf{Join} \; A \; R \; (S \cup T) \cong \textbf{Join} \; A \; R \; ({\textbf{Join} \; A \; R \; S, \textbf{Join} \; A \; R \; T})$$

***

```
sig A { R: set A }

sig S, T in A {}

check {
  { Preorder[A,R]
    some Join[A,R,S+T]
    some Join[A,R,S]
    some Join[A,R,T]
  } implies {
    Equivalent[A,R,
      Join[A,R,S+T],
      Join[A,R,Join[A,R,S]+Join[A,R,T]]
    ]
  }
} for 10 expect 0
```

Alternatively:

```
sig A { R: set A }

sig S, T in A {}

check {
  { AllJoins[A,R]
  } implies {
    Equivalent[A,R,
      Join[A,R,S+T],
      Join[A,R,Join[A,R,S]+Join[A,R,T]]
    ]
  }
} for 10 expect 0
```

</details>

#### Binary Operator

<details>

<summary>Associativity</summary>

***

$$\textbf{Join} \; A \; R \; (\{\textbf{Join} \; A \; R \; \{ x,y \}, z \})  =  \textbf{Join} \; A \; R \; (\{ x,\textbf{Join} \; A \; R \; \{ y, z \} \})$$

***

```
sig A { R: set A }

associativity: check {
  { AllJoins[A,R]
  } implies {
    all x,y,z: A {
      Join[A,R,Join[A,R,x+y]+z] = Join[A,R,x+Join[A,R,y+z]]
    }
  }
} for 10 expect 0
```

</details>

<details>

<summary>Correspondence</summary>

***

$$R.x.y \equiv y = \textbf{Join} \; A \; R \; \{x, y \}$$

***

```
sig A { R: set A }

check {
  { Preorder[A,R]
  } implies {
    all x,y: A {
      x->y in R
      iff
      Join[A,R,x+y,y]
    }
  }
} for 10 expect 0
```

</details>

<details>

<summary>Idempotence</summary>

***

$$\textbf{Join} \; A \; R \; \{x, x\} \cong x$$

***

```
sig A { R: set A }

check {
  { Preorder[A,R]
  } implies {
    all x: A {
      Equivalent[A,R,Join[A,R,x+x],x]
    }
  }
} for 10 expect 0
```

</details>

<details>

<summary>Symmetry</summary>

***

$$\textbf{Join} \; A \; R \; \{x, y\} = \textbf{Join} \; A \; R \; \{y, x\}$$

***

```
sig A { R: set A }

check {
  { Preorder[A,R]
  } implies {
    all x,y: A {
      Join[A,R,x+y] = Join[A,R,y+x]
    }
  }
} for 10 expect 0
```

</details>
