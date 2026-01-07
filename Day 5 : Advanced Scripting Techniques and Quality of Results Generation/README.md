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
