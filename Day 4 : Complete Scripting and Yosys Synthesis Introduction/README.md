# Day 4 Complete Scripting and Yosys Synthesis Introduction

## Task 1: Hierarchy Check & Synthesis Script Generation

- Developed **dynamic Yosys script generation** to automate RTL-to-synthesis transition (`yosys_run.tcl`).
- Implemented **automated resource loading** of standard cell libraries and all Verilog sources using absolute paths.
- Integrated **structural hierarchy validation** to verify module consistency and design integrity before synthesis.
- Leveraged **variable-driven synthesis** using `$DesignName` and `$NetlistDirectory` for synchronized script execution.
- Provided **professional CLI feedback**, including status logging and headers for clear user experience.

**Screenshot:**
![1_Hierarchy_check_script_generation_1](1_Hierarchy_check_script_generation_1.png)
![1_Hierarchy_check_script_generation_2](1_Hierarchy_check_script_generation_2.png)
