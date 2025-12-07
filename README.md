# EV-Battery-Packet-Cooling-Duct-CFD-simulation-
📋 Project Overview
This repository documents the design and Computational Fluid Dynamics (CFD) analysis of a Serpentine Air-Cooling System for a Formula Student Electric Vehicle (FSEV) battery pack. The project aimed to optimize thermal management for a high-discharge Lithium-ion module under racing conditions.
Using a hybrid simulation approach (ANSYS Fluent for hydrodynamics and Fusion 360 for thermal mapping), the study validates the efficacy of a serpentine flow path in maintaining critical flow uniformity and managing pressure drops at high inlet velocities (17m s).

🎯 Objectives
•	Design Validation: Create a CAD model of a 36-cell module (Melasta Pouch Cells) with a serpentine airflow path.
•	Flow Analysis: Analyze velocity streamlines and calculate the static pressure drop (Delta P) using ANSYS Fluent.
•	Thermal Mapping: Evaluate the temperature distribution and identify hot spots using Fusion 360 Electronics Cooling.
•	Optimization: Determine the viability of the design for FSEV applications based on pressure and thermal gradients.

⚙️ Methodology
1. CAD Modeling (Fusion 360)
•	Geometry: 36 Pouch Cells arranged in a 3x12 configuration.
•	Air Path: Internal baffles designed to force air into a winding "S" shape (Serpentine).
•	Fluid Domain: Extraction of the negative air volume (4mm channel width) for CFD processing.
2. CFD Simulation (ANSYS Fluent)
•	Solver: Pressure-Based, Steady-State.
•	Turbulence Model: k-epsilon (Realizable) with Enhanced Wall Treatment.
•	Mesh: Patch Independent Tetrahedrons (Min size 0.5mm) to capture narrow channels without defeaturing.
•	Boundary Conditions:
o	Inlet: 17m s (Velocity Inlet).
o	Outlet: 0 Pa (Pressure Outlet).
o	Wall: Adiabatic, No-Slip.
3. Thermal Simulation (Fusion 360)
•	Heat Load: 175 W total internal heat generation (derived from drive cycle data).
•	Cooling Source: Fixed flow fan at 0.034m^3/s.

📊 Key Results
<img width="1206" height="578" alt="image" src="https://github.com/user-attachments/assets/6ae34120-c557-4207-8d92-dcb3736c5226" />

Visualizations
Velocity Streamlines (ANSYS Fluent)
The "Snake" pattern confirms the air successfully navigates the baffles, accelerating at the turns.
Thermal Gradient (Fusion 360)
Thermal mapping highlights the temperature rise from inlet (blue) to outlet (yellow/orange).

🛠️ Tech Stack & Tools Used
•	CAD & Thermal Analysis: Autodesk Fusion 360 (Electronics Cooling Workspace).
•	CFD Pre-Processing: ANSYS DesignModeler (Fluid Extraction).
•	Meshing: ANSYS Meshing (Patch Independent Algorithm).
•	CFD Solver: ANSYS Fluent 2025 R2 (First Order Upwind for Stability).

🚀 How to Run the Simulation **( Download the RAR file in the main branch and extract to access Ansys files)**
Prerequisites
•	ANSYS Workbench 2024/2025
•	Autodesk Fusion 360
Steps
1.	Geometry: Import the .step file from the /CAD folder into ANSYS DesignModeler.
2.	Meshing: Use the Patch Independent method. Set Max Size 5.0mm and Min Size 0.5mm.
3.	Setup:
o	Enable Energy Equation.
o	Set Material Density to 2500 kg/m^3.
o	Define Inlet Velocity 17 m/s.
4.	Run: Initialize using Standard Initialization and run for 600 iterations.

🧠 AI & Engineering Workflow
This project utilized an AI Engineering Co-pilot to accelerate the simulation workflow. Key contributions included:
•	Troubleshooting: Diagnosing "Floating Point Exceptions" and "Negative Volume" errors during the meshing phase.
•	Stability Optimization: Implementing "Soft Start" protocols (ramping velocity from 1 m/s to 17 m/s) and adjusting Relaxation Factors to achieve convergence.
•	Workflow Hybridization: Suggesting a parallel workflow (Fusion for Thermal, ANSYS for Flow) to meet tight project deadlines.

