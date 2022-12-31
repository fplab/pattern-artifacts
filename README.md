# pattern-artifacts
This repo includes artifacts for "Live Pattern Matching with Typed Holes". Specifically,

- Folder `agda-mechanization` contains a proof mechanization that concludes the type safety of the system presented in the paper.
- Folder `incon-sat` contains a minimal implementation of exhaustiveness and redundancy checking based on SAT solving (as described in Sec 4.7.1 of the paper). Instead of type checking a program with holes, it simply focuses on checking consistency between constraints ξ, which resemble patterns p. 

Please see the README in each folder for detailed instructions.
