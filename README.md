# compPhysHw3
# 1dWavePDE
This repository contains a code written by Will East and modified to solve Burger's equation with Roe's method and a minmod slope limiter. 

It solves Burger's equation on the unit interval [0,1] with periodic boundary conditions. The initial condition is a sine wave. Because the solution to the partial differential equation admits the appearance of shocks, special care must be taken to solve it. The code implements the flux based method called Roe's method as an iterating scheme to evolve the conserved quantity. Additionally, the code uses a slope limiter called minmod to avoid spurious oscillations.

We can study the convergence of the numerical scheme by using different resolutions. We take the highest resolution as a reference and we compute the L1 norm of the difference with the other resolutions. This way, we can see the speed of convergence of the method.

* At small times (before the shock happens), the convergence is quadratic even if we remove the minmod slope limiter.
Below is the error as a function of the resolutions (3 points were computed) without (upper figure) and with (lower figure) the minmod limiter.

![Unbiaised](/fig/error1lin.png)
Format: ![Alt Text](url)


![Unbiaised](/fig/error1minmax.png)
Format: ![Alt Text](url)


* At large times (once the shock is present), the convergence of the method becomes linear even with the slope limiter. The error as a function of the resolutions (3 points) with the minmod limiter is shown below.

![Unbiaised](/fig/errorEndminmax.png)
Format: ![Alt Text](url)

* It is possible to increase the order of convergence using other minmod reconstruction methods (WENO, Extremum Preserving Van Leer,...).
