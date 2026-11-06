# GA-SAC-BESS-CoOptimization
Bi-Level Co-Optimization of BESS Allocation and Continuous Dispatch in Unbalanced Distribution Networks Using Capacity-Conditioned Soft Actor-Critic (Manuscript Under Review)

---

### Project Overview
This repository contains the implementation of a unified bi-level co-optimization framework for active distribution networks. The upper level uses a Genetic Algorithm (GA) to optimize BESS capacity allocation, while the lower level uses a continuous Soft Actor-Critic (SAC) Deep Reinforcement Learning agent for dynamic active (P) and reactive (Q) power dispatch.

By incorporating a Capacity-Conditioned State Representation (S_t^cond = S_t || X_GA), a single pre-trained SAC policy evaluates candidate battery capacities instantly without repetitive neural network retraining across evolutionary search loops.

---

### Key Research Contributions & Results
- Zero Retraining Bottleneck: Replaces 500+ DRL retraining cycles during GA evolution with fast forward-pass policy inferences (< 2.40 ms).
- Voltage Restoration: Restores worst-case node voltage envelope from 0.925 p.u. to 1.025 p.u. on the unbalanced IEEE 34-bus feeder (0 statutory under-voltage breaches).
- Feeder Loss Mitigation: Reduces dynamic peak instantaneous active line losses by 53.3% and reactive losses by 67.3%.
- Software Cross-Validation: Automated Python-OpenDSS COM API co-simulation cross-validated under peak snapshot load flows inside DIgSILENT PowerFactory (< 0.002 p.u. error).

---

### Simulation Stack
- Optimization & AI: Metaheuristic Genetic Algorithm, Continuous Soft Actor-Critic (SAC), PyTorch
- Power Flow Engines: OpenDSS (via COM API), DIgSILENT PowerFactory
- Test Feeder: Benchmark Unbalanced IEEE 34-Bus Distribution System

---

### Directory Architecture
- dss_models/ : IEEE 34-Bus Master DSS scripts and load profiles
- src/ : GA optimizer, PyTorch SAC agent, and OpenDSS environment scripts
- powerfactory/ : DIgSILENT PowerFactory cross-validation setup files

---

### Contact & Citation
Author: Shabnam Praween  
Affiliation: Department of Electrical Engineering, Advanced College of Engineering and Management (ACEM), Tribhuvan University, Nepal  
Email: shabnam.praween.ee@gmail.com
