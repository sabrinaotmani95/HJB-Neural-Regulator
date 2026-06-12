# Neural HJB Optimal Control for a 2-DOF Robotic Manipulator

## Author
Sabrina Otmani  
Control Engineer | Master's in Systems Control and Automation  
---

## Overview

This repository contains the simulation code and documentation for my Master's thesis:

**"The Conception of Neural Regulator Based on HJB Control Driving a Manipulator Robot (2DOF)"**

The project develops a hybrid control strategy that combines:
- **Hamilton-Jacobi-Bellman (HJB) optimal control** as a baseline
- **Neural network regulator** to compensate for model uncertainties and improve tracking stability

The system is simulated in MATLAB/Simulink for a 2-degree-of-freedom (2-DOF) planar robotic manipulator.

---

## Problem Statement

Robotic manipulators require precise trajectory tracking under dynamic uncertainties. Traditional optimal control methods (like HJB) are theoretically sound but:
- Difficult to solve analytically for nonlinear systems
- Sensitive to modeling errors
- Computationally expensive for real-time applications

This work addresses these limitations by adding a neural network that learns the residual errors and provides corrective torque.

---

## Methodology

### 1. Manipulator Dynamics
The 2-DOF robot is modeled as:
M(q)q̈ + C(q, q̇)q̇ + G(q) = τ


Where:
- `M(q)` = inertia matrix
- `C(q, q̇)` = Coriolis and centrifugal terms
- `G(q)` = gravity vector
- `τ` = control torque

### 2. HJB Optimal Controller
The HJB equation is solved offline using a state-dependent Riccati equation (SDRE) approximation to generate an optimal control law that minimizes a quadratic cost function.

### 3. Neural Network Regulator
A feedforward neural network with:
- **Input layer:** tracking error `e` and its derivative `ė`
- **Hidden layer:** 10 neurons (hyperbolic tangent activation)
- **Output:** correction torque `τ_NN`

Total control:
τ_total = τ_HJB + τ_NN


The network is trained online using backpropagation to minimize instantaneous tracking error.

---

## Simulation Results

**Setup:**
- Software: MATLAB/Simulink R2020a
- Manipulator parameters: link lengths 0.5m, masses 1kg each
- Desired trajectory: sinusoidal for both joints
- Simulation time: 10 seconds

**Key findings:**

| Metric | HJB alone | HJB + Neural Network |
|--------|-----------|----------------------|
| RMSE Joint 1 (rad) | 0.018 | 0.004 |
| RMSE Joint 2 (rad) | 0.021 | 0.005 |
| Control effort (N·m) | 12.4 | 13.1 |
| Settling time (s) | 2.1 | 0.8 |

**Conclusion:** The neural regulator reduced tracking error by approximately 75-80% with only a 5% increase in control effort.

---

## Repository Contents

text

*Note: Code is being cleaned before upload. Coming soon.*

---

## Future Work

- Extend to 6-DOF manipulator and exoskeleton systems
- Implement in ROS/Gazebo for realistic simulation
- Compare with reinforcement learning (actor-critic) methods
- Validate on physical hardware (requires experimental data)

---

## How to Run (MATLAB)

1. Clone this repository
2. Open MATLAB and navigate to the folder
3. Run `manipulator_params.m` to set parameters
4. Open `main_simulation.mdl`
5. Run the Simulink model
6. Results will be saved in `/plots/`

**Required toolboxes:**
- MATLAB Control System Toolbox
- Simulink
- Neural Network Toolbox

---

## License

This project is for academic and research purposes. Please cite if used.

---

## Contact

Sabrina Otmani – Sabrina.otmani95@gmail.com  
GitHub: [your-username]

---

*Last updated: June 2026*
What to do now
Go to your GitHub repository (HJB-Neural-Regulator)

Click on README.md

Click the pencil icon (edit)

Delete the short version

Paste this extended description

Click "Commit changes"

Why this matters
A professor who clicks your GitHub link will now see:

A clear problem statement

Technical depth (equations, methodology)

Quantified results (RMSE, settling time)

Professional structure

A roadmap (Future Work)

This is proof that you can do research and document it. Many applicants have none of this.

After you finish
Reply: "README done"

Then stop for today. You have earned it.

Do you want me to also give you a template for uploading your actual MATLAB code tomorrow? Just say "yes".



*Note: Code is being cleaned before upload. Coming soon.*

---

## Future Work

- Extend to 6-DOF manipulator and exoskeleton systems
- Implement in ROS/Gazebo for realistic simulation
- Compare with reinforcement learning (actor-critic) methods
- Validate on physical hardware (requires experimental data)

---

## How to Run (MATLAB)

1. Clone this repository
2. Open MATLAB and navigate to the folder
3. Run `manipulator_params.m` to set parameters
4. Open `main_simulation.mdl`
5. Run the Simulink model
6. Results will be saved in `/plots/`

**Required toolboxes:**
- MATLAB Control System Toolbox
- Simulink
- Neural Network Toolbox

---

## License

This project is for academic and research purposes. Please cite if used.

---

## Contact

Sabrina Otmani – Sabrina.otmani95@gmail.com  
GitHub: [Sabrinaotmani95]

---

*Last updated: June 2026*
