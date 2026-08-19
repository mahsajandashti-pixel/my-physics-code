# my-physics-code
numerical simulations of basic physics including projectile motion and simple harmonic motion using NumPy and Matplotlib 
"""
projectile motion simulation  
free fall under gravity using euler method
Author : [Mahsa Dashti]
Date : 2026
""" 

import numpy as np  
import matplotlib.pyplot as plt

# ====== parameters ======

g = 9.8     #gravitional acceleration (m/s^2)
k = 0.15    # air resistance coefficient
dt = 0.01   # time step (s)
t_max = 10.0  # maximum simulation time (s)

# ====== initial conditions ======

time_steps = int(t_max / dt) # total number of time steps 
t = np.zeros(time_steps)     # time array
y = np.zeros(time_steps)     # height array 
v = np.zeros(time_steps)     # velocity array

y[0]=100.0  # initial height(m) 
v[0]=0.0    # initial velocity(m/s) 

# ====== numerical integration (euler method) ======

for i in range(time_steps - 1):
    # update time
    t[i+1] = t[i] + dt
    # calculate acceleration 
    a = -g - k * v[i]
    # update velocity and position using euler method 
    v[i+1]=v[i]+a *dt
    y[i+1]=y[i]+v[i]*dt
    
    # ground collision detection 
    # if object hits the ground , stop the simulation 
    if y[i+1]<= 0:
        y[i+1]=0   # set height to exactly zero
        t=t[:i+2]  # truncate time array 
        y=y[:i+2]  # truncate height array 
        v=v[:i+2]  # truncate velocity array 
        break      # exit the loop

# ====== visualization ======
plt.figure(figsize=(8,5))  # create figure wth specific size 
plt.plot(t,y,label='y(t)',color='red',linewidth=2)  # plot height vs time
plt.plot(t,v,label='v(t)',color='blue',linewidth=4) # plot velocity vs time
# customize the plot 
plt.title('projectile motion' , fontsize = 14 , fontweight = 'bold') 
plt.xlabel('time')
plt.ylabel('height')
plt.grid(True)
plt.legend()
plt.show()

# ====== simulation result ======
print("Simulation Results:")
print(f"time of flight:{t[-1]:.2f}seconds")
print(f"impact velocity : {v[-1]:.2f} m/s")
print(f"final height : {y[-1]:.2f} m")

