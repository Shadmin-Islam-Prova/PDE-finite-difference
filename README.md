# pde-finite-difference
Finite difference solutions of the heat, wave, Laplace, Poisson and advection equations 
# Later practiced in Python

# PDE Finite Difference Methods

Finite difference solutions of five PDEs

## Equations

| PDE | Equation | Scheme | Stability limit |
|---|---|---|---|
| Heat | u_t = α u_xx | Explicit, implicit, Crank-Nicolson | Explicit: r = α·dt/dx² ≤ 0.5 |
| Wave | u_tt = c² u_xx | Explicit (central) | C = c·dt/dx ≤ 1 |
| Laplace | u_xx + u_yy = 0 | Five-point stencil | Not needed (direct solve) |
| Poisson | u_xx + u_yy = f | Five-point stencil | Not needed (direct solve) |
| Advection | u_t + c·u_x = 0 | First-order upwind | C = c·dt/dx ≤ 1 |

## Parameters used

| PDE | Domain | Values |
|---|---|---|
| Heat | 0 < x < 1, t ≤ 0.1 | α = 1, N = 20 |
| Wave | 0 < x < 1, t ≤ 2 | c = 1, N = 50 |
| Laplace | unit square | N = 40 |
| Poisson | unit square | N = 40, f = −2π² sin(πx) sin(πy) |
| Advection | 0 < x < 1, t ≤ 0.5 | c = 1, N = 200 |

Initial and boundary conditions are in the header of each script.

## Results

Each script prints the maximum error against the exact solution.
Unstable cases are printed too, so you can see where each scheme breaks.

## Folders

- `python/`: five scripts, needs `numpy` (see `requirements.txt`)
- `r/`: five scripts, uses base R only

## How to run

Python:

```
pip install -r python/requirements.txt
python python/heat.py
```

R:

```
Rscript r/heat.R
```


