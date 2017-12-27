<a id='Internal-Finite-Element-Tools-1'></a>

# Internal Finite Element Tools

<a id='General-1'></a>

## General

[#](#DifferentialEquations){#DifferentialEquations} **`DifferentialEquations`** &mdash; *Module*.

### DifferentialEquations

This is a package for solving numerically solving differential equations in Julia by Chris Rackauckas. The purpose of this package is to supply efficient Julia implementations of solvers for various differential equations. Equations within the realm of this package include stochastic ordinary differential equations (SODEs or SDEs), stochastic partial differential equations (SPDEs), partial differential equations (with both finite difference and finite element methods), and differential delay equations. For ordinary differential equation solvers, see [ODE.jl](https://github.com/JuliaLang/ODE.jl)

This package is for efficient and parallel implementations of research-level algorithms, many of which are quite recent. These algorithms aim to be optimized for HPC applications, including the use of GPUs, Xeon Phis, and multi-node parallelism. With the easy to use plot/convergence testing algorithms, this package also provides a good sandbox for developing novel numerical schemes.

<a id='Mesh-Tools-1'></a>

## Mesh Tools

[#](#DifferentialEquations.meshgrid){#DifferentialEquations.meshgrid} **`DifferentialEquations.meshgrid`** &mdash; *Function*.

meshgrid(vx,vy,vz)

Computes an (x,y,z)-grid from the vectors (vx,vy,vz). For more information, see the MATLAB documentation.

meshgrid(vx,vy)

Computes an (x,y)-grid from the vectors (vx,vy). For more information, see the MATLAB documentation.

meshgrid(vx)

Computes an (x,y)-grid from the vectors (vx,vx). For more information, see the MATLAB documentation.

[#](#DifferentialEquations.CFLν){#DifferentialEquations.CFLν} **`DifferentialEquations.CFLν`** &mdash; *Function*.

CFLν(Δt,Δx)

Computes the CFL-condition ν= Δt/Δx

[#](#DifferentialEquations.CFLμ){#DifferentialEquations.CFLμ} **`DifferentialEquations.CFLμ`** &mdash; *Function*.

CFLμ(Δt,Δx)

Computes the CFL-condition μ= Δt/(Δx*Δx)

<a id='Solver-Tools-1'></a>

## Solver Tools

[#](#DifferentialEquations.gradbasis){#DifferentialEquations.gradbasis} **`DifferentialEquations.gradbasis`** &mdash; *Function*.

gradbasis(node,elem)

Returns the gradient of the barycentric basis elements.

[#](#DifferentialEquations.quadfbasis){#DifferentialEquations.quadfbasis} **`DifferentialEquations.quadfbasis`** &mdash; *Function*.

quadfbasis(f,gD,gN,A,u,node,elem,area,bdNode,mid,N,Dirichlet,Neumann,isLinear;gNquadorder=2)

[#](#DifferentialEquations.quadpts){#DifferentialEquations.quadpts} **`DifferentialEquations.quadpts`** &mdash; *Function*.

quadpts(order)

Returns the quadrature points and weights for and order ### quadrature in 2D.

[#](#DifferentialEquations.accumarray){#DifferentialEquations.accumarray} **`DifferentialEquations.accumarray`** &mdash; *Function*.

accumarray(subs, val, sz=(maximum(subs),))

See MATLAB's documentation for more details.

[#](#DifferentialEquations.assemblematrix){#DifferentialEquations.assemblematrix} **`DifferentialEquations.assemblematrix`** &mdash; *Function*.

assemblematrix(node,elem;lumpflag=false,K=[])

Assembles the stiffness matrix A as an approximation to Δ on the finite element mesh (node,elem). Also generates the mass matrix M. If lumpflag=true, then the mass matrix is lumped resulting in a diagonal mass matrix. Specify a diffusion constant along the nodes via K.

### Returns

A = Stiffness Matrix M = Mass Matrix area = A vector of the calculated areas for each element.

assemblematrix(FEMmesh::FEMmesh;lumpflag=false,K=[])

Assembles the stiffness matrix A as an approximation to Δ on the finite element mesh (node,elem). Also generates the mass matrix M. If lumpflag=true, then the mass matrix is lumped resulting in a diagonal mass matrix. Specify a diffusion constant along the nodes via K.

### Returns

A = Stiffness Matrix M = Mass Matrix area = A vector of the calculated areas for each element.

[#](#DifferentialEquations.gradu){#DifferentialEquations.gradu} **`DifferentialEquations.gradu`** &mdash; *Function*.

gradu(node,elem,u,Dlambda=[])

Estimates the gradient of u on the mesh (node,elem)

<a id='Error-Tools-1'></a>

## Error Tools

[#](#DifferentialEquations.getH1error){#DifferentialEquations.getH1error} **`DifferentialEquations.getH1error`** &mdash; *Function*.

function getH1error(node,elem,Du,uh,K=[],quadOrder=[])

getH1error(femMesh::FEMmesh,Du,u)

Estimates the H1 error between uexact and uh on the mesh (node,elem). It reads the mesh to estimate the element type and uses this to choose a quadrature order unless specified. If K is specified then it is the diffusion coefficient matrix.

[#](#DifferentialEquations.getL2error){#DifferentialEquations.getL2error} **`DifferentialEquations.getL2error`** &mdash; *Function*.

getL2error(node,elem,uexact,uh,quadOrder=[])

getL2error(femMesh::FEMmesh,sol,u)

Estimates the L2 error between uexact and uh on the mesh (node,elem). It reads the mesh to estimate the element type and uses this to choose a quadrature order unless specified.