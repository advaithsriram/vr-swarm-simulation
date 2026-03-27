# Next-Best-View Aerial Swarms for Multi-Viewpoint Monitoring

The project report can be accessed here: [Advaith_LIS_Final.pdf](Advaith_LIS_Final.pdf)

This repository contains the simulation framework and experimental data for a comparative study between decentralized swarm-based exploration and Next-Best-View (NBV) planning in multi-drone systems.

The codebase builds on a Unity drone simulation originally developed in Project AutoQuad (Spring 2018, UAVs@Berkeley and ML@Berkeley), then developed at EPFL LIS. It was extended for a semester project at EPFL LIS focused on multi-agent aerial monitoring and visibility maximization.

## Project Overview

The primary objective of this project is to evaluate how effectively decentralized swarming algorithms can maximize scene visibility compared to explicit, information-driven NBV planning.

While NBV approaches are traditionally studied for single-agent systems, this work extends the comparison to multi-agent settings where scalability and coordination are critical.

## Methodology

Experiments were conducted in a Unity-based simulation environment using textured 3D residential models from the House3K dataset.

The study compares two distinct multi-agent control strategies:

- **MAP-NBV (Multi-Agent Prediction-Guided NBV):** A decentralized framework using the PoinTr model for point cloud completion. It iteratively selects viewpoints to maximize information gain by reasoning about unseen surfaces through geometric priors.
- **Decentralized Swarming (Olfati-Saber):** A potential-field-based algorithm where drone motion is governed by local interaction rules (attraction, repulsion, and obstacle avoidance). In this work, boundary drones were adapted to orient sensors inward toward the swarm centroid to maintain persistent observation of the target.

### Evaluation Metric

Performance is quantified using a normalized point cloud visibility metric. This metric measures the fraction of the ground-truth object surface represented by accumulated depth measurements, without requiring a full 3D reconstruction.

## Key Findings

- **Efficiency Trade-offs:** Swarm-based methods achieved higher overall surface coverage (up to ~96.6%) with shorter mission times and reduced travel distances, but required substantially more image captures.
- **Observation Sparsity:** NBV planning attained comparable reconstruction quality with significantly fewer observations, at the cost of longer execution times and more irregular trajectories.
- **Diminishing Returns:** Both methods showed diminishing returns as drone count increased. For swarms, visibility gains typically saturated around 5-6 drones due to field-of-view overlap and sensing redundancy.

## Repository Context

This repository includes:

- Unity simulation assets and scripts for multi-drone scene monitoring experiments.
- Experiment launch and orchestration scripts for both NBV and swarm pipelines.
- Post-processing and analysis scripts for comparing point-cloud visibility and uncovered regions.
- Output CSVs and notebooks used for quantitative comparison.

## Origins and Prior Work

The simulator foundation originated from:

- **Project AutoQuad, Spring 2018**
- **UAVs@Berkeley** and **Machine Learning @ Berkeley**

Original related project and references:

- AutoQuad repository: https://github.com/suneelbelkhale/AutoQuad
- RPY PID controller reference: https://github.com/WebdiverShaka/DroneControl

## Acknowledgments

This research was conducted as a semester project at **EPFL**, within the **Laboratory of Intelligent Systems (LIS)**.

- **Professor:** Dario Floreano
- **Assistant:** Benjamin Jarvis
- **Student:** Advaith Sriram
