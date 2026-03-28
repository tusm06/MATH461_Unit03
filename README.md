# MATH461_Unit03

## Problem description

A fire backdraft occurs when a depleted oxygen fire compartment suddenly receives fresh oxygen, causing a rapid explosive combustion. We model this as a compressible flow shock problem: a high-pressure, high-temperature region (burnt gases) is separated from a low-pressure, cooler region (fresh air entering). The interface creates a shock wave that propagates through the domain, transferring momentum and triggering rapid combustion dynamics.

## Question formulation

1. How does the shock velocity evolve as it propagates through the domain?
2. What is the structure of the velocity profile across the shock?
3. How much time does the shock take to reach the boundary of the cooler region?
4. What is the evacuation time available for people in the cooler region before the shock arrives?

## Mathematical model

**Assumptions:**
- 1D compressible flow along the spatial domain
- Inviscid flow (no viscous dissipation except at the shock)
- No heat transfer except through shock dynamics
- Shock is sharp (discontinuity in velocity/pressure)
- Burgers equation captures the nonlinear wave dynamics with diffusive regularization

**Variables** 

- $u(x,t)$: velocity field (1D)
- $\rho(x,t)$: density
- $p(x,t)$: pressure
- Independent variables: $x$ (space), $t$ (time)

**Parameters:**
- $\nu$: viscosity coefficient (for Burgers equation regularization)
- $L$: domain length
- $u_H, u_L$: high and low velocity initial conditions (left and right states)

**Equations:**

*Burgers Equation (simplified shock-capturing model):*

$$\frac{\partial u}{\partial t} + u \frac{\partial u}{\partial x} = \nu \frac{\partial^2 u}{\partial x^2}$$

This captures the essential nonlinear advection and shock formation. The viscous term prevents unphysical discontinuities and regularizes the shock thickness.

**How will you answer your question?**

We will:
1. Solve the Burgers equation numerically using finite differences (upwind scheme + viscous regularization)
2. Initialize with a step function velocity profile (high-velocity burnt gases meeting low-velocity fresh air)
3. Track the shock position and velocity profile evolution over time
4. Identify the shock location as a function of time (where velocity gradient is steepest)
5. Calculate the time for the shock to reach the cooler region boundary
6. Estimate evacuation time as the duration before the shock front reaches critical distances
7. Visualize the shock propagation, velocity structure, and timeline for evacuation scenarios
