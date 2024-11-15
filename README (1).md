
# DOME: Drone-Assisted Monitoring of Emergent Events

This repository reproduces the results from the paper **"DOME: Drone-Assisted Monitoring of Emergent Events for Wildland Fire Resilience"** presented at ICCPS 2023. The DOME system leverages drones to monitor dynamic emergent events, with a focus on prescribed (Rx) fires. The repository contains the implementation, results, and a presentation summarizing our work.

## Repository Contents
- **`DOME.ipynb`**: The full implementation of the DOME system, including task generation, allocation, and multi-drone flight planning.
- **`DOME.pdf`**: The paper that introduces the DOME system, its methodology, and its evaluation.
- **`DOME FINAL.pptx`**: A presentation summarizing the project and showcasing the results.

## Overview of DOME
The DOME system is designed to enhance situational awareness and response efficiency for Rx fires. Rx fires are controlled burns used by forest services to manage hazardous fuels and promote ecosystem health. DOME coordinates multiple drones equipped with sensors to perform real-time monitoring.

### Key Features
1. **Task Generation**: Using a physics-inspired rule-based framework, DOME generates monitoring tasks for drones based on user-defined rules, fire prediction models, and current fire status.
2. **Task Allocation**: Tasks are allocated to drones by considering their capabilities, sensor types, and current status. The system minimizes utilization to ensure efficient resource distribution.
3. **Multi-Drone Flight Planning**: DOME plans optimal flight paths for drones, balancing sensing coverage, data quality, and communication constraints.
4. **Data Storage and Transmission**: DOME enables drones to store data during network disconnections and upload it once communication with the Ground Controller (GC) is restored.

## Implementation Phases
### 1. Task Generation
- **Spatial-Temporal Factors**: Tasks are defined based on the fire's predicted evolution and user priorities.
- **Physics-Based Fire Prediction**: Models like FARSITE are used to simulate fire spread and guide task creation.
- **Dynamic Updates**: Tasks are continuously updated based on real-time data from drones.

### 2. Task Allocation
- **Utilization-Based Allocation**: Tasks are clustered spatially and assigned iteratively to minimize drone utilization.
- **Heterogeneous Drone Capabilities**: The system accounts for differences in drones’ sensors, flying speed, and communication range.

### 3. Multi-Drone Flight Planning
- **Epoch-Based Planning**: Tasks are scheduled for fixed durations (epochs) to ensure periodic updates.
- **Waypoint Generation**: Drones are guided through optimal waypoints while considering coverage, data resolution, and communication constraints.
- **Markov Decision Process (MDP)**: Flight planning is modeled as an MDP, enabling dynamic adjustments to maximize task accomplishment.

### 4. Data Generation
The simulation starts with a 50×50 grid, initializing fire at specified points (e.g., [542, 1590]). Fire spreads to adjacent cells with a defined probability (e.g., 0.9) and progresses through stages: "starting," "spreading," and "burnt out." Burnout times are sampled from plausible durations (e.g., 16–24 minutes), creating realistic fire spread patterns.

## Results
Our experiments demonstrate the following results:
- **Task Assignment**: The number of tasks assigned to task clusters for each drone at the end of each epoch was plotted, providing insights into resource allocation efficiency.
- **Reward vs. Epoch Time**: The plot of reward versus epoch time was generated, showcasing the improvement in data quality and task completion over time.

## Getting Started
1. Clone the repository:
   ```bash
   git clone https://github.com/your-repo/dome.git
   cd dome
   ```
2. Open `DOME.ipynb` in Jupyter Notebook to run the simulations.

## Contributors
- Ajay Sankar Makkena  
- Bala Sathwik  
- Banoth Mithun Raj  
- Gude Rachana  
- Maligireddy Anjali  
- Mokkapati Shanmukha Sree  

## References
- Liu, Fangqi, et al. "DOME: Drone-assisted Monitoring of Emergent Events For Wildland Fire Resilience." Proceedings of the ACM/IEEE 14th International Conference on Cyber-Physical Systems (with CPS-IoT Week 2023). 2023.

