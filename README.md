# ASIC-Design-for-Matrix-Vector-Computation
ASIC Design for Matrix-Vector Computation
# Matrix-Vector Multiplication ASIC (RTL Design)

## Overview
W is an MxN array matrix and x has an Nx1 vector with 8-bit or 16-bit values; hence, the result (y) will be an Mx1 vector whose elements should be 48-bits. W and x are fetched from a memory which is not part of the ASIC.

In addition to this computation, the designed ASIC should be capable of doing Sub-Word-Sampler (SWS) and ReLU function.

\[
y_i' = SWS_a^b(y_i) = y_i[b:a]; \quad b \ge a.
\]

\[
z_i = ReLU(y_i')
\]

The SWS extracts the bits of \( y_i \), located in position a to b and the ReLU function should pass positive values, otherwise, it returns zero. The sub-word fetched by the SWS function should be 8 bits or 16 bits.

I implemented these two modules and instantiated them in my DataPath.v file.

In addition to core computation, the design integrates:
- **Sub-Word Sampling (SWS)**
- **ReLU activation function**

The system is implemented at the **Register Transfer Level (RTL)** using Verilog and follows a complete ASIC design approach, including datapath, control FSM, and memory interface.

### Schematic
![Schematic](Schematic.png)

### Layout
![Layout](Layout.png)


---

## Key Features
- Matrix-vector multiplication 
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
