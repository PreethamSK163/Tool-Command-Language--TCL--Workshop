# Day 1 : Introduction to TCL and VSDSYNTH Toolbox Usage

## Task 1: Design Configuration & Environment Setup

- Implemented a CSV-driven configuration framework to enable design-agnostic TCL automation.
- Centralized design metadata in `openMSP430_design_details.csv` for scalable reuse across designs.
- Parsed key–value pairs to reliably initialize synthesis variables within TCL scripts.
- Automated directory mapping for RTL sources (`./verilog`) and output generation (`./outdir_openMSP430`).
- Integrated OSU 0.18µm standard cell libraries via explicit library search paths.
- Validated the Linux CAD environment for permissions, paths, and execution readiness.

**Screenshot:**
![1_Introduction_to_tcl_task_1](1_Introduction_to_tcl_task_1.png)
![1_Introduction_to_tcl_task_2](1_Introduction_to_tcl_task_2.png)

## Task 2: Shell Scripting & User Input Validation

- Developed a shell-based wrapper script (`vsdsynth`) using `tcsh` to control the end-to-end automation flow.
- Implemented a command-line interface header to clearly present tool functionality and integration with Yosys and OpenTimer.
- Added argument validation logic to verify the presence of the mandatory CSV configuration file before execution.
- Handled missing-input scenarios by displaying corrective usage instructions and safely terminating the flow.
- Applied executable permissions using environment-level commands to finalize the script as a Linux utility.

**Screenshot:**
![2_Scenario_1_User_doesn't_provide_an_input_CSV_file_1](2_Scenario_1_User_doesn't_provide_an_input_CSV_file_1.png)
![2_Scenario_1_User_doesn't_provide_an_input_CSV_file_2](2_Scenario_1_User_doesn't_provide_an_input_CSV_file_2.png)
