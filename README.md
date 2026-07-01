# Adaptive Time-Graded Control for VSC-MTDC Networks

[![MATLAB](https://img.shields.io/badge/MATLAB-Simulink-orange.svg)](https://www.mathworks.com/products/simulink.html)
[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Field](https://img.shields.io/badge/Field-Power%20Systems%20%26%20Smart%20Grids-green.svg)]()

This repository contains the MATLAB/Simulink implementation of an **Adaptive Time-Graded Control Method** for Voltage Source Converter Multi-Terminal DC (VSC-MTDC) networks. The project implements a communication-less, decentralized control scheme designed to coordinate multiple VSC stations during active power imbalances, severe contingencies (converter outages), and dynamic wind energy integration.

It serves as a professional validation benchmark based on the research article: *"An adaptive time-graded control method for VSC-MTDC networks"*.

---

## 📌 Project Overview & Key Features

Modern MTDC grids heavily rely on droop control or master-slave (slack-based) configurations. However, traditional droop controllers suffer from unregulated DC voltage deviations, while master-slave topologies introduce a single point of failure. 

This project implements an **adaptive, time-graded protection and control mechanism** that:
* **Decentralized Coordination:** Operates without the need for high-speed telecommunication links between terminals.
* **Dynamic Mode Transition:** Automatically switches VSC terminals between Active Power Control ($P-Q$) and DC Voltage Control ($V_{dc}-Q$) depending on localized DC voltage thresholds.
* **Priority-Based Restoration:** Recovers the grid to its optimal operating state sequentially once transient contingencies are cleared.
* **Wind Energy Integration:** Evaluates grid robustness under highly fluctuating wind turbine power injections.

---

## 📂 Repository Structure
```directory
├── models/                                      # Main Simulink models
│   ├── mtdc_base_network.slx                    # Base 4-terminal VSC-MTDC network
│   ├── mtdc_droop_control.slx                   # Conventional droop-control benchmark
│   ├── mtdc_reference_tracking.slx              # Active power reference tracking scenario
│   ├── mtdc_converter_outage.slx                # Permanent converter outage scenario
│   └── mtdc_wind_integration.slx                # Wind farm integration scenario
│
├── docs/                                        # Simulation figures and visualizations
│   ├── VDC.png                                  # DC voltage transient recovery
│   ├── Screenshot 2026-07-01 142926.png         # Steady-state operation
│   ├── Screenshot 2026-07-01 142305.png         # Dynamic response to disturbances
│   └── Screenshot 2026-07-01 142153.png         # Multi-signal transient comparison
│
├── references/
│   └── adaptive_time_graded_control_paper.pdf   # Reference research paper
│
└── README.md
