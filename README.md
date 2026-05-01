# ASIC-Design-for-Matrix-Vector-Computation
ASIC Design for Matrix-Vector Computation
# Matrix-Vector Multiplication ASIC (RTL Design)

## Overview
This project presents the design and implementation of a custom **ASIC** for matrix-vector multiplication:

\[
y = Wx
\]

where:
- \( W \): M×N matrix  
- \( x \): N×1 vector  
- \( y \): M×1 output vector (up to 48-bit precision)

In addition to core computation, the design integrates:
- **Sub-Word Sampling (SWS)**
- **ReLU activation function**

The system is implemented at the **Register Transfer Level (RTL)** using Verilog and follows a complete ASIC design approach, including datapath, control FSM, and memory interface.

📄 Full report: [Project Report](./Report-Proj2(1).pdf)

---

## Key Features
- Matrix-vector multiplication engine
- 64-bit datapath architecture
- Integrated ReLU activation function
- Bit-level Sub-Word Sampling (SWS)
- Memory-mapped interface for inputs and outputs
- Modular RTL design (datapath + control)

---

## Architecture

### Datapath
The datapath includes:
- Register file (2 read / 1 write ports)
- 64-bit multiplier and adder
- Comparator and multiplexers
- SubWordSampler module
- ReLU module
