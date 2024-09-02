# NASSCOM-VSD-PHYSICAL-DESIGN-SOC-DESIGN-PROGRAM

## Table of Contents
- [Day - 1 Introduction of Open-Source EDA, OpenLane and Sky130 PDK](#day---1-Introduction-of-Open-Source-EDA-OpenLane-and-Sky130-PDK)
- [Day - 2 Good Floorplan vs bad Floorplan and Introduction to library cells](#DAY---2-Good-Floorplan-vs-bad-Floorplan-and-Introduction-to-library-cells) 


### Overview Of QFN-48 Chip (PicoRV32 - A Size-Optimized RISC-V CPU)
VSD Squadron Board: The VSD Board is shown below. Our focus is on the enclosed region containing the "Microprocessor (PicoRV32A-Cpu)," which will be designed using the RTL to GDS flow, progressing from the abstract design level to the fabrication stage.

![image](https://github.com/user-attachments/assets/844ea7fc-f4f4-4353-ae5d-d75a4507d075)

### Introduction to IC Design components and terminologies

![image](https://github.com/user-attachments/assets/26f265f8-3b5a-4942-9655-53be6e8833f0)

![image](https://github.com/user-attachments/assets/bdea7b05-d989-443e-8539-bff0f37a9abd)

### Introduction to RISC-V
RISC-V is an open-source instruction set architecture (ISA) based on the principles of Reduced Instruction Set Computing (RISC). Unlike proprietary architectures, RISC-V is freely available for anyone to use and modify, which has led to its growing popularity across various fields, from embedded systems to high-performance computing.

At its core, RISC-V is designed to be simple and efficient, with a base set of instructions that cover essential operations like arithmetic, logic, memory access, and control flow. This base can be expanded with additional features, such as floating-point arithmetic, atomic operations, and vector processing, depending on the application’s needs.

![image](https://github.com/user-attachments/assets/eae5af87-001d-4a60-85ca-a129f6513c68)

## Day - 1 Introduction of Open-Source EDA, OpenLane and Sky130 PDK


### OPENLANE 
OpenLane is an open-source, end-to-end physical design flow for digital ASICs (Application-Specific Integrated Circuits) in the field of VLSI (Very Large Scale Integration). It is part of the broader OpenROAD project and is designed to be a fully automated, tape-out-ready toolchain for designing digital integrated circuits. OpenLane is used to transform a digital design (described in RTL) into a layout that can be fabricated.
![image](https://github.com/user-attachments/assets/d3531547-1a2e-4cc9-9672-c0b4018be9f3)
<!DOCTYPE html>
<html data-color-mode="light" data-dark-theme="dark" data-light-theme="light">
  <head>
    <title>Render</title>
    
    <meta name="referrer" content="never" />
    <link rel="stylesheet" href="/static/assets/mermaid-5ff900d41fa481ba0234.css"/>
    <script src="/static/assets/mermaidMarkdown-5ff900d41fa481ba0234.js" type="text/javascript"></script>
  </head>
  <body
    class="is-embedded"
    data-render-url="//viewscreen.githubusercontent.com"
    data-github-hostname="github.com"
    data-deploy-env="production"
    data-client-timeout-attempts="30"
    data-github-docs-hostname="https://docs.github.com"
  >
    <div class="render-shell js-render-shell">
      <div class="border-wrap mermaid-view "></div>
    </div>
  </body>
</html>


#### Key Features of OpenLane:
1. **RTL to GDSII Flow:**- OpenLane provides a flow that takes RTL as input and produces GDSII (Graphic Design System II), which is the standard file format for the final layout of the chip.

![image](https://github.com/user-attachments/assets/7a7f032d-7d7b-46f5-a4f7-2c72c91f2400)

2. **Open-Source Tools:** - It integrates several open-source tools such as Yosys (for synthesis), OpenSTA (for static timing analysis), Magic (for layout), KLayout (for layout visualization), and many others.
3. **Technology-Independent:**- OpenLane is designed to work with various technology nodes, though it is primarily associated with the SkyWater 130nm PDK (Process Design Kit), which is also open-source.
4. **Customizable Flow:**- Users can customize the flow according to their design needs, with the ability to tweak various parameters and stages of the design process.
5. **Tape-Out Ready:**- The flow is designed to produce results that are ready for tape-out, meaning the design can be sent to a foundry for manufacturing.
#### Typical Flow in OpenLane:
1. **Synthesis:**- Converting RTL code to a gate-level netlist.

 ![image](https://github.com/user-attachments/assets/2c619ac7-5117-48aa-92f1-516a3f191dc1)

2. **Floorplanning:**- Defining the layout of the chip, including the placement of blocks and the arrangement of IOs.
 ![image](https://github.com/user-attachments/assets/3581a3b6-24aa-49e8-8632-5a3e8de32f74)

3. **Placement:**- Placing the synthesized gates on the chip floorplan.
 ![image](https://github.com/user-attachments/assets/4d947db7-68e4-40ae-ad60-fabf697abd43)

4. **Clock Tree Synthesis (CTS):**- Designing a clock distribution network to meet timing requirements.

   
 ![image](https://github.com/user-attachments/assets/64904d1c-1c2e-4820-ba7c-e2d86367aa7e)

5. **Routing:**- Creating the metal connections between gates and blocks.
 ![image](https://github.com/user-attachments/assets/2dd57219-bae8-4afd-b4f8-54d695ed71f0)

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
### What is ABC (Algorithm for Boolean Circuits) ?
- ABC is an academic software tool used for the synthesis and verification of Boolean circuits. It integrates various algorithms for logic synthesis, technology mapping, and optimization. ABC is often used in the research community for experimenting with new algorithms and techniques in logic synthesis and formal verification.
- 
### RTL2GDS OpenLANE ASIC Flow Practical Implementation

#### LAB-1
##### Steps to Use OpenLane in Interactive Mode
###### 1. Setup OpenLane Environment:
First, ensure that OpenLane is properly installed and that you have the necessary tools and libraries available.
###### 2. Start the Docker Container:
- OpenLane operates within a Docker container. You can start the container using the following command:
```bash
  make mount
```
- This command mounts your current directory into the Docker container and drops you into an interactive shell.
###### 3. Initialize the Design:
- Once inside the container, you need to prepare your design for the flow. This typically involves setting up the design directory and copying your RTL code into it.
- Use the following command to start an interactive session for your design:
```bash
./flow.tcl -interactive
```
- This command will start OpenLane in interactive mode.
###### 4. Run Individual Flow Stages:
- In interactive mode, you can manually execute each step of the ASIC design flow. Common steps include:

  
  Synthesis:
   ```bash
   run_synthesis
   ```
  Floorplanning:
   ```bash
   run_floorplan
   ```
  Placement:
    ```bash
   run_placement
    ```
  Clock Tree Synthesis (CTS):
   ```bash
   run_cts
    ```
  Routing:
    ```bash
   run_routing
    ```
  Signoff:
   ```bash
   run_signoff
   ```
###### 5. Inspect and Modify Intermediate Results:
- After each step, you can inspect the results, check logs, and adjust parameters as needed. This level of control allows you to optimize the design or troubleshoot issues before proceeding to the next step.
###### 6. Generate Final GDSII File:
- Once all steps are successfully completed, you can generate the final GDSII file, which is the format required for fabrication:
  ``` bash
  run_magic
  ````
- This step involves running DRC (Design Rule Check), LVS (Layout vs. Schematic), and generating the final layout.
  
![Screenshot from 2024-08-22 17-41-01](https://github.com/user-attachments/assets/bbdc48bc-b228-4819-9db6-d7feaa73d3b9)

To run in interactive mode 
 command will be 
 ```bash
bash-4.2$ ./flow.tcl -interactive
 ```
package import and check
```bash
% package require openlane
```
prepare for the design run the command 
```bash
% prep -design picorv32a
```
command for synthesis 
```bash
 % run_synthesis 
```

![Screenshot from 2024-08-22 18-43-04](https://github.com/user-attachments/assets/3bb4b134-afdc-42f3-97bc-4bee082626d2)

![Screenshot from 2024-08-22 18-43-17](https://github.com/user-attachments/assets/2c3ca1da-b5b9-4837-800e-2b750ac17aa7)
###### D Flip-Flop Ratio
Now we will find the flip flop ratio
```bash
flop ratio =(total no. of d flop realised) / (total no. cells)
           = 1613/14876
           = 0.10842
```


![Screenshot from 2024-08-22 18-13-40](https://github.com/user-attachments/assets/a6be1ca5-842b-4431-a771-784ba144fc95)

# Day - 2 Good Floorplan vs bad Floorplan and Introduction to library cells

## Utilization factor and Aspect ratio of a chip or die:

The utilization factor and aspect ratio are critical metrics in chip or die design and fabrication:

**Utilization Factor:**
- **Definition:**  The utilization factor, often referred to as area utilization, is a measure of how efficiently the available area on a chip or die is used by the actual logic, memory, and other functional components. It is calculated as the ratio of the area occupied by the functional elements to the total available area of the chip.
Formula:
Utilization Factor = (Area Occupied by Functional Components/Total Chip Area)×100 %

- Importance: A higher utilization factor indicates that more of the chip's area is used for functional purposes, which is generally desirable for cost efficiency. However, it needs to be balanced with considerations like routing space, power distribution, and thermal management.

**Aspect Ratio:**
- **Definition:** The aspect ratio of a chip or die refers to the ratio of its width to its height. It is an important parameter in the physical design and packaging of semiconductor devices.
Formula:
Aspect Ratio = Height of the Chip/Width of the Chip

 
- Importance: The aspect ratio affects the chip's mechanical stability, ease of packaging, and manufacturability. Ideally, the aspect ratio should be close to 1 (i.e., the chip is nearly square), as this minimizes stress and simplifies the packaging process. However, depending on the application and design constraints, the aspect ratio may vary.


![Screenshot 2024-08-24 221207](https://github.com/user-attachments/assets/c41d2c60-621c-4e05-a93e-bfe2dc929d52)

**Concept of pre-placed cells and de-coupling capacitors:**
- **Pre-placed Cells:**
Pre-placed cells are components or functional units within an IC or on a PCB that are placed at specific locations before the main placement and routing process begins. These cells are typically used for power management, signal integrity, or other critical functions that require precise positioning to meet design constraints. Pre-placed cells can include decoupling capacitors, power pads, voltage regulators, or other components that are essential for the proper functioning of the circuit.

- **Decoupling Capacitors:**
Decoupling capacitors are small-value capacitors placed between the power supply rails (Vcc and Gnd) of an integrated circuit or on a PCB to provide a local source of energy that can supply transient current demands of the active devices. They help to "decouple" the local power supply from the rest of the circuit, ensuring that rapid changes in current demanded by one component do not affect the supply voltage of other components.

![image](https://github.com/user-attachments/assets/e150ba66-28c5-4678-abab-5ddfd327764a)

**Run Floorplan**
```bash
run_floorplan
```
![Screenshot from 2024-08-30 21-50-33](https://github.com/user-attachments/assets/7c5ccc63-ce5e-4c6c-8729-c41e0280defb)

![Screenshot from 2024-08-30 21-50-41](https://github.com/user-attachments/assets/33a247a0-b421-4293-ab8f-07d3bc7e0b3d)

**Picorv32a floorplan def file:**


![Screenshot from 2024-08-30 22-01-51](https://github.com/user-attachments/assets/00e525ea-022c-497c-99cc-4b920998e174)

![Screenshot from 2024-08-30 21-59-56](https://github.com/user-attachments/assets/961be1a5-bba4-4001-b640-c6759e889625)



**magic tool tech file and the layout of design:**

![image](https://github.com/user-attachments/assets/6dca3660-2c4f-4a22-af12-54d79e50e14a)


**Centering the Design:**

Press ``` S ``` to select the entire design.

Press ``` V ``` to vertically align it to the middle of the screen.

**Zooming In on a Specific Area:**

Left-click and drag to select the desired region.

Right-click to bring up the context menu.

Press``` Z ``` to zoom in on the selected area.


**Getting Details of a Cell:**

Move your cursor to the cell of interest.

Press ``` S ``` to select the cell.

In the tkcon window, enter the command "what" to display cell details.

![image](https://github.com/user-attachments/assets/680be45e-a6b5-419e-93d0-5be3b2322120)


## Placement in VLSI Design
Placement plays a crucial role in VLSI (Very Large Scale Integration) design. It involves determining the physical locations of standard cells or logic elements within a chip or block. Let's break it down:

- **Global Placement:**

  - Global placement assigns general locations to movable objects (cells).
  - Some overlaps between placed objects are allowed during this stage. 
  - The goal is to achieve a rough layout that satisfies area constraints.

- **Detailed Placement:**

  - Detailed placement refines the object locations obtained from global placement.
  - It enforces non-overlapping constraints and ensures that cells are placed on legal cell sites.
  - The quality of detailed placement significantly impacts subsequent routing stages.

``` magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.placement.def & ```


![Screenshot from 2024-08-26 18-16-10](https://github.com/user-attachments/assets/8051e35b-b5b8-43b1-9d4d-7a1f1dc5838a)




![Screenshot from 2024-08-26 18-04-15](https://github.com/user-attachments/assets/ee8746ed-8c5d-429f-a0b1-4f8b11288677)
![Screenshot from 2024-08-26 18-11-42](https://github.com/user-attachments/assets/e8130182-c3f6-4658-8d2b-ad2b5f3b6385)
![Screenshot from 2024-08-26 18-12-21](https://github.com/user-attachments/assets/590e4e06-9d00-45be-bbe2-59636d6a5f11)
![Screenshot from 2024-08-26 18-17-47 - 1](https://github.com/user-attachments/assets/504c7df1-f5b8-43c1-8a97-6417500c9818)
![Screenshot from 2024-08-30 00-52-21](https://github.com/user-attachments/assets/d4e6b92f-5dae-497f-84f7-3a6d188b2104)
![Screenshot from 2024-08-30 00-52-45](https://github.com/user-attachments/assets/ab407d82-8158-4a4c-b869-35595199bda4)
![Screenshot from 2024-08-30 00-53-29](https://github.com/user-attachments/assets/d717b8f6-447c-426b-b2a5-62616e1e8969)
![Screenshot from 2024-08-30 00-53-39](https://github.com/user-attachments/assets/2d5e063a-973e-4410-a480-81a8d89c5897)
![Screenshot from 2024-08-30 01-24-03](https://github.com/user-attachments/assets/723cd9e0-1aa9-4fd9-a699-1ddefbb5ce8d)
![Screenshot from 2024-08-30 02-00-12](https://github.com/user-attachments/assets/088d4da2-422b-407a-bdfc-094536a22721)
![Screenshot from 2024-08-30 02-00-27](https://github.com/user-attachments/assets/d6c60066-e5c0-43b7-9e4d-9efe9f505848)
![Screenshot from 2024-08-30 02-01-16](https://github.com/user-attachments/assets/e1f56ef9-bd52-4a00-8b76-d7c81801f534)
![Screenshot from 2024-08-30 18-58-52](https://github.com/user-attachments/assets/353485dc-7745-4416-bce2-7af8d8d7ea1b)
![Screenshot from 2024-08-30 18-59-06](https://github.com/user-attachments/assets/53403cfd-6548-448a-ae2d-bee4f615adf3)
