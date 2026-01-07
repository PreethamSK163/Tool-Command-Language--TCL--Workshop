# Day 5 : Advanced Scripting Techniques and Quality of Results Generation

## Task 1: Automated Synthesis Script Finalization

- Implemented **end-to-end synthesis automation**, executing the complete RTL-to-gate flow using `$DesignName` as the root hierarchy.
- Integrated **technology mapping** through Yosys `abc`, targeting the OSU 0.18µm standard cell library for hardware-realizable outputs.
- Enabled **multi-format netlist generation**, exporting both Gate-Level Verilog and structural JSON for downstream analysis.
- Applied **post-synthesis optimization routines** to clean redundant logic and eliminate floating or unused wires.
- Configured **batch-mode Yosys execution**, capturing detailed synthesis logs to support Quality of Results (QoR) evaluation.

**Screenshot:**
![1_Synthesis_script_creation_1](1_Synthesis_script_creation_1.png)
![1_Synthesis_script_creation_2](1_Synthesis_script_creation_2.png)

## Task 2: Automated Netlist Sanitization & Formatting

- Implemented an **automated post-synthesis netlist refinement engine** to eliminate manual editing before STA.
- Developed **high-speed stream editing logic** to process the synthesized Verilog netlist immediately after generation.
- Applied **regex-based sanitization (`regsub`)** to remove escaped characters and backslashes, ensuring standard Verilog compliance.
- Standardized **bussed signal notation and instance naming**, improving interoperability with STA tools.
- Ensured **non-destructive refinement**, preserving complete gate-level connectivity while cleaning syntax artifacts.
- Validated **seamless integration with Opentimer**, confirming the sanitized netlist is STA-ready without additional user intervention.

**Screenshot:**
![2_Edit_output_netlist_1](2_Edit_output_netlist_1.png)
![2_Edit_output_netlist_2](2_Edit_output_netlist_2.png)
![2_Edit_output_netlist_3](2_Edit_output_netlist_3.png)
![2_Edit_output_netlist_4](2_Edit_output_netlist_4.png)

## Task 3: TCL Array Commands & Data Structuring

- Implemented a **TCL associative array–based data management layer** to organize synthesis and timing metrics efficiently.
- Developed **centralized key–value mapping** to store critical results such as area, power, and timing slack with high clarity and fast access.
- Enabled **dynamic metric tracking** using array indexing, allowing simultaneous monitoring of multiple QoR parameters.
- Implemented **automated data retrieval routines** to extract and display selected metrics during runtime for immediate visibility.
- Established a **structured information flow** that synchronizes data across Synthesis, Timing Analysis, and Reporting stages.
- Designed a **scalable array architecture**, ensuring the tool can handle increased design complexity without restructuring the codebase.

**Screenshot:**
![3_TCL_array_commands_1](3_TCL_array_commands_1.png)
![3_TCL_array_commands_2](3_TCL_array_commands_2.png)

## Task 4: Modular Programming via Multiple TCL Procedures (proc)

- Refactored the automation flow using **functional decomposition**, separating environment setup, constraint handling, and synthesis execution.
- Designed a **modular tool architecture** using multiple TCL `proc` blocks, improving readability and long-term maintainability.
- Implemented **reusable procedures** for common operations such as regex-based port extraction, file checks, and directory validation.
- Enabled **dynamic argument management**, allowing procedures to adapt to different designs and configurations without code duplication.
- Improved **debug efficiency** by isolating logic into independent procedures, simplifying error identification and testing.
- Established a **scalable framework template**, enabling future EDA tool integrations through additional procedure calls without altering the core engine.

**Screenshot:**
![4_Setting_multiple_proc_1](4_Setting_multiple_proc_1.png)
![4_Setting_multiple_proc_2](4_Setting_multiple_proc_2.png)
![4_Setting_multiple_proc_3](4_Setting_multiple_proc_3.png)
![4_Setting_multiple_proc_4](4_Setting_multiple_proc_4.png)
![4_Setting_multiple_proc_5](4_Setting_multiple_proc_5.png)
![4_Setting_multiple_proc_6](4_Setting_multiple_proc_6.png)
![4_Setting_multiple_proc_7](4_Setting_multiple_proc_7.png)
![4_Setting_multiple_proc_8](4_Setting_multiple_proc_8.png)
![4_Setting_multiple_proc_9](4_Setting_multiple_proc_9.png)
![4_Setting_multiple_proc_10](4_Setting_multiple_proc_10.png)
![4_Setting_multiple_proc_11](4_Setting_multiple_proc_11.png)
![4_Setting_multiple_proc_12](4_Setting_multiple_proc_12.png)
