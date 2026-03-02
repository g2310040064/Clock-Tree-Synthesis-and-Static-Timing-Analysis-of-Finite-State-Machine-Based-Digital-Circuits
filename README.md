**Clock Tree Synthesis (CTS) and Static Timing Analysis (STA)**
This project demonstrates end-to-end FSM design with Clock Tree Synthesis and Static Timing Analysis using Vivado.

**📌 Project Overview**

Traffic Light Controllers are classic examples of Finite State Machines (FSMs) used in real-world embedded and digital systems.
This project implements an FSM-based Traffic Light Controller using Verilog HDL, followed by Clock Tree Synthesis (CTS) and Static Timing Analysis (STA) to ensure timing correctness in a sequential digital circuit.

The design is verified through functional simulation, synthesized onto an FPGA, and analyzed for timing closure.

**🎯 Objectives**

Design and implement an FSM-based Traffic Light Controller

Verify correct state transitions using RTL simulation

Perform synthesis and device-level implementation

Apply Clock Tree Synthesis to balance clock distribution

Perform Static Timing Analysis to check setup/hold constraints

Achieve full timing closure

**🔁 FSM Design Description**

States and Operation

State	          Description
S0	      Road A Green, Road B Red
S1	      Road A Yellow, Road B Red
S2	      Road A Red, Road B Green
S3	      Road A Red, Road B Yellow

**🧪 Functional Simulation Results**

**RTL Simulation Waveform**

**Analysis**
FSM initializes correctly after reset
Proper sequencing observed:
Road A: Green → Yellow → Red
Road B: Red → Green → Yellow
Outputs change only at clock edges

<img width="1280" height="508" alt="image" src="https://github.com/user-attachments/assets/9e118bb6-7b8a-49a6-989a-8e4612d66a24" />


**🧩 RTL Schematic View**

**Analysis**

Design consists of:
State register
Next-state combinational logic
Output logic using multiplexers
Clear separation between sequential and combinational blocks
Optimized logic structure
<img width="948" height="640" alt="image" src="https://github.com/user-attachments/assets/8af38808-3dca-4292-96a9-801faf5b0f8a" />

**🧱 Device View (Post-Synthesis)**

**Analysis**
Very low resource utilization
Logic evenly placed across the FPGA
No placement or routing congestion
FloorPlanning:
<img width="1110" height="647" alt="image" src="https://github.com/user-attachments/assets/89018d1c-3198-4842-9411-c0d4dfb91c5b" />
I/O Planning:
<img width="1194" height="646" alt="image" src="https://github.com/user-attachments/assets/74094070-46ef-45b7-980b-e3e78f9b837f" />

**🌳 Clock Tree Synthesis (CTS)**

**Clock Network View**

**Analysis**

CTS performed automatically by Vivado
Dedicated global clock buffers used
Balanced clock routing across all flip-flops
Reduced clock skew and insertion delay

**Static Timing Analysis (STA) Results**

Static Timing Analysis was performed after synthesis and Clock Tree Synthesis to verify that all timing constraints were met for reliable sequential operation.

**1️⃣ Setup Time Analysis**

Setup time ensures that data arrives at the destination flip-flop sufficiently before the active clock edge.

**Setup Time Summary**

Parameter	                    |    Value

Worst Negative Slack (WNS)	  :    +8.853 ns

Total Negative Slack (TNS)    :   	0.000 ns

Number of Failing Endpoints   :  	0

Total Number of Endpoints     : 	4

Timing Status                    	PASS

**Analysis**

All setup paths meet timing constraints.

Large positive WNS indicates strong timing margin.

No setup violations were detected.

**2️⃣ Hold Time Analysis**

Hold time ensures that data remains stable after the clock edge.

**Hold Time Summary**

Parameter	                    Value

Worst Hold Slack (WHS)	      +0.211 ns

Total Hold Slack (THS)	       0.000 ns

Number of Failing Endpoints    0

Total Number of Endpoints	     4

Timing Status                  PASS

**Analysis**

All hold constraints are satisfied.

Positive hold slack confirms correct clock skew management.

No race conditions observed.

**3️⃣ Pulse Width Analysis**

Pulse width analysis ensures that the clock high and low durations are sufficient for flip-flop operation.

**Pulse Width Summary**
Parameter	                               |     Value

Worst Pulse Width Slack (WPWS)	         :   +4.500 ns

Total Pulse Width Negative Slack (TPWS)	 :    0.000 ns

Number of Failing Endpoints	             :    0

Total Number of Endpoints                :   	5

Timing Status                            :	PASS

**Analysis**

Clock pulse widths satisfy minimum high and low time requirements.

No pulse width violations were detected.

Clock integrity is preserved across all sequential elements.

**Design Timing Summary**

<img width="1280" height="297" alt="image" src="https://github.com/user-attachments/assets/bd7149e9-f415-43a6-a5c5-7bbcfded86d1" />

**Overall Power Analysis Summary**

The power analysis was performed on the implemented netlist using Vivado’s Power Report with typical process conditions.

**Total On-Chip Power:** 0.062 W

**Design Power Budget:** Not specified

**Process Corner:** Typical

**Ambient Temperature:** 25.0 °C

**Junction Temperature:** 25.4 °C

**Effective Thermal Resistance (θJA):** 6.2 °C/W

**Thermal Margin:** 74.6 °C (safe operating range)

**Off-Chip Power Consumption:** 0 W

**Power Distribution**

**Static Power:** 0.060 W (97%)

**Dynamic Power:** 0.002 W (3%)

**Dynamic Power Breakdown**

**I/O Power:** 0.001 W (77%)

**Clocks:** < 0.001 W (21%)

**Signals:** < 0.001 W (1%)

**Logic:** < 0.001 W (<1%)

<img width="1280" height="415" alt="image" src="https://github.com/user-attachments/assets/6945e9e4-a3cd-4638-a94e-c7646c343eab" />

**Conclusion**

This project successfully demonstrates an efficient and low-power digital design verified through post-implementation power analysis. The total on-chip power consumption is 0.062 W, with static power contributing 97% and dynamic power limited to only 3%, indicating very low switching activity and optimized logic utilization.

The dynamic power is mainly dominated by I/O operations, while clock, signal, and logic power contributions are negligible, confirming that the internal logic is well-optimized. The design operates under safe thermal conditions, with a junction temperature of 25.4 °C and a high thermal margin of 74.6 °C, ensuring reliable and stable performance.

Overall, the results validate that the implemented design is power-efficient, thermally safe, and suitable for low-power FPGA applications. The methodology and analysis used in this project provide a strong foundation for future enhancements, such as power budgeting, clock gating, and activity-based optimization for further power reduction.





