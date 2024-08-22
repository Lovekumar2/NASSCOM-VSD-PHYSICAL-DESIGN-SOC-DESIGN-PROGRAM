# NASSCOM-PHYSICAL-DESIGN-SOC-DESIGN-PROGRAM

## Table of Contents
- [Day - 1 Introduction of Open-Source EDA, OpenLane and Sky130 PDK](#day---1-Introduction-of-Open-Source-EDA-OpenLane-and-Sky130-PDK)


## Day - 1 Introduction of Open-Source EDA, OpenLane and Sky130 PDK


### OPENLANE 
OpenLane is an open-source, end-to-end physical design flow for digital ASICs (Application-Specific Integrated Circuits) in the field of VLSI (Very Large Scale Integration). It is part of the broader OpenROAD project and is designed to be a fully automated, tape-out-ready toolchain for designing digital integrated circuits. OpenLane is used to transform a digital design (described in RTL) into a layout that can be fabricated.

#### Key Features of OpenLane:
1. **RTL to GDSII Flow:**- OpenLane provides a flow that takes RTL as input and produces GDSII (Graphic Design System II), which is the standard file format for the final layout of the chip. 
2. **Open-Source Tools:** - It integrates several open-source tools such as Yosys (for synthesis), OpenSTA (for static timing analysis), Magic (for layout), KLayout (for layout visualization), and many others.
3. **Technology-Independent:**- OpenLane is designed to work with various technology nodes, though it is primarily associated with the SkyWater 130nm PDK (Process Design Kit), which is also open-source.
4. **Customizable Flow:**- Users can customize the flow according to their design needs, with the ability to tweak various parameters and stages of the design process.
5. **Tape-Out Ready:**- The flow is designed to produce results that are ready for tape-out, meaning the design can be sent to a foundry for manufacturing.
#### Typical Flow in OpenLane:
1. **Synthesis:**- Converting RTL code to a gate-level netlist.
2. **Floorplanning:**- Defining the layout of the chip, including the placement of blocks and the arrangement of IOs.
3. **Placement:**- Placing the synthesized gates on the chip floorplan.
4. **Clock Tree Synthesis (CTS):**- Designing a clock distribution network to meet timing requirements.
5. **Routing:**- Creating the metal connections between gates and blocks.
6. **Signoff:**- Performing final checks, including static timing analysis, design rule checks (DRC), and layout versus schematic (LVS) checks.
7. **GDSII Export:**-Generating the final layout file that can be used for chip fabrication.
OpenLane is significant because it democratizes access to ASIC design, allowing researchers, startups, and hobbyists to design and potentially manufacture custom silicon without relying on expensive proprietary tools.
### Process Design Kit (PDK)
A Process Design Kit (PDK) is a collection of resources provided by semiconductor foundries to help chip designers create integrated circuits (ICs) that are compatible with a specific manufacturing process. It includes detailed information about the process technology, such as design rules, standard cell libraries, simulation models, and technology files that describe how the physical layers of the chip should be constructed.
### Role Of PDK In ASIC Design
The Process Design Kit (PDK) plays a crucial role in ASIC (Application-Specific Integrated Circuit) design, serving as the bridge between the semiconductor manufacturing process and the design tools used by engineers to create custom integrated circuits. 
#### Key Roles of PDK in ASIC Design:
##### 1. Technology Representation:
- The PDK encapsulates all the technology-specific details of a semiconductor process. This includes the process nodes (e.g., 130nm, 65nm, 28nm, etc.), device models, design rules, and parameters specific to the fabrication technology.
- It allows ASIC designers to understand and apply the physical characteristics and constraints of the manufacturing process when designing their circuits.
##### 2. Standard Cell Libraries:
- PDKs include libraries of pre-designed and verified standard cells, such as logic gates, flip-flops, and other basic building blocks. These cells are optimized for the specific manufacturing process and are used extensively in the design of ASICs.
- Designers can use these cells to construct more complex circuits, ensuring that their designs will be manufacturable and meet the desired performance criteria.
##### 3. Design Rule Checking (DRC) and Layout Versus Schematic (LVS):
- The PDK provides the design rules required to check the layout for manufacturability. These rules ensure that the physical design adheres to the manufacturing constraints, preventing issues that could arise during fabrication.
- It also includes information for LVS checks, which ensure that the layout corresponds accurately to the intended circuit design. This step is critical for verifying that the design will function as expected after fabrication.
  ###### Design Rule Checking (DRC)
  - DRC is a verification process that checks whether the physical layout of an IC adheres to a set of design rules provided by the semiconductor foundry. These rules define the minimum and maximum dimensions, spacing, and alignment of various features on the chip, such as metal layers, vias, and transistors. The design rules are critical for ensuring that the chip can be reliably manufactured and will function correctly
###### Layout Versus Schematic (LVS)
- LVS is a verification process that compares the netlist extracted from the physical layout with the original schematic netlist to ensure that they match. The schematic represents the intended electrical connections and behavior of the circuit, while the layout represents the actual physical implementation of that design on the chip.
##### 4. Device Models for Simulation:
- PDKs include SPICE (Simulation Program with Integrated Circuit Emphasis) models for transistors and other devices. These models are used in simulation tools to predict the electrical behavior of circuits before they are fabricated.
##### 5.Process-Specific Design Automation:
- PDKs are tightly integrated with Electronic Design Automation (EDA) tools, enabling automated processes like place-and-route, timing analysis, and power optimization. The PDK ensures that these tools are calibrated for the specific process technology.
### What is .LEF File ?
- A LEF (Library Exchange Format) file is a standard file format used in the semiconductor industry to describe the physical aspects of standard cells, macros, and other components in a design. LEF files are crucial for the place-and-route (P&R) stage of ASIC and FPGA design, where the physical layout of a chip is finalized.The information in a LEF file helps design tools understand the physical constraints and characteristics of the cells, which allows for efficient placement and routing of the components on a silicon wafer.
