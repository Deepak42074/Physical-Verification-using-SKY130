# Physical-Verification-using-SKY130
A cloud based virtual training workshop conducted by VSD-IAT for Physical-Verification-using-SKY130.

![](https://github.com/Deepak42074/Physical-Verification-using-SKY130/blob/main/DAY_1_LAB/VSD_Physical_design.png)
## Table of Contents

  * [Day 1 - Introduction to SkyWater SKY130 and Open-Source EDA Tools](#day-1---introduction-to-skywater-sky130-and-open-source-eda-tools)
    + [SkyWater PDK](#skywater-pdk)
    + [Open-Source EDA Tools](#open-source-eda-tools)
    + [Physical Verification and Design Flows](#physical-verification-and-design-flows)
    + [Lab - Checking Tool Installations](#lab---checking-tool-installations)
    + [Lab - Creating an Inverter Design](#lab---creating-an-inverter-design)
  * [Day 2 - Design Rule Checks and Layout Vs. Simulation](#day-2---design-rule-checks-and-layout-vs-simulation)
    + [Fundamentals of Physical Verification](#fundamentals-of-physical-verification)
    + [Data Formats and GDSII](#data-formats-and-gdsii)
    + [Extraction Styles and Options in Magic](#extraction-styles-and-options-in-magic)
    + [GDS Reading and Writing in Magic](#gds-reading-and-writing-in-magic)
    + [DRC Rules in Magic](#drc-rules-in-magic)
    + [LVS Setup for Netgen](#lvs-setup-for-netgen)
    + [XOR Verification](#xor-verification)
    + [Lab - GDS read and Input Styles](#lab---gds-read-and-input-styles)
    + [Lab - Ports and Port Indexes](#lab---ports-and-port-indexes)
    + [Lab - Abstract Views](#lab---abstract-views)
    + [Lab - Basic Extraction](#lab---basic-extraction)
    + [lab - Setup for DRC](#lab---setup-for-drc)
    + [Lab - Setup for LVS](#lab---setup-for-lvs)
    + [Lab - Setup for XOR](#lab---setup-for-xor)
  * [Day 3 - Design Rule Checking](#day-3---design-rule-checking)
    + [Fundamentals of Design Rule Checking](#fundamentals-of-design-rule-checking)
    + [Back-end Metal Layer Rules](#back-end-metal-layer-rules)
    + [Local Interconnect Rules](#local-interconnect-rules)
    + [Front-end Rules](#front-end-rules)
    + [Wells, Taps and Net Rules](#wells-taps-and-net-rules)
    + [Deeps N-Well and High Voltage Rules](#deeps-n-well-and-high-voltage-rules)
    + [Device Rules](#device-rules)
    + [Miscellaneous Rules and Latch-up, Antenna and Stress Rules](#miscellaneous-rules-and-latch-up-antenna-and-stress-rules)
    + [Density Rules](#density-rules)
    + [Recommended, Manufacturing and ERC Rules](#recommended-manufacturing-and-erc-rules)
    + [Lab - Width and Spacing Rules](#lab---width-and-spacing-rules)
    + [Lab - Wide Spacing and Notch Rules](#lab---wide-spacing-and-notch-rules)
    + [Lab - Contact Cuts (Via) and its DRC Errors](#lab---contact-cuts-via-and-its-drc-errors)
    + [Lab - Minimum Area and Minimum Hole Rule](#lab---minimum-area-and-minimum-hole-rule)
    + [Lab - Wells and Deep N-Wells](#lab---wells-and-deep-n-wells)
    + [Lab - Derived Layers](#lab---derived-layers)
    + [Lab - Parameterised and PDK Devices](#lab---parameterised-and-pdk-devices)
    + [Lab - Angle And Overlap Rule](#lab---angle-and-overlap-rule)
    + [Lab - Unimplemented Rules](#lab---unimplemented-rules)
    + [Lab - Latch-up and Antenna Rules](#lab---latch-up-and-antenna-rules)
    + [Lab - Density Rules](#lab---density-rules)
  * [Day 5 - Running LVS](#day-5---running-lvs)
    + [Fundamentals of LVS](#fundamentals-of-lvs)
    + [Schematics and LVS Matching](#schematics-and-lvs-matching)
    + [LVS Netlists Vs. Simulation Netlists](#lvs-netlists-vs-simulation-netlists)
    + [Running Netgen](#running-netgen)
    + [Netgen Matching Algorithm](#netgen-matching-algorithm)
    + [Pre-Matching Analysis and Hierarchical Checking](#pre-matching-analysis-and-hierarchical-checking)
    + [Pin and Property Checking](#pin-and-property-checking)
    + [Series/Parallel Combining](#seriesparallel-combining)
    + [Symmetry Breaking](#symmetry-breaking)
    + [Interpreting Netgen Results](#interpreting-netgen-results)
    + [Lab - Introduction to LVS](#lab---introduction-to-lvs)
    + [Lab - LVS with Subcircuits](#lab---lvs-with-subcircuits)
    + [Lab - LVS with Blackboxes Subcircuits](#lab---lvs-with-blackboxes-subcircuits)
    + [Lab - LVS with SPICE Low Level Components](#lab---lvs-with-spice-low-level-components)
    + [Lab - LVS For Power-On-Reset Circuit](#lab---lvs-for-power-on-reset-circuit)
    + [Lab - Layout Vs. Verilog for Standard Cell](#lab---layout-vs-verilog-for-standard-cell)
    + [Lab - LVS with Macros](#lab---lvs-with-macros)
    + [Lab - LVS for Digital PLL Design](#lab---lvs-for-digital-pll-design)
  * [Acknowledgements](#acknowledgements)

## Day 1 - Introduction to SkyWater SKY130 and Open-Source EDA Tools

### SkyWater PDK
The SkyWater open PDK public repository and documentation link:
 - [Documentation](https://skywater-pdk.rtfd.io/) 
 - [PDK Library and files](https://github.com/google/skywater-pdk)

## Day 2 - Design Rule Checks and Layout Vs Simulation

## Day 3 - Design Rule Checking

## Day 4 - Understanding PNR and Physical verification with openlane flow

## Day 5 - Running LVS
