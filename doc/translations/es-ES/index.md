# DifferentialEquations.jl Documentation

This is a package for solving numerically solving differential equations in Julia by Chris Rackauckas. The purpose of this package is to supply efficient Julia implementations of solvers for various differential equations. Equations within the realm of this package include stochastic ordinary differential equations (SODEs or SDEs), stochastic partial differential equations (SPDEs), partial differential equations (with both finite difference and finite element methods), and differential delay equations. For ordinary differential equation solvers, see [ODE.jl](https://github.com/JuliaLang/ODE.jl)

This package is for efficient and parallel implementations of research-level algorithms, many of which are quite recent. These algorithms aim to be optimized for HPC applications, including the use of GPUs, Xeon Phis, and multi-node parallelism. With the easy to use plot/convergence testing algorithms, this package also provides a good sandbox for developing novel numerical schemes.

If at any time you run into documentation that is incomplete/confusing, please contact me via the Gitter channel and I will clear it up!

## Using the Package

To install the package, use the following command inside the Julia REPL:

```julia
Pkg.clone("https://github.com/ChrisRackauckas/DifferentialEquations.jl")
```

To load the package, use the command

```julia
using DifferentialEquations
```

To understand the package in more detail, check out the following tutorials. Example codes for the latest features can be found in <test/>. Due to the fast development speed of the package, it is recommended you checkout the main branch:

    Pkg.checkout("DifferentialEquations")
    

This will keep your local repository up to date with the latest changes.

## Tutorials

The following tutorials will introduce you to the functionality of DifferentialEquations.jl

    {contents}
    Pages = [
        "tutorials/femPoisson.md"
        "tutorials/femHeat.md"
        "tutorials/femStochastic.md"
        ]
    Depth = 2
    

## Manual

    {contents}
    Pages = [
        "man/overview.md"
        "man/problem.md"
        "man/mesh.md"
        "man/solvers.md"
        "man/solution.md"
        "man/plot.md"
        "man/convergence.md"
    ]
    Depth = 2
    

## Internal Documentation

    {contents}
    Pages = [
      "internals/femTools.md"
      "internals/extras.md"
    ]
    Depth = 2