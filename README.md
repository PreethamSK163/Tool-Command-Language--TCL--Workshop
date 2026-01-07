# Tool Command Language (TCL) : Digital VLSI Automation Project – RTL to QoR Flow

This project focuses on building a fully automated, design-agnostic RTL-to-gate-level synthesis and timing analysis flow using open-source VLSI tools, with a strong emphasis on reproducibility, scalability, and end-to-end automation. The goal was to create a structured framework that converts design specifications from CSV configuration files into complete synthesis and STA-ready outputs, including timing constraints, netlists, and quality-of-results (QoR) metrics.  

The project was executed over five days, progressively developing the automation framework, enhancing robustness, and integrating synthesis and timing analysis capabilities using industry-standard methodologies and open-source tools.

## Overview of Workflow and Daily Progress

**Day 1 – Introduction to TCL and VSDSYNTH Toolbox Usage**  
- Set up the foundation for automation by creating a design-agnostic configuration framework using TCL scripts driven entirely by CSV inputs containing design details and constraints.  
- Decoupled design data from script logic to enable scalable reuse for multiple RTL designs.  
- Developed a shell-based front-end (`vsdsynth`) using `tcsh`, providing a professional CLI interface with argument validation, error handling, and a dynamic help system; ensured only valid inputs entered the synthesis flow and Linux CAD environment was fully prepared.  

**Day 2 – Variable Creation and Processing Constraints from CSV**  
- Parsed CSV configuration files into internal TCL variables and matrices for automated environment initialization and dynamic variable creation.  
- Implemented intelligent directory management to ensure all RTL sources, output directories, and standard cell libraries were correctly linked and created if missing.  
- Supported variable-length CSV files with distinction between metadata headers and functional data; prepared environment for constraint generation and synthesis; used `openMSP430` design for verification.  

**Day 3 – Processing Clock and Input Constraints**  
- Automated generation of timing constraints by extracting clock definitions, input/output delays, and transition constraints from CSV files and converting them into SDC commands.  
- Developed a smart port parser to distinguish single-bit and multi-bit bussed signals; performed dynamic RTL scanning to extract port names directly from Verilog sources.  
- Applied advanced pattern matching to accurately map CSV constraints to RTL signals and compiled all timing constraints into a master SDC file compatible with synthesis tools like Yosys and timing analysis tools like OpenTimer.  

**Day 4 – Complete Scripting and Yosys Synthesis Introduction**  
- Generated dynamic TCL scripts for Yosys (`yosys_run.tcl`) to load all RTL sources and standard cell libraries with absolute paths.  
- Implemented hierarchy checks and structural validation to detect missing modules, syntax errors, or invalid netlist generation.  
- Added robust error handling routines to halt the flow gracefully in case of issues; enabled end-to-end RTL-to-gate synthesis with professional logging and real-time debugging and verification feedback.  

**Day 5 – Advanced Scripting Techniques and Quality of Results Generation**  
- Developed modular TCL procedures for reusable scripting, library and RTL loading, and constraint handling.  
- Translated SDC constraints into OpenTimer-compatible format, including clock latency, input/output delays, and bit-blasting for multi-bit buses to ensure granular timing coverage.  
- Automated generation of OpenTimer configuration files, execution of timing analysis, and extraction of QoR metrics such as instance count, worst negative slack (WNS), and final endpoint timing (FEP); created a professional CLI dashboard and CSV reporting system for fully automated RTL-to-QoR evaluation.  

## Tools and Technologies Used

- **TCL (`tclsh`)** – for scripting, automation, and data parsing  
- **tcsh / Shell Scripting** – for CLI wrapper development and automation control  
- **CSV Parsing Libraries / Matrix Handling in TCL** – for reading and converting design configurations into variables and arrays  
- **Yosys** – for RTL synthesis and netlist generation  
- **OpenTimer** – for static timing analysis using translated SDC constraints  
- **Verilog RTL Designs** – for source-level testing (example: `openMSP430`)  
- **Linux Environment** – for executing automation scripts, synthesis, and STA  

## Key Achievements

- Developed a **scalable, design-agnostic automation framework** for RTL synthesis and timing analysis.  
- Automated **CSV-to-TCL variable parsing**, enabling flexible reuse across different designs.  
- Implemented **smart port parsing and bit-blasting** for accurate timing constraints on bussed signals.  
- Created **fully automated SDC-to-OpenTimer translation**, including clocks, input/output delays, and transitions.  
- Enabled **end-to-end flow execution** from RTL to QoR metrics, with professional CLI feedback and CSV reports.  
- Established a **robust error-handling and hierarchy validation system**, preventing invalid netlists and synthesis failures.  

This project demonstrates a professional, reproducible VLSI automation flow, integrating design configuration, synthesis, STA, and QoR extraction, suitable for advanced ASIC and SoC design verification and optimization.
