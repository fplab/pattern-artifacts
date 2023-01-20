# A Solver-based implementation of `Incon`

A simple solver-based inconsistency checker for constraint language described in the paper.

# Setup

Assuming you have [opam](https://opam.ocaml.org/doc/Install.html) installed, `$ ./build` creates a new opam switch, installs necessary dependencies, builds the project, and runs inline tests.  You may find the tests at the bottom of [incon.ml](src/incon.ml).

# File Structure in `src`

* `constraint.ml` defines the constraint language along with three operations on constraints, `dual`, `truify`, and `falsify`. They are all described in the main paper.

* `solver.ml` offers a dozen of helper function and an interface for satisfiability checking in `Z3`.

* `incon.ml` describes a decision procedure to check inconsistency of
constraints, equivalent to `incon` judgment in the paper.  Function
`trans` turns a constraint (that encodes exhaustiveness checking or
redundancy checking) into a logical formula.  As a result, checking satisfiability of the formula is equivalent to checking the consistency of the constraint.

# Try it yourself!

Launch ocaml top-level.
```bash
dune utop src
```

Within the top-level, bring the functions into scope with `open Incon;;`, and you may check exhaustiveness and redundancy as follows.

- `Inl x` and `Inr ??` may be exhaustive.

```ocaml
is_exhaustive (disjunct [ Inl Truth; Inr Unknown ]);;
```

- `2 | ?? ` may not be redundant with respect to `2 | 3`.

```ocaml
is_redundant (disjunct [ Num 2; Unknown ]) (disjunct [ Num 2; Num 3 ]);;
```
