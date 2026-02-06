# FSM-Based Traffic Light Controller: Clock Tree Synthesis and Static Timing Analysis

This project presents the design and timing analysis of a Finite State Machine (FSM)-based Traffic Light Controller. It focuses on **Clock Tree Synthesis (CTS)** to optimize clock distribution and **Static Timing Analysis (STA)** to ensure timing correctness in sequential digital circuits, addressing setup/hold violations, clock skew, and critical path timing.

## Project Overview

Traffic Light Controllers are a practical example of FSMs, coordinating traffic signals through well-defined states and transitions. This project models the FSM at the **gate/transistor level**, applies CTS for balanced clock distribution, and performs STA to verify timing constraints across all sequential elements.

## Objectives

- Design and implement an FSM for traffic light control with defined states and transitions.
- Apply Clock Tree Synthesis to minimize clock skew and balance clock delays.
- Perform Static Timing Analysis to evaluate setup and hold times, clock-to-Q delays, slack, and critical paths.
- Analyze timing closure challenges in sequential digital circuits.

## Key Concepts

- **Finite State Machines (FSM)**
- **Clock Tree Synthesis (CTS)**
- **Static Timing Analysis (STA)**
- **Timing Constraints** (Setup, Hold, Slack)
- **Critical Path Analysis**

## Methodology

1. **FSM Design:** Define states, transitions, and output logic for traffic light sequences.
2. **Clock Tree Synthesis (CTS):** Create a hierarchical clock distribution network to reduce skew and balance delays.
3. **Static Timing Analysis (STA):** Calculate propagation delays, setup/hold margins, clock-to-Q delays, slack, and identify critical paths.
4. **Timing Verification:** Ensure all sequential paths meet timing constraints for reliable circuit operation.

## Tools Used

- HDL Simulation Tools (Verilog/VHDL)
- EDA Tools for CTS and STA (Synopsys, Cadence, or OpenROAD)
- Gate/Transistor-level modeling for timing analysis

## Conclusion

By integrating CTS and STA techniques, this project demonstrates a practical approach to timing closure in FSM-based sequential circuits. The Traffic Light Controller serves as a realistic, manageable example for studying clock distribution, skew optimization, and critical path analysis at the gate/transistor level.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
