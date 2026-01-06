# Day 3 Processing Clock and Input Constraints

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
