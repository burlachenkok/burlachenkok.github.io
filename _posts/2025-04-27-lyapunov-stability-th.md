---
layout: post
title: Note on Two Theorems On Lyapunov Stability
published: true
---


I was glad to gain insights from Prof. Eric Feron's Non-Linear Control course, where I learned about two important theorems that state the following.

# Definitions

## Stability

*Asymptotic Stability.* The system $$x(t)$$ is asymptotic stable if $$\lim_{t \to \infty} x(t) = 0.$$

*Exponential Stability.* The system $$x(t)$$ is exponential stable if $$\|x(t)\| \le c\cdot \exp(-\alpha t)\|x_0\|.$$

*An Invariant Set.* An invariant set is a set for a dynamical system if, whenever the system starts be in the set it remains in the set for all future time.

## Lyapunov Function

Assume that we can define a function $$V(x): \mathbb{R}^d \to \mathbb{R}^+$$, and this function is continuously differentiable.

Next, $$V(x) = 0$$ if and only if $$x = 0$$. Finally, $$V(x)$$ is radially unbounded in the sense that for all $$M \in \mathbb{R}$$, there exists $$R \in \mathbb{R}$$ such that

$$
\|x\|^2 \geq R^2 \implies V(x) \geq M.
$$

# Theorems

## Lyapunov Theorem (1892)

Lyapunov's theorem provides a sufficient condition for asymptotic stability for dynamics. We assume that there is a dynamic process

$$
\frac{dx}{dt} = f(x), \quad x(0) = x_0
$$

driven by an ODE. By the chain rule, we can evaluate the time derivative of the Lyapunov function:

$$
\frac{dV(x)}{dt} = \langle \nabla V(x(t)), \frac{dx}{dt} \rangle = \langle \nabla V(x(t)), f(x(t)) \rangle.
$$

If

$$
\frac{dx}{dt} = f(x), \quad x(0) = x_0
$$

and there exists a Lyapunov function $$V(x): \mathbb{R}^d \to \mathbb{R}^+$$ such that

$$
-\langle \nabla V(x), f(x) \rangle > 0, \quad \forall x(t) \neq 0,
$$

then

$$
\lim_{t \to \infty} x(t) = 0.
$$

The caveat is that finding such a function $$V(x)$$ is generally very hard. Additional references on how to construct $$V(x)$$ can be found in the works of Yakubovich, Popov and  Arkadiy Nemirovski.

## LaSalle's Theorem (1960)

LaSalle's theorem generalizes Lyapunov theorem and is useful for analyzing systems with more complex behavior.


Consider the process

$$
\frac{dx}{dt} = f(x), \quad x(0) = x_0.
$$

If the set $I = \left\{ x : \langle \nabla V(x), f(x) \rangle = 0 \right\}$ is empty except for $$x(t)=0$$ then

$$
\lim_{t \to \infty} x(t) = 0.
$$
