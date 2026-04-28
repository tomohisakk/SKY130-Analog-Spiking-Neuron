# SKY130 Spiking Neuron

## Overview
Compact analog spiking neuron implemented in the SKY130 open-source process.  
Designed to generate neuron-like spikes from an input stimulus, targeting low-power neuromorphic and compute-in-memory applications.

Optimized for fabrication with a minimal 6-pin interface.

## Features
- Analog spiking behavior  
- Area-efficient design  
- Low power consumption  
- External bias control  
- Fabrication-ready (TinyTapeout)

## Pinout
| Pin | Name     | Description                         |
|-----|----------|-------------------------------------|
| 1   | VDD      | Supply voltage                      |
| 2   | VSS      | Ground                              |
| 3   | BiasC    | Bias control                        |
| 4   | IREFA    | Bias control                        |
| 5   | IREFB    | Bias control                        |
| 6   | Vout     | Spiking output                      |

## Operation

### 1. Core Principle
The neuron operates by integrating an input stimulus into an internal membrane state.  
This state evolves continuously until it reaches a threshold, at which point a spike is generated and the system resets.

This behavior mimics biological neurons where:
- A **fast variable** (membrane voltage) drives spike generation
- A **slow variable** (recovery/adaptation) regulates firing patterns

---

### 2. Dynamics
- The membrane node integrates input current and internal nonlinear currents  
- When excitation dominates, the voltage rapidly rises → spike  
- A reset mechanism brings the system back to a baseline  
- A slower feedback path suppresses activity after spikes, enabling:
  - spike-frequency adaptation  
  - bursting  
  - refractory-like behavior  

---

## Architecture (Conceptual)
The circuit is functionally composed of:
1. **Membrane block** – integrates input and generates nonlinear dynamics  
2. **Recovery block** – provides delayed negative feedback  
3. **Spike detection + reset** – converts analog state into discrete spikes  

This mirrors standard silicon neuron architectures where state variables are stored on capacitors and currents define their evolution.


## Fabrication
Ready for TinyTapeout submission and compliant with SKY130 design rules.
