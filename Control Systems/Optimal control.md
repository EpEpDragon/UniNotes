# Optimal control
Allows to specify physical performance objectives, eg. minimum-time or minimum-energy, as cost function and use optimisation theory to determine the best possible solution.

- Don't need to choose cl poles
- Rather find control input to minimise cost function

Find nonlinear time varying control function, mostly solved numerically:
$u(k) = f(\boldsymbol{x}(k), k)$
- Input:   $u(k)$ 
- Current states:   $\boldsymbol{x}(k)$
- Current time:   k

For linear plant with quadratic cost function, [[LQR]] (Linear Quadratic Regulator) analytic solution exists.