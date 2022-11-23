# Miscellaneous Math

* Metamath - proof explorer
  Metamath is like math programming.
  You can write your math theory and prove it (cascadingly) from the axioms.
  Lemma can be proven until axiom as well.

* Types of numbers

| Symbol | Name | Description | Example
|--------|------|-------------|--------
| N | Natural number | positive number | ```1, 2, 3, 4, 5, ...```
| Z | Integer number | whole number, including negative | ```..., -3, -2, -1, 0, 1, 2, 3, ...```
| Q | Rational number | number expressible as `p/q` where p and q is integer (NOT the precise definition) | ```1/2, 3/4, 227/356, ...```
| A | Algebraic number | number that represents solution to polynomials, may include Complex number | ```sqrt(2), sqrt(3), ...```
| R | Real number | all numbers in real line, rational and irrational | `0.2345..., pi, e, 0.25`
| C | Complex number | numbers in the form of `p + iq` where p and q is integer and i is square root of -1 | `2 + 3i`

---
# Cantor and infinity

There are different kind of infinity. Infinity is NOT a number, it is a kind of saying "this things goes on forever". Some infinity is bigger that the others.

(Not precise definition!)
Countably infinite - infinite, but we can count/enumerate it
Uncountably infinite - infinite and we couldn't enumerate it

Example
| Number | Infinite?
|--------|-------
| N - Natural number | countably infinite: `1, 2, 3, 4, ... (and this goes on forever)`
| Z - Integer number | countably infinite: `0, 1, -1, 2, -2, 3, -3, ... (and this goes on forever)`
| Q - Rational number | countably infinite: make row & column with Z and iterate it
| R - Real number | by Cantor's diagonalization, it is uncountably infinite


---
# Quantum and Matrix

* In quantum formalism with matrix, a state |0> is a definition, e.g.
  |0> is different depending on which quantum phenomena a quantum computer is using, whether it is an electron spin, ... (what are other quantum phenomena human exploits to make quantum computing?)

# Algebraic Structures

Algebraic structures are a set with an operations, (S, op1, op2, ...) that satisfies some axioms.

| Structure | Operation | Closure | Associative | Identity | Inverse | Commutative |
|-----------|-----------|---|---|---|---|---|
| Set              | N.A.  |   |   |   |   |   |
| Group            | +     | v | v | v | v |   |
| Abelian Group    | +     | v | v | v | v | v |
| Ring             | +<br>* (distributive over +) | v<br>v | v<br>v | v<br>v | v<br>- | v<br>- |
| Field            | +<br>* (distributive over +) | v<br>v | v<br>v | v<br>v | v<br>v | v<br>v |

# Foundations of Mathematics

## Propostional Calculus

System P2:
| Name | Definition | Comment |
|------|-------|---------|
| Axiom of Simplification | P -> (Q -> P) | Tautology, regardless the truth of P and Q, this axiom will always produce True |
| Axiom of Distribution   | (P -> (Q -> R))  ->  ((P -> Q) -> (P -> R)) | 
| Axiom of Contraposition | (not P -> not Q)  ->  (P -> Q) |
| Rule: Modus Ponen       | P, P -> Q |- Q | 

## Predicate Calculus

## Set Theory

| Name | Definition | Comment |
|------|------------|-----------|
| Axiom of Extensionality |  | Two sets are the same if they have the same elements
| Axiom of Replacement |  | 
| Axiom of Union | | 
| Axiom of Power Set | | 
| Axiom of Regularity | | 
| Axiom of Infinity | | 
| Axiom of Choice | | 