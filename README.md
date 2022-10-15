# Physical-Verification-using-SKY130
A cloud based virtual training workshop conducted by VSD-IAT for Physical-Verification-using-SKY130.

![](https://github.com/Deepak42074/Physical-Verification-using-SKY130/blob/main/DAY_1_LAB/VSD_Physical_design.png)
## Table of Contents

  * [Day 1 - Introduction to SkyWater SKY130 and Open-Source EDA Tools](#day-1---introduction-to-skywater-sky130-and-open-source-eda-tools)
    + [SkyWater PDK](#skywater-pdk)
    + [Tools supported by openpdks](#Tools-supported-by-openpdks)
    + [Lab - Creating an Inverter Design](#lab---creating-an-inverter-design)
  * [Day 2 - Design Rule Checks and Layout Vs. Simulation](#day-2---design-rule-checks-and-layout-vs-simulation)
    + [Fundamentals of Physical Verification](#fundamentals-of-physical-verification)
    + [Layout file formats and GDSII format](#Layout-file-formats-and-GDSII-format)
    + [Extraction commands Styles and Options in Magic](#extraction-commands-styles-and-options-in-magic)
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

Steps to  install SKY130 PDKs and openpdk:
First clone the repository and for this run the following commands.

```
git clone https://github.com/RTimothyEdwards/open_pdks
cd open_pdks
configure --enable-sky130-pdk
make
sudo make install
```

The "make" process grabs the SKY130 repository and submodules, as well as a few third party repositories to use in the install. It then builds the libraries from these various repositories.

### Tools supported by openpdks

Open_PDKs is a Makefile based installer that takes files from the SkyWater PDKs and reformats them for a number of open source EDA tools as listed below:
- Magic
- Klayout
- Openlane
- Xschem
- Netgen
- Ngspice
- IVerilog
- qflow
- IRSIM
- xcircuit

The libraries supported by open_pdks are:
- Digital standard cells (ex: sky130_fd_sc_hd)
- Primitive devices/analog (ex: sky130_fd_pr)
- I/O cells (ex: sky130_fd_io)
- 3rd party libraries (ex: sky130_ml_xx_hd)
sky130_ml_xx_hd : This contains set of layout for alphanumeric layout used for putting text on layout whihc can be seen under microscope.

### lab creating an inverter design
#### Schematic Design and Simulation

![](https://github.com/Deepak42074/Physical-Verification-using-SKY130/blob/main/DAY_1_LAB/Inverter_sch.png)

- Inverter testbench
![](https://github.com/Deepak42074/Physical-Verification-using-SKY130/blob/main/DAY_1_LAB/Inverter_tb.png)

- Inverter testbench spice file:
![](https://github.com/Deepak42074/Physical-Verification-using-SKY130/blob/main/DAY_1_LAB/inverter_tb_spice.png)

- Simulation Result
![](https://github.com/Deepak42074/Physical-Verification-using-SKY130/blob/main/DAY_1_LAB/Schematic_simulation.png)

#### Layout Design and Postlayout simulation
- Layout imported from spice file: file -> import spice
![](https://github.com/Deepak42074/Physical-Verification-using-SKY130/blob/main/DAY_1_LAB/spice2mag.png)

- Layout after connecting pins
![](https://github.com/Deepak42074/Physical-Verification-using-SKY130/blob/main/DAY_1_LAB/final_layout.png)

- Postlayout simulation result
![](https://github.com/Deepak42074/Physical-Verification-using-SKY130/blob/main/DAY_1_LAB/Post_layout_simulation.png)

## Day 2 - Design Rule Checks and Layout Vs Simulation

### Fundamentals of Physical Verification

The two primary aspects of physical verification are as follows:

1. Design Rule Checks (DRC)
 * This make sures that the design layout meets all the silicon foundry rules for mask making.
2. Layout vs. Schematic (LVS)
 * This makes sure that the design layout matches a simulatable netlist by  electrical connectivity and number of devices,pins. This matches the design layout to others forms that electrically matches the design and shows electrical description of circuits which is independent of layout.

LVS is based on principle that if we have multiple version of something derived from independent sources then those version can be cross checked to find errors in each other. So the more the independent sources, the more robust result, although LVS uses only two sources:
1. Checking From independent source
* Extracted Layout is compared with schematic netlist or vice versa.

2. Checking From Dependent sources
In the modern practice of automation where chips are designed from a single source (RTL design), the LVS process is the matter of  checking the design through different flows; one starting at the RTL source and working forwards and the other starting at the finished layout and working backwards.

### Layout file formats and GDSII format :

Layout file formats are:
These formats must describe both data (rectangles, subcells, polygons) and metadata (labels, cell boundaries and instance names, etc.) regarding IC layouts. 

1. Caltech Intermediate form (.cif)
2. GDSII stream format
3. Open Artwork System Interchange Standard (OASIS) : It is supposed to form much smalle file than GDS.

The GDSII format is preferred format for mask making. In magic the commands to generate mask data include a mixture of cif and calma. The Layer:purpose pairs distinguishes GDS from other formats. Instead of describing each layer with a name such as DIFF for diffusion, it describes them as a pair of numbers, seperated by a colon (ex. 65:20). Here, one number denotes the layer (such as diffusion, metal1, poly), while the other number denotes the purpose (such as blockage, net, drawing, label, pin, ,etc.). Though, layer:purpose pairs may be inconsistent across foundries.

### Extraction commands Styles and Options in Magic:

The chip layout file formats do not contain much metadata mud that includes any concept of netlist that corresponds to layout.The layout tool must be able to independently generate  the circuit netlist equivalent by looking at mask geometry of the layout. This process is known as extraction.

- Extraction in magic :

 Layout -> Intermediate form -> Netlist

 .mag file -> .ext file -> spice file

There is one ext file per cell in the design. The enumerates all electriced nets in the layout, all the devices (transistors, capacitors, resistors) and all instances of cell, ext file. all connection from cell down to subrell, parasities cap. blw nets.

Netlist -> Simulator -> Data plot


## Day 3 - Design Rule Checking

## Day 4 - Understanding PNR and Physical verification with openlane flow

## Day 5 - Running LVS
LVS and DRC are the main principle forms of sign-off validation before sending a chip for fabrication to the foundry. While the foundry will perform a full DRC on our design, they do not perform LVS, since the foundry has no way of knowing the behaviour/function of our design or what it is supposed to do. Even if our design does not meet LVS, it has the potential to come back from manufacturing just as dead as a chip that fails DRC.

Mostly all LVS tool needs the schematic and layout netlists, and usually, netlists used for this purpose are in .spice format, though any format with gives enough information about the circuit will work just fine (lef/def, verilog, blif, etc). Netgen accepts spice and verilog formats, both of which can be simulated(spice file with ngspice and verilog file with iverilog).

### LVS Netlists Vs Simulation Netlists differnce:

|Netlist for LVS|Netlist for Simulation|
|-|-|
|Devices in design|Devices in design|
|Basic parameters|All parameters|
||Parasitic capacitors|
||Parasitic resistors|
|Nets in design|Nets rewired around parasitic resistors|
||Parasitic Inductors|
||Parasitic mutual inductance|

Magic commands to extract netlists for LVS run, we use the following extraction commands.
```
extract do local
extract all
ext2spice lvs
ext2spice
```
### Running Netgen

Netgen is an extension Tcl/Tk interpreter language, and as such, all netgen commands share Tcl/Tk syntax.

The shell command for running netgen is shown below.

```
netgen -batch lvs "filename1 subcircuit1" "filename2 subcircuit2" setup_file output_file

```
### Lab - Introduction to LVS
We need to first git clone the repo to obtain all files necessary for the this lab.
```
git clone https://github.com/RTimothyEdwards/vsd_lvs_lab.git
```
#### Lab5_1
![](https://github.com/Deepak42074/Physical-Verification-using-SKY130/blob/main/DAY_5_LAB/LAB5_1.1.png)
![](https://github.com/Deepak42074/Physical-Verification-using-SKY130/blob/main/DAY_5_LAB/LAB5_1.2.png)
![](https://github.com/Deepak42074/Physical-Verification-using-SKY130/blob/main/DAY_5_LAB/LAB5_1.3.png)
![](https://github.com/Deepak42074/Physical-Verification-using-SKY130/blob/main/DAY_5_LAB/LAB5_1.4.png)
![](https://github.com/Deepak42074/Physical-Verification-using-SKY130/blob/main/DAY_5_LAB/LAB5_2.1.png)
![](https://github.com/Deepak42074/Physical-Verification-using-SKY130/blob/main/DAY_5_LAB/LAB5_2.2.png)




