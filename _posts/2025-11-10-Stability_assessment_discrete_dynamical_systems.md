---
layout: post
title: "Thoughts on Stability Assessment of Discrete Dynamical Systems"
date: 2025-11-12
categories: [Optimization, Research]
---

# Stability Assessment of Discrete Dynamical Systems

An important premise must be emphasized: **this criterion applies specifically to fixed points (1-periodic orbits) of discrete dynamical systems** — for instance, fixed points in iterative maps $x_{n+1}=f(x_n,\lambda)$ that satisfy $f(x_0,\lambda) = x_0$. Under this premise, $|f'(x_0)|<1$ corresponds to stability and $|f'(x_0)|>1$ to instability. This conclusion is absolutely correct and serves as one of the core criteria for bifurcations in discrete systems (such as flip bifurcations).

However, when extended to continuous dynamical systems or high-period orbits/chaotic attractors in discrete systems, the stability criteria differ. To avoid confusion, let's clarify the "applicable scope" and "exceptional cases" of this criterion to establish a complete stability assessment framework:

## I. The Essence: Why Does This Criterion Work? (Stability Nature of Fixed Points in Discrete Systems)

The core of discrete systems is "iterative evolution." The stability of a fixed point $x_0$ essentially concerns whether small perturbations decay through iterations:

Assume a small perturbation $\delta_n = x_n - x_0$ near the fixed point $x_0$. Applying Taylor expansion to the iterative map $x_{n+1} = f(x_n)$ (ignoring higher-order terms):

$$
x_{n+1} - x_0 = f(x_0 + \delta_n) - f(x_0) \approx f'(x_0) \cdot \delta_n
$$

Thus $\delta_{n+1} \approx f'(x_0) \cdot \delta_n$. After iterations, we obtain $\delta_n \approx [f'(x_0)]^n \cdot \delta_0$:

* If $|f'(x_0)| < 1$: $[f'(x_0)]^n$ approaches 0 as $n$ increases, perturbations decay → fixed point is **stable**;
* If $|f'(x_0)| > 1$: $[f'(x_0)]^n$ approaches infinity as $n$ increases, perturbations amplify → fixed point is **unstable**;
* If $|f'(x_0)| = 1$: linear terms fail, nonlinear terms must be examined (this is the critical point of bifurcation, e.g., $f'(x_0) = -1$ in flip bifurcations).

## II. Key Supplement: Different Stability Criteria for Different Systems/Objects

| Object of Study | System Type | Stability Criterion |
|----------------|-------------|---------------------|
| Equilibrium Point | Continuous System (ODE $\dot{x}=f(x)$) | **Eigenvalues** of Jacobian matrix $J(x_0) = \frac{\partial f}{\partial x}\bigg\|_{x_0}$:<br>- All eigenvalues have real parts < 0 → stable;<br>- At least one eigenvalue has real part > 0 → unstable;<br>- Some eigenvalues have real part = 0 → non-hyperbolic (bifurcation critical point, e.g., Hopf bifurcation). |
| Fixed Point (1-periodic orbit) | Discrete System (map $x_{n+1}=f(x_n)$) | Derivative of map at fixed point $f'(x_0)$ (i.e., 1×1 Jacobian):<br>- $\|f'(x_0)\| < 1$ → stable;<br>- $\|f'(x_0)\| > 1$ → unstable;<br>- $\|f'(x_0)\| = 1$ → non-hyperbolic (bifurcation critical point, e.g., flip bifurcation). |
| n-periodic orbit (n≥2) | Discrete System | Derivative of n-times iterated map $f^n(x) = f(f(\dots f(x)\dots))$ (n-fold composition) at periodic point:<br>- $\|(f^n)'(x_0)\| < 1$ → stable;<br>- $\|(f^n)'(x_0)\| > 1$ → unstable.<br>(Example: 2-periodic orbit requires computing $(f \circ f)'(x_0) = f'(x_1) \cdot f'(x_0)$, where $x_0,x_1$ are 2-periodic points) |
| Periodic Orbit (Limit Cycle) | Continuous System | **Floquet multipliers** of the periodic orbit (describing perturbation evolution near the orbit):<br>- All Floquet multipliers have modulus < 1 (or real part < 0) → stable;<br>- At least one Floquet multiplier has modulus > 1 (or real part > 0) → unstable;<br>- Some multipliers have modulus = 1 → non-hyperbolic (bifurcation critical point). |
| Chaotic Attractor | Continuous/Discrete System | Examine **Lyapunov exponents**:<br>- At least one positive Lyapunov exponent → chaotic (perturbations grow exponentially, sensitive dependence on initial conditions);<br>- All Lyapunov exponents ≤ 0 → non-chaotic (stable periodic or steady state). |

## III. Summary: Don't Confuse "Absolute Value of Derivative" with "Real Part/Modulus of Eigenvalues"

The criterion $|f'(x)| < 1$ is specific to fixed points in discrete systems, focusing on whether perturbations decay through iterations. In contrast, continuous systems focus on whether perturbations decay over time in differential equations, requiring "real parts of eigenvalues" for assessment (negative real part → decay, positive real part → growth).

When encountering stability problems, ask yourself two questions:

1. Is it a "continuous system" or a "discrete system"?
2. Is the object of study an "equilibrium point," a "1-periodic orbit," or a "high-period orbit/chaotic attractor"?

By answering these questions and referring to the corresponding criteria in the table, you won't make mistakes!
