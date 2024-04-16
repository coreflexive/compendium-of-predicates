# 😅 An Example

I wanted to see what a generative effect looked like.  After much searching, copying, and pasting, I created this Alloy specification:

```
sig A {
  , R: set A
  , f: B
}

sig B { S: set B }

run {
  HasGenerativeEffect[A,B,R,S,f]
}

pred HasGenerativeEffect(A,B: set univ, R,S,f: univ->univ) {
  MonotoneMap[A,B,R,S,f]
  some x,y: A {
    not Equivalent[
      B,S,
      f[Join[A,R,x+y]],
      Join[B,S,f[x]+f[y]]
    ]
  }
}

pred MonotoneMap(A,B: set univ, R,S,f: univ->univ) {
  Preorder[A,R]
  Preorder[B,S]
  Function[A,B,f]
  all x,y: A | x->y in R implies f[x]->f[y] in S
}

fun Join(A: set univ, R: univ->univ, S: set univ) : set univ {
  { x: univ | Join[A,R,S,x] }
}

pred Join(A: set univ, R: univ->univ, S: set univ, x: univ) {
  Above[A,R,S,x]
  all y: univ | Above[A,R,S,y] implies x->y in R
}

pred Equivalent(A: set univ, R: univ->univ, x,y: univ) {
  Preorder[A,R]
  x in A
  y in A
  x->y in R and y->x in R
}

pred Preorder(A: set univ, R: univ->univ) {
  Reflexive[A,R]
  Transitive[A,R]
}

pred Function(A,B: set univ, R: univ->univ) {
  Entire[A,B,R]
  Simple[A,B,R]
}

pred Above(A: set univ, R: univ->univ, S: set univ, y: univ) {
  Preorder[A,R]
  S in A
  y in A
  all s: univ | s in S implies s->y in R 
}

pred Reflexive(A: set univ, R: univ -> univ) {
  EndoRelation[A,R]
  all x: A | x->x in R
}

pred Transitive(A: set univ, R: univ -> univ) {
  EndoRelation[A,R]
  all x,y,z: A | x->y in R and y->z in R implies x->z in R
}

pred Entire(A,B: set univ, R: univ->univ) {
  Relation[A,B,R]
  all a: A | some b: B | a->b in R
}

pred Simple(A,B: set univ, R: univ->univ) {
  Relation[A,B,R]
  all x: A | all y,z: B | x->y in R and x->z in R implies y = z
}

pred EndoRelation(A: set univ, R: univ->univ) {
  Relation[A,A,R]
}

pred Relation(A,B: set univ, R: univ->univ) {
  R in A->B
}

pred AllJoins(A: set univ, R: univ -> univ) {
  all x,y: A | some z: A | Join[A,R,x+y,z]
}
```

