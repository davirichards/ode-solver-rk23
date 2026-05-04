# ode-solver-rk23
Bogacki-Shampine ODE Solver (RK23) — Numerical Methods from Scratch Implementation of the Bogacki-Shampine method (a 3rd-order Runge-Kutta scheme) for solving Ordinary Differential Equations (ODEs), built from scratch in Python.

# What it does
Solves the initial value problem for the ODE:
du/dt = 10 · exp(-(t-2)² / 2·(0.075)²) - 0.6
with initial condition u(0) = 0.5, over the interval [0, 4] with step size h = 0.1.

The notebook computes and compares two numerical solutions in parallel:

  RK3 (3rd-order) — standard 3-stage Runge-Kutta update
  RK4 (4th-order embedded) — higher-order estimate using the same intermediate stages

This dual-output is the core idea behind Bogacki-Shampine: reusing function evaluations to estimate the local truncation error between orders, which is the foundation for adaptive step-size control in modern ODE solvers like scipy.integrate.solve_ivp.

# Why it matters
Most numerical solvers (MATLAB's ode23, SciPy's RK23) are built on this exact principle. Implementing it from scratch demonstrates understanding of:

  Runge-Kutta methods and their Butcher tableaux
  Embedded error estimation
  The trade-off between accuracy and computational cost in numerical integration

# Tech stack
  Python 
  numpy 
  matplotlib

Output
A plot comparing both numerical solutions over time, visualizing the divergence between the 2nd and 3rd-order estimates.
