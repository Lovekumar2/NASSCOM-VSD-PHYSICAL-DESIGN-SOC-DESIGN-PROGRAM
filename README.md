# NASSCOM-PHYSICAL-DESIGN-SOC-DESIGN-PROGRAM

## Table of Contents
- [Day - 1 Introduction of Open-Source EDA, OpenLane and Sky130 PDK](#day---1-Introduction-of-Open-Source-EDA-OpenLane-and-Sky130-PDK)
- [Day - 2 Introduction of Open-Source EDA, OpenLane and Sky130 PDK](#day---1-Introduction-of-Open-Source-EDA-OpenLane-and-Sky130-PDK)

 

## Day - 1 Introduction of Open-Source EDA, OpenLane and Sky130 PDK


### OPENLANE 
OpenLane is an open-source, end-to-end physical design flow for digital ASICs (Application-Specific Integrated Circuits) in the field of VLSI (Very Large Scale Integration). It is part of the broader OpenROAD project and is designed to be a fully automated, tape-out-ready toolchain for designing digital integrated circuits. OpenLane is used to transform a digital design (described in RTL) into a layout that can be fabricated.

#### Key Features of OpenLane:
**RTL to GDSII Flow:**- OpenLane provides a flow that takes RTL as input and produces GDSII (Graphic Design System II), which is the standard file format for the final layout of the chip.

**Open-Source Tools:** - It integrates several open-source tools such as Yosys (for synthesis), OpenSTA (for static timing analysis), Magic (for layout), KLayout (for layout visualization), and many others.
**Technology-Independent:**- OpenLane is designed to work with various technology nodes, though it is primarily associated with the SkyWater 130nm PDK (Process Design Kit), which is also open-source.
**Customizable Flow:**- Users can customize the flow according to their design needs, with the ability to tweak various parameters and stages of the design process.
**Tape-Out Ready:**- The flow is designed to produce results that are ready for tape-out, meaning the design can be sent to a foundry for manufacturing.
#### Typical Flow in OpenLane:
1. **Synthesis:**- Converting RTL code to a gate-level netlist.
2. **Floorplanning:**- Defining the layout of the chip, including the placement of blocks and the arrangement of IOs.
3. **Placement:**- Placing the synthesized gates on the chip floorplan.
4. **Clock Tree Synthesis (CTS):**- Designing a clock distribution network to meet timing requirements.
5. **Routing:**- Creating the metal connections between gates and blocks.
6. **Signoff:**- Performing final checks, including static timing analysis, design rule checks (DRC), and layout versus schematic (LVS) checks.
7. **GDSII Export:**-Generating the final layout file that can be used for chip fabrication.
OpenLane is significant because it democratizes access to ASIC design, allowing researchers, startups, and hobbyists to design and potentially manufacture custom silicon without relying on expensive proprietary tools.
