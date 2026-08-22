# Projectile Motion — Numerical Simulation

A computational physics project studying projectile motion under uniform gravitational acceleration.

The trajectory is simulated numerically using the Euler method and compared with the analytical solution.

## Physics

The projectile is launched with an initial velocity \(v_0\) at an angle \(\theta\) above the horizontal.

The equations of motion are:

\[
a_x = 0
\]

\[
a_y = -g
\]

The Euler method is used to numerically integrate the equations of motion.

## Numerical Method

The position is updated using:

\[
x_{n+1} = x_n + v_{x,n}\Delta t
\]

\[
y_{n+1} = y_n + v_{y,n}\Delta t
\]

The velocity is updated using:

\[
v_{x,n+1} = v_{x,n}
\]

\[
v_{y,n+1} = v_{y,n} - g\Delta t
\]

Linear interpolation is used to estimate the projectile's landing position more accurately.

## Analytical Solution

For projectile motion without air resistance, the exact flight time is:

\[
T = \frac{2v_0\sin\theta}{g}
\]

and the exact range is:

\[
R = \frac{v_0^2\sin(2\theta)}{g}
\]

The numerical results are compared with these analytical results.

## Parameters

| Parameter | Value |
|---|---:|
| Initial velocity | 20 m/s |
| Launch angle | 45° |
| Gravitational acceleration | 9.81 m/s² |
| Time step | 0.001 s |
| Numerical method | Euler |

## Results

The simulation calculates:

- Numerical flight time
- Analytical flight time
- Numerical range
- Analytical range
- Relative errors

The numerical and analytical trajectories are also compared visually.

## Visualization

The final trajectory comparison is shown below:

![Projectile trajectory](figures/projectile_trajectory.png)

## Technologies

- Python
- NumPy
- Pandas
- Matplotlib
- Jupyter Notebook

## Future Improvements

Possible extensions of this project include:

- Projectile motion with air resistance
- Different launch angles
- Different initial velocities
- Convergence analysis
- Comparison with the Runge–Kutta method
- Investigation of numerical error

## Part of Computational Physics Journey

This project is the first project in my Computational Physics Journey, beginning with classical mechanics and gradually progressing toward waves, electromagnetism, relativity, and computational quantum mechanics.

## Author

Mahsa Dashti

Physics Student
