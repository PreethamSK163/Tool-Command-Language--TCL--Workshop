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
