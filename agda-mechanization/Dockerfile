from haskell:8.4.3
run cabal update
run cabal install alex happy
run cabal install Agda-2.6.2
copy . .
cmd ["agda" , "-v", "2" , "all.agda"]
