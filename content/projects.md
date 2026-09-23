+++
title = "Projects"
description = "Build tools, scientific Python and graph theory — a few favourites from Andrea Bedini's public work."
template = "projects.html"

[extra]
eyebrow = "// projects"
headline = "Things I've built, out in the open."
intro = "Build tooling from the day job, and older things from before it: data tools in Python and a Tutte polynomial solver in C++. A few favourites — the rest live on GitHub."

[[extra.tags]]
label = "Build systems"

[[extra.tags]]
label = "Scientific computing"

[[extra.tags]]
label = "Graph theory"

[[extra.projects]]
name = "foliage"
owner = "input-output-hk"
lang = "Haskell"
desc = "A tool to create custom Haskell package repositories — fully reproducible, from a handful of declarative files."
href = "https://github.com/input-output-hk/foliage"

[[extra.projects]]
name = "ghc"
owner = "stable-haskell"
lang = "Haskell"
meta = "2024 — now · co-lead"
desc = "An initiative to make Haskell more accessible and reliable. I replaced GHC’s ad-hoc build system with Cabal, and extended Cabal to support cross-compilation."
href = "https://github.com/stable-haskell/ghc"

[[extra.projects]]
name = "cabal-solver-plan"
owner = "andreabedini"
lang = "Haskell"
desc = "Run the cabal-install dependency solver with precisely specified inputs — useful for debugging and reproducing build plans."
href = "https://github.com/andreabedini/cabal-solver-plan"

[[extra.projects]]
name = "PyTables"
owner = "PyTables"
lang = "Python"
meta = "2013 — 16 · governance team"
desc = "A Python package for managing extremely large amounts of data. I published releases, added extended-precision support, and wrote the low-level sorting code, the test suite and the release automation."
href = "https://github.com/PyTables/PyTables"

[[extra.projects]]
name = "ipython"
owner = "ipython"
lang = "Python"
meta = "2013 · IPython 1.0"
desc = "An extension to embed matplotlib output directly inside a notebook cell, back when IPython was not yet Jupyter."
href = "https://github.com/ipython/ipython"

[[extra.projects]]
name = "tutte"
owner = "andreabedini"
lang = "C++"
meta = "Zenodo · 10.5281/zenodo.15941"
desc = "Compute the Tutte polynomial of a graph by marrying the transfer matrix with tree-decomposition — faster than anything else at the time."
href = "https://github.com/andreabedini/tutte"
+++
