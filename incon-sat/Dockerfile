from ocaml/opam:debian-10-ocaml-4.12
run sudo apt install -y python3 libgmp-dev
run opam install --yes dune utop ocamlformat z3 ppx_inline_test
copy . .
env PATH=/home/opam/.opam/4.12/bin:$PATH
run dune build @runtest
cmd dune utop src


