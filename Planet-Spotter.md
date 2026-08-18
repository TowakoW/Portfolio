---
layout: page
title: Projects
permalink: /projects/
---
### Planet Spotter
*Work in progress* program that pulls from NASA JPL's Horizons API to graph real-time location data for all planets (+ Pluto) in our solar system. The program then uses the Self-Implicit Euler method to simulate short term planet motion about the Sun. This is my first larger project, and I am continuing to update it as I learn more coding.

Planet Spotter is a simple program that pulls planet data from NASA JPL's Horizons API and creates a short term simulation based on initial values. The goal is to create a program that allows users to see current planet locations relative to their current location on earth, as well as one of my first endeavors to become more familar with Python programming!

## Method
### Step 1: Horizons API
Real-time information is fetched from NASA JPL Horizons API for all planets in the solar system as well as the Sun and Pluto.
* Hopefully moons will be added in the future.

The received output is parsed to take only each object's GM (km^3/s^2) and ephemeris data (x, y, z, vx, vy, vz).

### Step 2: Initial Plotting
planet_data.py planet_calc.py

The parsed data is plotted on an interactive 3d graph with matplotlib.pyplot.

### Step 3: Physics Simulation
Using the Semi-Implicit Euler method, the locations of the planets are calculated and updated on the graph.

  **Acceleration Calculation:**
  Parameters
  -----
  system: System
        System object ("solar_system")
  a: np.ndarray
        Gravitational acceleration array to be modified, shape (N, 3), (km/s^2)

  Equation
  -----
  a = sum(GM/r_norm^3 * r_ij)
        
  Reference
  -----
  "5 Steps to N-body Simulation" by alvinng4: 
https://alvinng4.github.io/grav_sim/5_steps_to_n_body_simulation/step2/#implementation-3-advanced

### Step 4: Translating to Local Perspectives
work in progress...

Resources
NASA JPL Horizons API: https://ssd.jpl.nasa.gov/horizons/

["5 steps to N-body simulation" by alvinng4:](https://alvinng4.github.io/grav_sim/5_steps_to_n_body_simulation/)

### Next Steps...
Convert cartesian coordinates to RA/DEC from the perspective of a specific point on Earth to show relative planet locations for viewers of the night sky/add moons and other satellites.

**See below for demo interactive 3D graph:**
(Not live-updating due to Github website limitations)

<iframe src="/TowakoW/interactive_orbit.html" width="100%" height="600px" style="border:none;"></iframe>

*Shot taken on Aug 17, 2026 at 10:35 PM*

<a href="/TowakoW/" class="btn btn-sm z-depth-0" role="button">Back to Home</a>
