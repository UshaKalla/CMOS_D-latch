# CMOS_D-latch
Creating a discrete CMOS driven D-latch memory unit. 


# CMOS D-Latch Memory Unit

* **Static Power Optimization:** Built a transistor-level CMOS D-latch memory circuit using NMOS and PMOS devices, achieving stable data storage with zero static power consumption.
* **Transistor Reduction via NOR Topology:** Reduced the total transistor count from $22$ down to $18$ by implementing a custom CMOS NOR topology while perfectly preserving core latch functionality. 
* **SR-to-D Latch Transformation:** Redesigned basic SR latch inputs into a D-latch configuration using active-low controls and pull-up resistors, completely eliminating the invalid $S=1, R=1$ race condition state.

## Why Reducing Transistors is Imperative

In integrated circuit (IC) design and digital hardware engineering, minimizing the number of transistors is a critical design goal for several key reasons:

* **Reduced Chip Area and Cost:** Silicon real estate is expensive. Fewer transistors mean the physical layout takes up less space on the silicon wafer, directly lowering manufacturing costs per chip.
* **Lower Power Consumption:** Every transistor has parasitic capacitance and contributes to dynamic switching power loss. Fewer transistors mean less power is wasted switching states, leading to cooler and more energy-efficient circuits.
* **Higher Speed (Improved Propagation Delay):** Parasitic capacitance slows down signal transitions. Reducing the total component count decreases capacitive loading on nodes, allowing signals to propagate faster through the circuit.
* **Higher Reliability and Yield:** Simpler circuits with fewer components have a lower probability of manufacturing defects, improving the overall manufacturing yield and long-term hardware reliability.
