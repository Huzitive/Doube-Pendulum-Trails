# Double-Pendulum Trails — RK4 + Worker

An interactive double-pendulum physics simulation built with **HTML, CSS, and JavaScript**, using the **Runge–Kutta 4th-order method (RK4)** and a **Web Worker** for real-time numerical integration.  
Visualized with smooth trails, dynamic damping, and adaptive performance scaling.

---

## 🌌 Overview

This project demonstrates chaotic motion in a double-pendulum system.  
It simulates two connected pendulums influenced by gravity and damping, solving nonlinear equations of motion via RK4.  
All computation runs on a Web Worker thread, ensuring a responsive UI and consistent frame rate.

### Features
- Real-time RK4 numerical integration (480 Hz internal)
- Off-main-thread computation via Web Worker  
- Adjustable physical parameters (rod length, mass, gravity, damping)
- Trail visualization with gradient coloring  
- Auto-performance tuning for frame stability  
- Pan, zoom, and re-center controls  
- MathJax-rendered equations inside the UI  
- Responsive interface with Swiss-style minimal design  

---

## 🧩 Controls

| Action | Description |
|--------|--------------|
| **Space** | Play / Pause simulation |
| **R** | Reset parameters |
| **C** | Clear trail |
| **Mouse Drag** | Pan view |
| **Scroll** | Zoom in/out |
| **Double-Click** | Re-center view |

---

## ⚙️ Parameters

Adjust directly in the side panel:

| Parameter | Range | Default |
|------------|--------|----------|
| Rod 1 Length (L₁) | 60–240 | 160 |
| Rod 2 Length (L₂) | 60–240 | 160 |
| Mass (m₁) | 0.2–5.0 | 1.2 |
| Mass (m₂) | 0.2–5.0 | 1.0 |
| Gravity (g) | 50–1000 | 500 |
| Damping (γ) | 0–0.01 | 0.002 |
| Trail Length | 200–6000 | 2500 |
| Simulation Speed | 0.25–3.0 | 1.0 |

---

## 🧮 Equations of Motion

\[
\begin{aligned}
\dot{\theta}_1 &= \omega_1,\\
\dot{\theta}_2 &= \omega_2,\\
\dot{\omega}_1 &= 
\frac{-g(2m_1+m_2)\sin\theta_1 - m_2 g\sin(\theta_1-2\theta_2) - 2\sin(\theta_1-\theta_2)\, m_2 (\omega_2^2 L_2 + \omega_1^2 L_1\cos(\theta_1-\theta_2))}{L_1[2m_1+m_2 - m_2\cos(2\theta_1-2\theta_2)]} - \gamma\omega_1,\\
\dot{\omega}_2 &= 
\frac{2\sin(\theta_1-\theta_2)\,[\omega_1^2 L_1 (m_1+m_2) + g (m_1+m_2)\cos\theta_1 + \omega_2^2 L_2 m_2 \cos(\theta_1-\theta_2)]}{L_2[2m_1+m_2 - m_2\cos(2\theta_1-2\theta_2)]} - \gamma\omega_2.
\end{aligned}
\]

---

## 🖥️ Tech Stack

- **HTML5 Canvas** for visualization  
- **Web Workers** for physics computation  
- **MathJax** for formula rendering  
- **Vanilla JavaScript** (no libraries)  
- **CSS Grid + Flex** for UI  

---

## 🚀 Run Locally

```bash
git clone https://github.com/<your-username>/double-pendulum-trails.git
cd double-pendulum-trails
