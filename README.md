# DIGITAL VLSI SOC DESIGN AND PLANNING 
Hello, everyone! I'll be sharing what I have learned during a 2 weeks of workshop on Digital VLSI SOC design and planning using openLANE tool and sky-130nm PDK under the guidance of Kunal Ghosh, VLSI System Design(VSD) pvt.ltd.

## Day 1 -Inception of open-source EDA, OpenLANE and sky130 PDK

## How to talk to computers
### Introduction to QFN-48 Package, chip, pads, core, die and IPs

ARDUINO BOARD: Lets start with an  arduino board, the encircled area is a microcontroller chip. to design such chip or IC we have to follow the ASCI design flow.
![01 06 2024_19 11 14_REC](https://github.com/VIJAYAKUMARAHS/VSD-SoC_Design_and_Planning_Program/assets/89599199/14c33535-27d0-4951-8e70-422a6fb93d3b)

chip architecture 
![01 06 2024_19 29 15_REC](https://github.com/VIJAYAKUMARAHS/VSD-SoC_Design_and_Planning_Program/assets/89599199/a5d5897c-74a0-4c4b-b0e1-cb4186923e32)

Post chip fabrication the chip is in the form of die then we package that die in to required package form.
Package: QFN 48 quad flat No leads
![01 06 2024_19 33 30_REC](https://github.com/VIJAYAKUMARAHS/VSD-SoC_Design_and_Planning_Program/assets/89599199/6d523206-9dd8-483a-861a-b2e638e7c827)

![01 06 2024_19 42 57_REC](https://github.com/VIJAYAKUMARAHS/VSD-SoC_Design_and_Planning_Program/assets/89599199/66f28906-d9da-4952-a27a-f39f96136841)


![01 06 2024_19 45 35_REC](https://github.com/VIJAYAKUMARAHS/VSD-SoC_Design_and_Planning_Program/assets/89599199/e2361841-3394-4612-9fa7-51629326378b)

CORE: Where we place the IPs, Macro and standard cell.

DIE: the size of an entire chip area

PADS: this is where we are giving signal in and take out and also we place protection circuit here. when comes to full chip level design we say pads, when comes to block level design we say ports.

#### Sample SOC look like

![01 06 2024_19 56 09_REC](https://github.com/VIJAYAKUMARAHS/VSD-SoC_Design_and_Planning_Program/assets/89599199/5df9da25-909c-4971-b17b-05eb9599487e)

Foundry: where chip are fabricated.

![01 06 2024_19 59 04_REC](https://github.com/VIJAYAKUMARAHS/VSD-SoC_Design_and_Planning_Program/assets/89599199/b56ea874-f46d-41e6-a27d-a5de449530b7)

Foundry look like (smale setup:IIT Bombay)

![01 06 2024_20 01 22_REC](https://github.com/VIJAYAKUMARAHS/VSD-SoC_Design_and_Planning_Program/assets/89599199/51d5fda1-155a-43b9-ab41-69c40cc3083b)

### Introduction to RISC-V
RISC architecture that were developed at the University of California, Berkeley. RISC is an open standard instruction set architecture (ISA) based on established RISC principles. Unlike most other ISA designs, RISC-V is provided under open source licenses that do not require fees to use. A number of companies are offering or have announced RISC-V hardware, open source operating systems with RISC-V support are available, and the instruction set is supported in several popular software toolchains.
![01 06 2024_20 12 29_REC](https://github.com/VIJAYAKUMARAHS/VSD-SoC_Design_and_Planning_Program/assets/89599199/fdda8d67-121b-4195-9c81-3e3ea5755f87)

![01 06 2024_20 15 52_REC](https://github.com/VIJAYAKUMARAHS/VSD-SoC_Design_and_Planning_Program/assets/89599199/ae32e585-a1df-4cc6-9879-61df378cae9b)

### From Software Applications to Hardware
Application Software - System Software - Hardware chip

Application software are enters into system software and system sodtware converts the entire program into binary language.

*Operating System, Compiler, Assemblers*

Operating system handles input/output operations and allocate memory also it manage the low level system functions.

Compiler takes the output from the operating system as programming languages such as C,C++,Java and convert them into intsructions. These instructions depends upon hardware.

Assembler take the instructions from compiler and convert them into binary numbers. This binary language send to hardware and hardware performs ouput based on the function.

Instruction acts as abstract interface between C-language and the hardware.

![01 06 2024_20 25 44_REC](https://github.com/VIJAYAKUMARAHS/VSD-SoC_Design_and_Planning_Program/assets/89599199/a5d78a15-635b-4087-ad1f-7bd743b28e04)

![01 06 2024_20 27 55_REC](https://github.com/VIJAYAKUMARAHS/VSD-SoC_Design_and_Planning_Program/assets/89599199/a1e745b2-cbbd-4693-a3d9-8c1ff2858bac)

![01 06 2024_20 29 25_REC](https://github.com/VIJAYAKUMARAHS/VSD-SoC_Design_and_Planning_Program/assets/89599199/e113f08c-6cdb-47cb-93f2-6b53e86cf77e)

## Soc design and OpenLANE
## Introduction to all components of open-source digital asic design

![01 06 2024_21 55 53_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/a16927a9-87f6-4e8a-a5c6-4f886167788a)

To design ASIC chips, few tools or things required. Those are

**RTL Design:**  register-transfer level (RTL) is a design abstraction which models a synchronous digital circuit. for this designs many open sorces are available. like, librecores.org, opencores.org, github.com, etc...

**EDA tools:** The term Electronic Design Automation (EDA) refers to the tools that are used to design and verify integrated circuits (ICs). open sorces tools are available like Qflow, OpenROAD, OpenLANE, etc.
 

**PDK data:** PDK is process design kit. It is interface between FAB and design.  

 process design rules: DRC, LVS, REX Digital standerd cell libreries i/o librerirs etc..... which are used to model a fabrication process for the EDA tools used to design an ICs.

![01 06 2024_22 07 37_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/cb3169cb-0c7a-40f5-9fb7-b61f11fddaf9)
### Is 130nm is old
![01 06 2024_22 09 16_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/d41f621e-f3dc-49a1-9013-3bbbe4214cf7)

 ## Simplified RTL2GDS flow

 ![01 06 2024_22 12 03_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/c7ad05be-b772-4b20-8109-d9e9b9eed973)

 **Step 1: Synthesis:-** Synthesis is a process of converting RTL(writen in verilog or VHDL) to gate level netlist.
 ![01 06 2024_22 35 37_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/230186f6-214d-407c-8558-942e4f0bed52)

 **Step 2: Floor planning and Power planning:-** Floorplanning is the process of creating core area, specifying core to I/O boundary spacing, standard cell rows, placing I/O pins, placing macros using macro guidelines and adding placement blockages and halo.

![01 06 2024_22 40 15_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/e0428a1b-c48d-4d2d-845d-f57011bfd087)

![01 06 2024_22 46 20_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/63a34a9a-99f7-4c8e-a72b-80b37d3baf67)

*Power planning:* means to provide power to the every macros, standard cells, and all other cells are present in the design. Power and Ground nets are usually laid out on the metal layers. In this create power and ground structure for both IO pads and core logic.

![01 06 2024_22 48 03_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/6f0d29c3-de7e-478c-b10e-974a4657536c)


**Step 3: Placement:-** Placement is the process of find the best place to place the standard cells in core area with less congestion, less timing violations and less DRV's.

![01 06 2024_22 50 07_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/3abb1603-694b-4055-8e7c-b3342e978501)

*There are two steps in placement*

**1. Global placement:-** It is very first stage of the placement where cells are placed inside the core area for the first time looking at the timing and congestion.
**2.Detailed placement:-** In detailed placements, we determined the exact route and layers for each netlist. the objective of detailed placement is valid routing, minimize area and meet timing constrains.

![01 06 2024_23 05 38_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/f332b681-156b-425f-8f91-691cd33e42d3)

**Step 4: Clock Tree Synthesis:-** We have to route the clock. In the process of clock synthesis, we have distribute the clock to the every sequential elements. for example flipflops, registers, ADC, DAC ete. basically clock netwroks looks likes a tree. To minimize the clock skew by using the low-skew global routing resources for clock signals. Usually a tree is a H tree, X tree, fishbone tree etc.

![01 06 2024_23 07 55_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/cbde64ff-d120-44bb-905c-7837a061b463)

![01 06 2024_23 12 51_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/3ac93b7a-63c8-485e-9d96-344a3a8183c5)

**Step 5: Routing:-** Making physical connections between signal pins using metal layers are called Routing. Routing is the stage after CTS and optimization where exact paths for the interconnection of standard cells and macros and I/O pins are determined. 

The sky130 PDK defines the 6 routing leyers. the lowest leyer is called local interconnect layer (titanium nitride layer). Other five layers are alluminium layersIn the proccess of routing, metal trackes forms a routing grids and these grids are huge. so, devide and conquer approach is use for routing.
![01 06 2024_23 16 51_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/2ae21bfd-4950-4218-9c6f-2c801a32edfd)

**Step 6: Sign Off:-** After the routing is completed. we started 

Physical verification: DRCs, LVS, ERC.

Timing Verification: Here Static Timing Analysis will done.


### Introduction to OpenLANE and Strive chipsets

OPENLANE is an automated RTL to GDSII flow tool and its composed of several tools such as OpenROAD, Yosys, Magic, Netgen, Fault, CVC SPEF-Extractor, CU-GR, Klayout and a number of scripts used for design exploration and optimization. 

![01 06 2024_23 28 01_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/c55b5961-2a00-4fed-a70d-f6d19eaeea8a)

striVe SoC Family

![01 06 2024_23 30 33_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/dac9efbf-c9ee-4215-90b0-314bdffaeeaf)

The main goal of OPENLANE is to produce a clean GDSII with no human intervation.

No LVS violations

No DRC Violations

No timing Violations

It has 43 design examples with their best configurations.

## Introduction to OpenLANE detailed ASIC design flow

The flow start with RTL and ends with GDSII. OpenLANE is a completely automated RTL to GDSII flow which embeds in it different opensource tools, namely, OpenROAD, Yosys, ABC, Magic etc.,

![01 06 2024_23 36 17_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/6566ae2b-33e3-405c-82b6-030a2b0aeb13)

![01 06 2024_23 42 31_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/9564692c-4a2a-4c1c-9c5e-f0a04085271e)

**Dealing with Antenna violations**

when a metal wire segment is fabricated, it collect charges which can demaged the transister gates during the fabrication.

![01 06 2024_23 45 57_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/eb450a2a-e841-4b81-9e1f-6f03642b2452)

**Solutions**

![01 06 2024_23 54 16_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/bdb50f45-71b6-459b-9bb4-2b2f184cfccf)

With OpenLANE, we took a preventive approach. here we add fake antenna diode next to every cell input after placement. Then run the Antenna checker on the routed layout. If the checker reports a violation on cell input pin, replace the fake diode cell by a real one.

![01 06 2024_23 59 24_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/0bb25b6f-2eec-4274-ae23-0e78d5b2c403)

Static Timing analysis(STA) It involves the interconnect RC Extraction(DEF2SPEF) from the routed layout, followed by STA on OpenSTA(OpenROAD) tool. resulting report will shows the timing violations if any violations is there.

Physical Verification (DRC and LVS) Magic is used for design Rules checking and SPICE Extraction from Layout. Magic and Netgen are used for LVS.





## Get familiar to open-source EDA tools

### OpenLANE Directory structure in detail
#### NOTE:- Before jump in to this session we must install linux Ubuntu 18.04 using VirtualBox in your machine.

**Lets look at some basic LINUX Commands:**
1. **ls** - The most frequently used command in Linux to list directories
2. **pwd** - Print working directory command in Linux
3. **cd** - Linux command to navigate through directories
4. **mkdir** - Command used to create directories in Linux
5. **mv** - Move or rename files in Linux
6. **cp** - Similar usage as mv but for copying files in Linux
7. **rm** - Delete files or directories
8. **touch** - Create blank/empty files
9. **ln** - Create symbolic links (shortcuts) to other files
10. **clear** - Clear the terminal display
11. **cat** - Display file contents on the terminal
12. **echo** - Print any text that follows the command
13. **less** - Linux command to display paged outputs in the terminal
14. **man** - Access manual pages for all Linux commands
15. **uname** - Linux command to get basic information about the OS
16. **whoami** - Get the active username
17. **tar** - Command to extract and compress files in linux
18. **grep** - Search for a string within an output
19. **head** - Return the specified number of lines from the top
20. **tail** - Return the specified number of lines from the bottom
21. **diff** - Find the difference between two files
22. **cmp** - Allows you to check if two files are identical
23. **comm** - Combines the functionality of diff and cmp
24. **sort** - Linux command to sort the content of a file while outputting
25. **export** - Export environment variables in Linux
26. **zip** - Zip files in Linux
27. **unzip** - Unzip files in Linux
28. **ssh** - Secure Shell command in Linux
29. **service** - Linux command to start and stop services
30. **ps** - Display active processes
31. **kill and killall** - Kill active processes by process ID or name
32. **df** - Display disk filesystem information
33. **mount** - Mount file systems in Linux
34. **chmod** - Command to change file permissions
35. **chown** - Command for granting ownership of files or folders
36. **ifconfig** - Display network interfaces and IP addresses
37. **traceroute** - Trace all the network hops to reach the destination
38. **wget** - Direct download files from the internet
39. **ufw** - Firewall command
40. **iptables** - Base firewall for all other firewall utilities to interface with
41. **apt, pacman, yum, rpm** - Package managers depending on the distribution
42. **sudo** - Command to escalate privileges in Linux
43. **cal** - View a command-line calendar
44. **alias** - Create custom shortcuts for your regularly used commands
45. **dd** - Majorly used for creating bootable USB sticks
46. **whereis** - Locate the binary, source, and manual pages for a command
47. **whatis** - Find what a command is used for
48. **top** - View active processes live with their system usage
49. **useradd and usermod** - Add a new user or change existing user data
50. **passwd** - Create or update passwords for existing users


**checking the required files**: 
we are working in openlane_working_dir
explore about PDK
**PDK** is process design kits openlane is works with Sky130_fd_sc_hd PDK, sky130" is process name or node name."fd" is a foundary name (skyWater foundary)."sc" means standerd cell librery files and the last one "hd" stands for high density

Sky130_fd_sc_hd varient contains many technology files like verilog, spice, techlef, meglef,mag,gds,cdl,lib,lef,etc.

![02 06 2024_17 04 54_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/990eb573-3741-43d4-aa5b-fa9d649cd647)

Sky130_fd_sc_hd PDK

![02 06 2024_17 27 06_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/7e28a812-070f-4076-8db2-09ae2251e01a)

Lets explore all related files

![02 06 2024_17 45 50_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/d00d450c-6af0-4e54-a0c5-a556400660c4)

### Design Preparation Step

We have to enter in to the openlane path, type docker after 
Here we use flow.tcl file to open the tool in interactive mode

![02 06 2024_18 01 34_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/1924f29c-a16f-4854-8794-c52f8000c7d1)

above i missed - here

![02 06 2024_18 02 44_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/3d1d816d-3a34-4d6c-ad7c-bcb94541ebd4)

Now we have to input the required packages

![02 06 2024_18 08 16_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/0a5b0971-8a71-4da4-9a54-1088bd1a2e46)

Now its ready for the commands

here we are opening the picorv32a.v design

![02 06 2024_18 12 01_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/8f6a0388-12ea-4996-95eb-9d2a06d739f2)
Here we can see that the time period is set to the 5.00 nsec.

![02 06 2024_18 14 10_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/bac74b8a-6cc6-4e20-941a-050711f1cba0)

we see in the openlane sky130_fd_sc_hd folder, the period is set about 24 nsec. so it is not override to the main file. If it override then give first priority to the main folder.

![02 06 2024_18 23 30_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/5eb504c8-0b2b-41f6-966e-ed3dd7e55068)


we have to prepare design setup stage. for that command is prep -design picorv32a

![02 06 2024_18 27 06_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/3f1a8ad8-4412-4157-933d-66c8556f62ef)
its merging the two lef files
The above image shows the preparation complete

### Review files after design prep and run synthesis

After completing the preparation, in the picorv32a file, the run terictory is created. Inside the folder, Today's date is created.

![02 06 2024_18 34 13_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/a5e76340-56f6-4009-96c7-167db08e7149)

![02 06 2024_18 37 48_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/ec5a5066-dca9-4451-b392-0101cdcf6caa)

Merged .lef content's

![02 06 2024_18 40 06_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/72f5f875-14e8-4e86-83eb-a760054a8272)

 In the result folder is empty because till we have not run anything and in the report folder all the folders are there about synthesis, placement, floorplanning,cts,routing,magic,lvs.

 now here also one config.tcl file is available similar like design folder. But this config.tcl file contains all default parameter taken by the run.

 Now coming to the openlane, we are going to run the synthesis. for that command is run_synthesis It will take some 5 mnts to run the synthesis and finally synthesis will complited.

 ![02 06 2024_18 56 31_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/af838681-bb03-4a41-a8f9-8bc077592b22)



### OpenLANE Project Git Link Description

About efabless openlane git repo and how github is helpfull to handle the data.

https://github.com/efabless/openlane

![02 06 2024_19 54 55_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/7efb6c45-4561-4487-bd3e-fae09b4fda29)


Video source


![02 06 2024_20 18 34_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/4195bca9-cbc7-4a99-a121-9232c013349b)



### Steps to characterize synthesis results



In the bellow image i marked the total number of cells 14876 and D ff is 1613.

![02 06 2024_20 32 07_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/162b3581-2e19-4305-b303-55912acfc99e)
 
flop ratio = number of flip flops/number of total cell

D flipflops = 1613,
total cells = 14876

flop ratio = 1613/14876 =0.1084*100 = 10.84%




 
# Day 2 - Good floor planning considerations

### Chip Floor planning consideration: 

### Utilization factor and aspect ratio

In this section lets cover the width and hight of the floor plan. this the first step toword the Physical design.

![03 06 2024_09 20 49_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/fd3828b0-1899-46f8-b9cd-600dc9fd504c)

Begin with a netlist, netlist is two flipflops and have a simple combination logic in between.

![03 06 2024_09 23 23_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/60203070-9c8b-4ccb-901d-037e1153c555)

All the combinational and sequential are taking in to rectangle shape

![03 06 2024_09 26 27_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/9d1627d1-c643-4f4e-9013-be1f034c607f)

standard cell have dimensions of 1unit*1unit

So, area= 1 Sq. units

Asuume same area for the flipflop as well = 1 Sq. units


![03 06 2024_09 28 46_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/cc387ce9-10b3-49b5-a257-3086f1069dd8)

what is CORE and DIE section of a chip

![03 06 2024_09 32 25_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/30bfe5d7-ac14-4868-ae5b-23c0c20057a7)

Let's try to place that particular logic inside the core. The netlist will occupy the whole area inside the core it means it utilizes the core 100%.

![03 06 2024_09 36 02_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/9efa7f20-12ec-4244-b2a9-f7682508ca06)

Utilization factor

![03 06 2024_09 38 13_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/dfc3e09e-73da-4ee7-be26-5c4b7d05bfa6)

![03 06 2024_09 39 03_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/daa6bf06-c3b5-4d29-8c24-fb257f84f64c)

Utilization Factor = Area occupied by netlist / Total area of the core
   
 lets put the dimensions we have, we get
 
 Utilization factor = 4*1sq.unit / 2unit *2unit
 
		= 4sq unit /  4sq unit

  Aspect ratio is 1. its represents your design is square shape, if aspect reatio is other than 1 your design is rectangle shape.

  lets look at utilization factor is 0.5

  ![03 06 2024_09 45 01_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/f9506dfa-034d-4393-bf46-b2bf344e8912)

Now lets look at the 25% utilization factor and aspect ratio is 1

![03 06 2024_09 51 20_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/8a09a5d8-2d65-4cd6-958c-7c98609b6eca)

when comes to industrial projects they prefer 60% to 70% utilization and remaining 30 to 40% for the next procedure. and again its depending on the project.




  ### Concept of pre-placed cells


  Define loctions of pre placed cells

  Lets take a combinational logic which does some amount of function.
  Cut them in to two parts
  now, there two blocks and these are implemented separately.

  ![03 06 2024_10 00 08_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/473d3cc2-b28f-44a0-8cf0-5214e68b821c)

  lets separate this in to two different black box. if we do this because we use them separately. 
  **Concept of REFUSE** 

  ![03 06 2024_10 02 19_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/3e913875-4903-4b8c-b8b3-6022efee020d)

lets look at some readily available IPs

![03 06 2024_10 07 04_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/37899738-7657-4971-8fde-49a5b0f23ffa)

Now try to understand the some IPs, this are designed only once then used multiple time when ever they required. this are directly place and core area and then we have to fix them before placement.

![03 06 2024_10 12 22_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/2ba732d3-e8b7-4533-a01f-667bb0577c20)

After placing Pre placed cells then we surround them with de-coupling capacitor's.


### De-coupling capacitors

Let consider some circuit, which is the part of the blocks which has been described earlier. When some gate (let consider AND gate) switched from 0 to 1 or 1 to 0, considered amount of the switching current required because of available small capacitance . This capacitor should be completely charged to represent logic 1 and completly discharged to represent logic 0. Consider capacitance to be 0. Rdd,Ldd,and Lss are well defoned values. During switvhing operation, the circuit demands switching current i.e. peak current. Now, due to the presence of Rdd and Ldd, there will be a voltage drop across them and the voltage at Node 'A' would be Vdd' instead of Vdd.

![03 06 2024_10 18 03_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/e2a5a5f0-bde5-4c03-be04-3d6a965372af)


![03 06 2024_10 19 15_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/5c4a2cdf-249c-4d84-bea9-ed991db3f5b7)

Noise margins diagram

![03 06 2024_10 20 21_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/a195b8c3-9253-4282-99cf-69a95f5c58a8)


we have to put De-coupling capacitor in parallel with the circuit. Every time the circuit switches, it draws current from Cd, whereas, the RL network is used to replenish the charge into Cd. And the amount of current needed for the circuit is supplied by the De- Coupling Capacitor.

![03 06 2024_10 23 47_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/63238377-928d-4db5-b03f-768af5673ab7)

![03 06 2024_10 27 06_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/1ff040a2-cd7c-40a7-a54d-6b946eeeb7b9)



### Power planning


There is a signal which is send from driver to load and the signal is basically logic 0 to logic 1. Here we need to maintain the particular driver to load line with the same signal, so that the load recieves the same signal. Now power supply is applied. Now assume 16 bit bus has to retain the same signal from driver to the load. so it should get the sufficient power from the supply. But at this bus, there is no de-coupling capacitor is available because it is not physible to put capacitor at all over the place. now, power supply is far away from the bus, that is why some voltage drop between them will occur.

![03 06 2024_10 34 30_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/17a52bf4-f7c2-416e-b6f6-a28b1a77160b)

Lets look at the 16bit bus

![03 06 2024_10 38 32_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/67226569-0783-4070-8aba-5ed10e8f5625)

the problem is occurs due to all capacitor is connected to the single ground. This will cause a bump in 'ground' tap point during discharging. That bump is called as Ground Bounce.

![03 06 2024_10 41 31_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/1ea93754-a811-4dd9-b13e-ebc9692fa67b)

now, capacitors which were'0' volts will have to charge to '1V'volts through single 'vdd'tap point. This will cause lowering of voltage at Vdd tap point.

![03 06 2024_10 44 04_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/a09a0b74-d065-4ac2-abd0-0bc26257936d)

To solve this kind of problem instead of single power supply we create multiple VDD VSS lines.

![03 06 2024_10 45 39_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/652529d2-35c1-4de4-ae9d-23c3095cef90)

In real design this is how we create power plan

![03 06 2024_10 49 31_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/1d1c96f0-6488-45c7-9f8b-af308305bca9)




### Pin placement and logical cell placement blockage



Now lets look at the pin placement or port placement part in a design. pin placement is nothing but every macros, standard ceslls are having a input pins and outputs accordingly.
to give a connection to those pin we are usig metal layers in the design. basad on the cells or macros we connect them to the pins at  what ever direction they are belongs.
To understand it better lets go through this example

![03 06 2024_11 07 27_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/b6171bd6-e482-4fa0-9c4f-c0959140e7b7)

below we have 6 in pins and 5 out pins.

Now we are placing these pins in to the die space on the site rows.

![03 06 2024_11 51 23_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/5a510e63-a85e-4a08-91e2-2e5065099e86)

after the pins placement we logical cell placement blockage to avoid the standards cells placement in that area.


![03 06 2024_11 54 42_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/f8af318f-20d8-4f94-a3ad-f6c9da5806cf)

Now the froorplan is ready for the placement of standard cells.




### Steps to run floorplan using OpenLANE

**LABS**

Lets start with the floorplan, Before run the floorplanning, we required some switches for the floorplanning. these we can get from the configuration from openlane. the command is run_floorplan.

















 





