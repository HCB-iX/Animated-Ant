# Animated-Ant
An interactive, highly detailed 3D ant animation built for games, websites, or educational apps. It captures the complex, mechanical movements of an insect with smooth, lifelike articulation.
## ⚙️ Key Features

* **Procedural Creature Generation:** Dynamically generates multi-legged lizards, centipedes, and tentacle systems with realistic joint constraints and angular sway.
* **Inverse Kinematics (IK Solver):** Forward and backward IK solvers allow limb end-effectors to reach targets and step naturally across terrain.
* **State-Based Locomotion:** Multi-legged systems calculate optimal footholds dynamically based on body movement velocity and swing arcs.
* **Zero Dependencies:** Built purely with native JavaScript and HTML5 Canvas API.

---

## 📐 Mechanics & Physics Architecture

### 1. `Segment` Class
Represents an individual joint/bone in a skeletal hierarchy.
* **Hierarchical Forward Kinematics:** Computes relative (`relAngle`) and absolute (`absAngle`) joint angles.
* **Angular Limits & Stiffness:** Constrains rotational range using smooth-step stiffness calculations to enforce natural bone joint limits.

### 2. `LimbSystem` & `LegSystem`
Implements Inverse Kinematics solvers for limbs and articulated appendages.
* Resolves distance vectors dynamically to reach targeted points via `moveTo()`.
* Tracks foot-step states (`0: Stationary`, `1: Swinging`, `2: Placing`) to generate realistic walking patterns relative to creature speed.

### 3. `Creature` Class
The root physics body governing overall movement.
* Applies forward acceleration, rotational torque, friction, and resistance parameters.
* Drives child segments and limb systems to track targets (e.g., cursor position).

---

## 🚀 Setup & Execution

### Project File Structure
Ensure your project directory is organized as follows:

```text
project-root/
├── index.html
└── script.js
