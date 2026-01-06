# Day 3 Processing Clock and Input Constraints

## Summary

- Developed a **CSV-to-SDC translation engine** to automate clock and input constraint generation for synthesis.
- Implemented **automated clock creation**, parsing Clock Name and Period from CSV, generating `create_clock` commands, and ensuring precise timing targets.
- Engineered a **smart port parser** to categorize signals into single-bit and bussed types, enabling full coverage for timing constraints.
- Integrated **dynamic RTL scanning and space-normalization**, extracting port names from Verilog and standardizing formatting for parsing accuracy.
- Applied **dual-layer pattern matching** and advanced differentiation logic to map CSV-defined constraints to both bit-level and bus-level signals.
- Automated **SDC command generation** for `set_input_delay`, `set_input_transition`, and `set_output_delay`, appending all constraints to a single master SDC file.
- Ensured **hardware-software synchronization** using `[get_ports]` syntax, guaranteeing compatibility with Yosys and Opentimer.
- Validated **flow scalability and accuracy** on the `openMSP430` design, confirming that all primary inputs and clocks were constrained correctly without manual intervention.


## Task 1: Automated Clock Constraint Generation

- Developed a **translation engine** to convert CSV data into functional SDC commands for automated clock definition.
- Implemented **clock data parsing** to extract Clock Name and Period metadata from the internal design matrix.
- Created **standardized SDC syntax routines** to generate `create_clock` commands compatible with industry-standard EDA tools.
- Configured **automated file generation** to create and populate the `.sdc` constraint file in the design output hierarchy.
- Integrated **precision timing control** to handle period and duty cycle calculations for accurate synthesis timing targets.
- Verified the **accuracy of generated clock constraints** by inspecting the output SDC file against the CSV configuration.

**Screenshot:**
![1_Creating_complete_clock_constraints_1](1_Creating_complete_clock_constraints_1.png)
![1_Creating_complete_clock_constraints_2](1_Creating_complete_clock_constraints_2.png)
![1_Creating_complete_clock_constraints_3](1_Creating_complete_clock_constraints_3.png)
![1_Creating_complete_clock_constraints_4](1_Creating_complete_clock_constraints_4.png)
![1_Creating_complete_clock_constraints_5](1_Creating_complete_clock_constraints_5.png)
![1_Creating_complete_clock_constraints_6](1_Creating_complete_clock_constraints_6.png)

## Task 2: Port Categorization & Bus Expansion Logic

- Developed a **smart port parser** to distinguish between single-bit signals and multi-bit buses for full timing coverage.
- Implemented **pattern-based identification** using TCL regular expressions to detect bus indices automatically.
- Created a **categorization engine** to separate ports into "Bussed" and "Bit" types for specialized handling.
- Added **namespace sanitization** to format CSV-derived port names for proper synthesis netlist integration.
- Prepared data structures to **expand bus references** (e.g., `DATA[7:0]`) into individual SDC constraints.
- Validated the algorithm with the `openMSP430` netlist, confirming correct identification and sorting of primary inputs.

**Screenshot:**
![2_Algorithm_to_categorisze_input_ports_as_bits_and_bussed_1](2_Algorithm_to_categorisze_input_ports_as_bits_and_bussed_1.png)
![2_Algorithm_to_categorisze_input_ports_as_bits_and_bussed_2](2_Algorithm_to_categorisze_input_ports_as_bits_and_bussed_2.png)

## Task 3: Automated Port Extraction & Space-Normalization

- Integrated **dynamic RTL scanning** to automatically extract all input port declarations from Verilog source files.
- Developed **fixed-space reformatting routines** to standardize whitespaces and tabs for consistent parsing.
- Implemented **automated data cleaning** to strip Verilog keywords and delimiters, isolating pure signal names for constraint mapping.
- Utilized **temporary file buffering** for efficient data handling, ensuring performance with high-gate-count netlists.
- Cross-validated the extraction engine against the `openMSP430` design to ensure accurate identification and formatting of all primary inputs.

**Screenshot:**
![3_Grepping_input_ports_from_all_verilog_and_reformatting_for_fixed_space_1](3_Grepping_input_ports_from_all_verilog_and_reformatting_for_fixed_space_1.png)
![3_Grepping_input_ports_from_all_verilog_and_reformatting_for_fixed_space_2](3_Grepping_input_ports_from_all_verilog_and_reformatting_for_fixed_space_2.png)
![3_Grepping_input_ports_from_all_verilog_and_reformatting_for_fixed_space_3](3_Grepping_input_ports_from_all_verilog_and_reformatting_for_fixed_space_3.png)
![3_Grepping_input_ports_from_all_verilog_and_reformatting_for_fixed_space_4](3_Grepping_input_ports_from_all_verilog_and_reformatting_for_fixed_space_4.png)
![3_Grepping_input_ports_from_all_verilog_and_reformatting_for_fixed_space_5](3_Grepping_input_ports_from_all_verilog_and_reformatting_for_fixed_space_5.png)
![3_Grepping_input_ports_from_all_verilog_and_reformatting_for_fixed_space_6](3_Grepping_input_ports_from_all_verilog_and_reformatting_for_fixed_space_6.png)
![3_Grepping_input_ports_from_all_verilog_and_reformatting_for_fixed_space_7](3_Grepping_input_ports_from_all_verilog_and_reformatting_for_fixed_space_7.png)
![3_Grepping_input_ports_from_all_verilog_and_reformatting_for_fixed_space_8](3_Grepping_input_ports_from_all_verilog_and_reformatting_for_fixed_space_8.png)
![3_Grepping_input_ports_from_all_verilog_and_reformatting_for_fixed_space_9](3_Grepping_input_ports_from_all_verilog_and_reformatting_for_fixed_space_9.png)
![3_Grepping_input_ports_from_all_verilog_and_reformatting_for_fixed_space_10](3_Grepping_input_ports_from_all_verilog_and_reformatting_for_fixed_space_10.png)

## Task 4: Bit and Bussed Port Differentiation Logic

- Implemented **dual-layer pattern matching** to verify CSV-defined constraints against the reformatted RTL port list.
- Developed **automated SDC formatting routines** for `set_input_delay`, `set_input_transition`, and `set_output_delay` commands.
- Engineered **intelligent bus handling** to apply constraints accurately to entire buses or individual bits as required.
- Configured **streamlined file I/O** to append all interface constraints directly to the master SDC file for a single source of truth.
- Ensured **synthesis compatibility** by using standard `[get_ports]` syntax, making constraints immediately usable by Yosys or other EDA tools.

**Screenshot:**
![4_Bit_or_bussed_differentiation_1](4_Bit_or_bussed_differentiation_1.png)
![4_Bit_or_bussed_differentiation_2](4_Bit_or_bussed_differentiation_2.png)
![4_Bit_or_bussed_differentiation_3](4_Bit_or_bussed_differentiation_3.png)
![4_Bit_or_bussed_differentiation_4](4_Bit_or_bussed_differentiation_4.png)
![4_Bit_or_bussed_differentiation_5](4_Bit_or_bussed_differentiation_5.png)
![4_Bit_or_bussed_differentiation_6](4_Bit_or_bussed_differentiation_6.png)
![4_Bit_or_bussed_differentiation_7](4_Bit_or_bussed_differentiation_7.png)
![4_Bit_or_bussed_differentiation_8](4_Bit_or_bussed_differentiation_8.png)
![4_Bit_or_bussed_differentiation_9](4_Bit_or_bussed_differentiation_9.png)
![4_Bit_or_bussed_differentiation_10](4_Bit_or_bussed_differentiation_10.png)
![4_Bit_or_bussed_differentiation_11](4_Bit_or_bussed_differentiation_11.png)
![4_Bit_or_bussed_differentiation_12](4_Bit_or_bussed_differentiation_12.png)
![4_Bit_or_bussed_differentiation_13](4_Bit_or_bussed_differentiation_13.png)

## Task 5: Input Constraint Generation & Advanced Port Differentiation

- Developed **algorithmic port matching** to link high-level constraints with RTL port declarations.
- Implemented **intelligent bus detection** to identify bussed signals and apply constraints to individual bits accurately.
- Engineered **automated SDC command writing** for `set_input_delay` and `set_input_transition`, dynamically appending to the SDC file.
- Ensured **hardware-software synchronization** using `get_ports` syntax for compatibility with Yosys and Opentimer.
- Validated the **flow scalability** on the `openMSP430` design, confirming accurate constraints for all primary inputs without manual intervention.

**Screenshot:**
![5_Input_constraint_generation_and_bits_or_buffed_differentiation_1](5_Input_constraint_generation_and_bits_or_buffed_differentiation_1.png)
![5_Input_constraint_generation_and_bits_or_buffed_differentiation_2](5_Input_constraint_generation_and_bits_or_buffed_differentiation_2.png)
![5_Input_constraint_generation_and_bits_or_buffed_differentiation_3](5_Input_constraint_generation_and_bits_or_buffed_differentiation_3.png)
![5_Input_constraint_generation_and_bits_or_buffed_differentiation_4](5_Input_constraint_generation_and_bits_or_buffed_differentiation_4.png)
![5_Input_constraint_generation_and_bits_or_buffed_differentiation_5](5_Input_constraint_generation_and_bits_or_buffed_differentiation_5.png)
![5_Input_constraint_generation_and_bits_or_buffed_differentiation_6](5_Input_constraint_generation_and_bits_or_buffed_differentiation_6.png)
![5_Input_constraint_generation_and_bits_or_buffed_differentiation_7](5_Input_constraint_generation_and_bits_or_buffed_differentiation_7.png)
![5_Input_constraint_generation_and_bits_or_buffed_differentiation_8](5_Input_constraint_generation_and_bits_or_buffed_differentiation_8.png)
![5_Input_constraint_generation_and_bits_or_buffed_differentiation_9](5_Input_constraint_generation_and_bits_or_buffed_differentiation_9.png)
