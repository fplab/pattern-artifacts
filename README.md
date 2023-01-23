# pattern-artifacts
This repo includes artifacts for "Live Pattern Matching with Typed Holes". Specifically,

- Folder `agda-mechanization` contains a proof mechanization that concludes the type safety of the system presented in the paper.
- Folder `incon-sat` contains a minimal implementation of exhaustiveness and redundancy checking based on SAT solving (as described in Sec 4.7.1 of the paper). Instead of type checking a program with holes, it simply focuses on checking consistency between constraints ξ, which resemble patterns p. 

## Kick The Tires

- Assuming `Agda 2.6.2`(other version might also work) is installed, run `$ agda all.agda` under `agda-mechanization` will check the proof.

- Assuming `opam` is installed, run `$ ./build` under `incon-sat` will build the project and check the tests.

### Docker
  Alternatively, you may use [Docker](https://docs.docker.com/get-docker/). Note: building dockers may take a while.

- Build and run Agda mechanization
  ```
  $ docker build -t pattern-agda agda-mechanization
  $ docker run pattern-agda # will check proof
  ```
- Build and run Exhaustiveness and Redundancy Checker
  ```
  $ docker build -t pattern-incon agda-mechanization
  $ docker run -it pattern-incon # will invoke OCaml toplevel
  ``` 

Please see the README in each folder for detailed instructions.
