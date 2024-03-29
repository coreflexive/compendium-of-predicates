---
description: There is a price to pay for writing independent predicates
---

# 🎙️ A few words about the checks

It is important to remember that a finite scope may not be sufficient to determine the validity of an assertion. When creating a model of a software system, expanding the scope may increase our confidence in the validity of an assertion. However, Alloy is not capable of _confirming_ the validity of an assertion. This becomes a more significant issue when using Alloy to encode mathematics, as in this library.

It is important to remember that Alloy is not a theorem prover. The predicates can run without declaring signatures and facts, which is convenient for quickly visualising the meaning of predicates. However, writing Alloy this way requires us to be more careful when writing our checks. We must provide the context for a check as an antecedent. Usually, the context is supplied by the declared signatures and facts. We may check meaningless assertions if we overlook an essential constraint upon which a predicate relies. Nevertheless, this is a small price for the flexibility a library of independent predicates provides us.

My approach is transcribing a mathematical definition into an Alloy predicate and writing checks based on the corresponding theory.  This is an activity that takes much time and mental effort.  It is an ongoing effort.

You can be sure of this: the only checks I include here are those that run successfully.
