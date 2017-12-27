<a id='Convergence-Simulations-1'></a>

# Convergence Simulations

The convergence simulation

<a id='The-ConvergenceSimulation-Type-1'></a>

## The ConvergenceSimulation Type

[#](#DifferentialEquations.ConvergenceSimulation){#DifferentialEquations.ConvergenceSimulation} **`DifferentialEquations.ConvergenceSimulation`** &mdash; *Type*.

ConvergenceSimulation

A type which holds the data from a convergence simulation.

<a id='Related-Functions-1'></a>

## Related Functions

[#](#Base.length-Tuple{DifferentialEquations.ConvergenceSimulation}){#Base.length-Tuple{DifferentialEquations.ConvergenceSimulation}} **`Base.length`** &mdash; *Method*.

length(simres::ConvergenceSimulation)

Returns the number of simultations in the Convergence Simulation

[#](#DifferentialEquations.conv_ests){#DifferentialEquations.conv_ests} **`DifferentialEquations.conv_ests`** &mdash; *Function*.

conv_ests(error::Vector{Number})

Computes the pairwise convergence estimate for a convergence test done by halving/doubling stepsizes via

log2(error[i+1]/error[i])

Returns the mean of the convergence estimates

<a id='Plot-Functions-1'></a>

## Plot Functions