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

![03 06 2024_12 40 55_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/b576f2bc-6299-4217-bb74-6759720865c0)

in this you can variables required for the every stage in the design

![03 06 2024_12 43 10_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/82ed654f-cdc2-401b-a780-0a39735fc2e6)

Here we can see that the core utilization ratio is 50% (bydefault) and aspect ratio is 1 (bydefault). similarly other information is also given.

if we want to change anything here we have to change this switchs 
this are available at .tcl file in the directory.

Lets see the floorplan.tcl file contents

![03 06 2024_12 52 56_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/c2257f1a-465e-43a1-80a7-8ede30775c34)

In the OpenLANE lower priority is given to system default (floorplanning.tcl), the next priority is given to config.tcl and then priority is given to PDK varient.tcl (sky130A_sky130_fd_sc_hd_congig.tcl).

![03 06 2024_14 19 03_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/15b7cf32-ef59-49e6-9fc5-1d6daabcc61d)
here floorplan completed


### Review floorplan files and steps to view floorplan


Lets look at the logs 
![03 06 2024_14 16 39_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/c43f8b00-b9e3-43aa-b05e-563fa3e81401)

In the run folder, we can see the connfig.tcl file. this file contains all the configuration that are taken by the flow. if we open the config.tcl file, then we can see that which are the parameters are accepted in the current flow.

![03 06 2024_14 48 33_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/be3d3055-1c9f-4c46-bbe4-e642961d9dc6)

![03 06 2024_14 35 48_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/79ac4972-a13e-49a0-addc-f41547c94916)

![03 06 2024_14 38 21_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/2db04671-ad26-40f9-b38e-ef4535e2efee)

To watch how floorplane looks, we have to go in the results. in the result, one def( design exchange formate) file is available. if we open this file, we can see all information about die area (0 0) (660685 671405), unit distance in micron (1000). it means 1 micron means 1000 databased units. so 660685 and 671405 are databased units. and if we devide this by 1000 then we can get the dimensions of chips in micrometer.


![03 06 2024_14 41 28_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/6b68f289-6882-4c12-9ede-e8ca3f0718c6)

so, the width of chip is 660.685 micrometer and height of the chip is 671.405 micrometer.


### Review floorplan layout in Magic

To see the actual layout after the flow, we have to open the magic file by adding the command  
magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.floorplan.def

And then after pressing the enter, Magic file will open. here we can see the layout.

![03 06 2024_15 10 04_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/8c81533d-feaa-4834-bcd2-54e3c185928f)

when the magic tool opens with floorplan that time the image is not in centre to make that in to centre use "s" to select then use "v" to align to center.

To zoom a magic frist left click then drag then right click on mouse. after selecting press z on keyboard for zoom in and press shift z for zoom out.

![03 06 2024_15 17 49_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/ba9faff7-5617-40f4-97d8-d498dd242ade)

Lets check the input ports

![03 06 2024_15 21 07_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/11d5c593-830e-4d01-ba5d-99f118486151)

Lets check the horizontal pin details.

![03 06 2024_15 27 13_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/021eb5de-cdef-4929-8c3c-a38295d75077)

Lets check the vertical pin details.

![03 06 2024_15 30 39_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/37845b52-f7ba-4e08-85da-9ca7f764b873)

![03 06 2024_15 35 56_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/59e0ebcb-13a5-4dba-b8de-2baa7a96e612)
these are TAP cells

Now, lets see the where standard cells are presents, usually they are present at (0,0) location.

![03 06 2024_15 38 49_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/2f3f26c7-35ca-4f30-b878-83cd95992107)


## Library building and Placement

### Netlist binding and initial place design

Lets look in to the placement and routings stage of the physical desugn. the very frist step in this is bind netlist with physical cells

![03 06 2024_15 48 55_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/25c9cc2c-39ca-444e-91c9-93fb70a5b3ba)

In reality this is how look like

![03 06 2024_15 51 04_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/ee6b5e9e-64bd-4356-a79a-4cb0f7fd7b67)

Lets look at varies flavours of standard cells

![03 06 2024_15 55 15_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/e49b8140-0410-4759-9d24-3d058377d593)

Now moving on to the placement, We have the floorplan with inout and output ports, we have particular netlist, and we have particular size given to each component of this netlist. So we have the physical view of the logic gates. Next step is to place the netlist onto the floorplan. We have to take the connectivity information from the netlist and design the physical view gates on the floorplan.

![03 06 2024_15 59 01_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/ee7b164f-d38d-4bfc-9e9f-0b906b83e3e8)

we have the floorplan where we have the pre placed cells locations are not affected they are kept as it as and the second thing which will be taken care of that is no cell should be placed over the pre-placed cells.

place the physical view of the netlist onto the floorplan in such a fashion that logical connectivity should be maintained and that particular circuit should interact with their input and output ports to maintain the timing and the delay will be minimal.

![03 06 2024_16 06 14_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/f9594047-c252-4d84-930b-fd2dd6910f32)



### Optimize placement using estimated wire-length and capacitance


In optimize placement we will solve the problem of distancing. 
 
Let's take an example of Din2 to FF1. There must be a wire going from Din2 to FF1 but before going into routing the wiring we will try to estimate the capacitances. If we look the capacitance from Din2 to FF1 it is every huge because wire length is huge in that case even the resitance will also be huge because of that length. If we send the signal from Din2 then it will be difficult reach FF1 to catch that input because distance is large. So we can place some intermediate (buffer's) steps to maitain the Signal integrity.

![03 06 2024_16 15 02_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/15a5d5e0-7abb-4be9-9ad7-2cbcf495fa7c)

![03 06 2024_16 19 53_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/d0ac3b0d-3e66-475b-b18a-24715cbec571)


![03 06 2024_16 21 10_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/c124ed50-9d26-4a11-b7a9-4806316901d0)

considering the clock is ideal.

### Need for libraries and characterization


![03 06 2024_16 26 43_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/5a7287c4-50ff-455c-b543-0db6ccc94635)

In ICdesign Flow needs to go through the several steps. 

first we need to convert the functionality(RTL) into legal hardware(gate level netlist) is refered to as Logic Synthesis. 

next is logic synthesis to Floorplaning, in this we input the output of logic synthesis and decide the size of the Core and Die. 

after floorplaning to Placement, in this we take the particular logic cell to place them on the core area in such a fashion that initial timing is better.

CTS(Clock tree synthesis), here we take care of clk, should reach each and every flop at the same time also take care of each clk signal has equal rise and fall.

Routing: routing has to go through the certain flow depending on characterization of the flip flop.

STA(Static timing analysis), in this we try to see the set up time, hold time, maximum achieved frequency of the circuit.

![03 06 2024_16 35 09_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/eecb1459-eb2b-4464-a081-a4baf9a0531a)



### Congestion aware placement using RePlAce

The placement is done in two stages. Global(course placement) and detailed. In global placement, legalization is not happen but after detailed placement legalization will be done.

When we run the command (run_placement), first Global placement is happens. main objective of global placement is to reducing the wire length.
placement result

![03 06 2024_19 22 05_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/4aae4f50-609e-4bf7-8723-2845e0c0a1f5)

Now opening the Magic file to see actual view of standerd cells placement. 

lets see the standard cells

![03 06 2024_19 25 14_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/c35a0d3c-03a9-46f9-831b-199c904aa356)






## Cell design and characterization flows

### Inputs for cell design flow

Lets understand Cell Design Flow, Gates, flipflops, buffers are named as 'Standard Cells'. These standard cells are being placed in the section called as 'Library'.

![03 06 2024_19 38 00_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/598f101a-6b9e-444e-8daf-df4a29da8d24)

See the different drive strength cells

![03 06 2024_19 41 43_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/477d6460-db5f-4a70-bb01-e44b09030384)

Library consists standard cells with different vt flavors, drive strength etc..

![03 06 2024_19 45 28_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/b522f715-0191-4c0e-aec5-ebd3815c132e)

The inverter has to represented in form of the shape, drive strength, power charracteristic and so on. Here cell design flow is devided into three parts.

i. Inputs

ii. Design steps

iii. Outputs

Inputs:- Inputs required for cell design is PDKs, DRC and LVS rules SPICE models, library and user defined specs. In DRC & LVS rules tech file is provided which contains design rules and actual values. Rules can be converted in to code. SPICE MODEL tells about threshold voltage equation.

![03 06 2024_19 48 31_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/03d9e89b-b004-4572-a01c-2fe763bddc71)

SPICE module parameters

![03 06 2024_19 51 37_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/43aec052-a304-4f87-bebf-b19d548fc9dd)


### Circuit design step


The seperation between the power rail and the ground rail defines the cell height. Cell width depends upon the timing and drive strength.

![03 06 2024_19 58 12_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/cf093c28-b8e2-4e3b-991a-8aa690641c66)


### Layout design step

Lets look the layout design, based on the function we hace to design the PMOS and NMOS circuits.then draw the network grap.

![03 06 2024_20 02 47_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/d9d11be6-73ef-4cc0-9f82-54bcba667838)

Euler's path and stick diagram.
![03 06 2024_20 04 23_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/dc5b25c5-f621-404c-9839-61539a50d4ba)

![03 06 2024_20 05 51_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/13d2dd49-7674-4c4e-b92e-941c45611394)

Typical layout look like
![03 06 2024_20 08 23_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/2cef0536-e854-4f33-b918-b071f27e6f84)




### Typical characterization flow



Let's try to build the characterization flow based on the inputs we have.

![03 06 2024_20 12 15_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/e91139ac-8a53-4fb1-abea-0983c8e6481e)


![03 06 2024_20 14 59_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/6c26791d-90a4-4f4a-9450-6ab1ede49108)


![03 06 2024_20 15 57_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/1e2a9112-5043-4247-89a7-c546f62ff77e)


feed in all this inputs from 1 to 8 in a form of a configuration file to the characterization software "GUNA" .

This software will generate power, noise and timing model.

![03 06 2024_20 17 49_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/d663d2d4-661c-4a6c-b16e-3422ef74e49b)




## General timing characterization parameters

### Timing threshold definitions


in the previous section we have inverter connected back to back, we have power sources, we have the stimulus applied to the inverter all these things brings a very important point of understanding differenet threshold points of a waveform itself and it is called as "Timing threshold definitions'.

Slew_high_rise_thr

![03 06 2024_20 21 25_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/dfca80f6-801d-45e1-9cc1-c98767603671)

 the typically value of this is about 20% it could be 30% as well.

 Slew_low_fall_thr

 ![03 06 2024_20 24 42_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/577589d1-c8b3-4393-be61-2c7c8cf38015)

 ![03 06 2024_20 25 32_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/03af3c89-80b7-4f39-a39e-75b6eb6d17be)

Typical value is 50%

Rise waveforms

 ![03 06 2024_20 27 39_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/c339cb17-915c-43e9-96a3-9e74d4fb78cd)

Fall waveforms 
![03 06 2024_20 30 12_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/7b66e0bf-def2-46d0-9d8d-106aa8bb7cf5)

Based on the above 8 values we are going to calculate slew, propagation delay and many things



### Propagation delay and transition time

If we want to calculate the delay of anything we need to subtract the out_rise_thr from in_rise_thr. Here let's take typical value 50%, let's see on the particular waveform how does it works Time delay = Time(out_thr)-time(in_thr).

![03 06 2024_20 36 00_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/9966c818-fa31-40b9-a451-dc6e606239f8)


![03 06 2024_20 38 05_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/ebd202ec-f91e-4d4d-9348-0829a7410998)

In the above example in_rise_thr and out_fall)thr was kept at 50%. But if the threshold ponit moves to the top the the output comes before the input and we see negative delay and negative delays are not accepted. So the reason behind having this negative delay is poor choice od threshold point so thr choice of the threshold point is really important.

![03 06 2024_20 39 25_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/249499ae-5b5f-42df-88ee-152e28b582ac)

Let's take another example where we have choosed threshold point correctly but still can get a negative delay. Because uotput comes before the input that's why we are getting negative delay here, which is not accepted

![03 06 2024_20 41 19_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/d33db897-157a-4538-a87f-9c0b195b28f1)

Transition time

![03 06 2024_20 43 37_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/d1692b6e-2284-425d-95a3-4654d0f07614)



## Day 3 - Design library cell using Magic Layout and ngspice characterization

### Labs for CMOS inverter ngspice simulations

### IO placer revision


Till now, we have done floor planning and run placement also. But if we want to change the floorplanning, for example, in our floor planning, pins are at equal distance and if we want to change it then we can also make it by Set command.

For that first we have to check the switches in the configuration and from that we have to take the syntax "env(FP_IO_MODE) 1". and make it to the "env(FP_IO_MODE) 2". then again run the floorplanning.

Then check the changes in the pins location through magic -T.
magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.floorplan.def &

![03 06 2024_21 56 34_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/d75d2c35-3525-40f3-a8ac-e34b6f3a4a87)


### SPICE deck creation for CMOS inverter

spice deck:- it's the connectivity information about the netlist so basically it's a netlist.It has input that are provided to the simulation and the deck points which will take the output.

Component connectivity:- In this we need to define the connectivity of the substrate pin. Substrate pin tunes the threshold voltage of the PMOS and NMOS.

Component values:- Values for the PMOS nad NMOS. We have taken the same size of both PMOS and NMOS.

Identify the nodes:- Node mean the points between which there is a component.These nodes are required to define the netlist.

![03 06 2024_22 22 31_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/17bedf0d-6533-4bf9-9901-a6d5569f0e24)

Name of the nodes:- name these nodes as Vin, Vss, Vdd, out.

![03 06 2024_22 24 15_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/3cfc4d8a-f593-4eee-aab0-4dabfc5e51e2)

### SPICE simulation lab for CMOS inverter

Lets describes the spice deck

PMOS information

![03 06 2024_22 28 24_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/65c4c38c-f866-406a-bd8a-fee31af39e68)


NMOS information

![03 06 2024_22 30 03_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/e120203a-7b0f-4578-beb3-d91e03162a9d)

Output load capacitance

![03 06 2024_22 32 03_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/c0efb665-7207-480f-ac54-156104524f62)

next they mention vdd is 0 to 2.5v and vin is 0 to 2.5v

simulation commands in which we are swiping the Vin from 0 to 2.5 with the stepsize of 0.05. Because we want Vout while changing the Vin.![03 06 2024_22 35 40_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/bce686f8-e2e5-4141-888e-ce1415983595)

![03 06 2024_22 36 42_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/d9cea9ce-cdee-43b1-a15d-913ac1f0ccf4)



Now we will do the SPICE simulation for the particular values. And will get the graph.
![03 06 2024_22 40 20_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/6a9e8499-7feb-487a-bb8b-518d4aa5b17a)

Now, doing other simulation in which we change the PMOS width to 3 times of NMOS width. and after diong the simulation, we get the graph like this shown below

![03 06 2024_22 43 02_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/278f2264-9305-49a0-b90b-d894b5643705)



### Switching Threshold Vm

By comparing this both the graph we can understang the concept of switching thresold voltage.

![03 06 2024_22 47 39_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/4ec1f377-b9e1-4866-bde3-92725f0a9c41)


In the below grape we can identify that the PMOS and NMOS are liase in which region. The direction of current flowing is different for NMOS and PMOS.

![03 06 2024_22 50 26_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/17c5278b-43ae-4022-8af7-6771e2c69b04)

![03 06 2024_22 52 59_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/41bd1999-55c6-4859-8eff-a33018b28777)



### Static and dynamic simulation of CMOS inverter


In Dynamic simulation we will know about the rise and fall delay of CMOS inverter and how does it varying with Vm. In this simulation everything else will remian same except the input which is provided will be a pulse and simulation command will be .tran

The graph Time vs Voltage will be plotted here from where we can calculate the rise and fall delay.

![03 06 2024_22 55 40_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/731a17d4-3a85-48b5-b95f-c22624bc78f5)

![03 06 2024_22 56 39_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/24bb2f21-5cad-4f17-a004-701ec234c157)
 

### Lab steps to git clone vsdstdcelldesign

Lets get clone the VSDSTDCELLDESIGN from the nickson-jose github.com

![03 06 2024_23 08 52_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/8349b973-3a79-4a49-b0bb-86d6741dce3a)

![03 06 2024_23 14 06_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/70f79180-f54b-4dce-8f46-fe2f367a237b)

Lets copt the sky130A.tech file

![03 06 2024_23 20 16_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/75ec08b8-0905-49f0-9a50-4761d0aac707)

![03 06 2024_23 21 13_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/31d4797e-7ca4-4236-aa8e-93c3b1961296)

Now, here to see the layout in magic, we don't need to write the whole address 

![03 06 2024_23 25 13_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/434970e5-9c62-4aee-9714-4ab2b9618b28)



## Inception of layout and CMOS fabrication process


### Create Active regions



### Lab introduction to Sky130 basic layers layout and LEF using inverter

In sky130, every color is showing the different layer. here the first layer is for local interconnect shown by blue_purple color, then second layer is metal 1 which is shown by light purple color, and the metal 2 is shown by pink color. N-well is shown by solide das line. green is N-diffusion region. and red is for polysilicon gate. similarly the brown color is for P-diffusion.
![04 06 2024_09 43 31_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/dee56780-bbe5-4bc1-943b-b8cecd2fde64)

In tckon window, lets see that the selected area is NMOS and similarly we can see PMOS also. and that is how we can check that the CMOS is working or not.

![04 06 2024_09 54 37_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/361c17bf-710e-4b6e-b077-d8dd3f2b8926)

Lets look the Nwell

![04 06 2024_09 56 06_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/69fdc64e-2f35-4a6d-93a3-80013e66f4c9)

by double pressing "S" to select the entire thing at output Y

![04 06 2024_09 58 37_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/9305c317-e4d9-43a5-87e5-a9c6e60e55f6)

lets find the PMOS in the layout

![04 06 2024_10 01 06_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/7fe49771-dea6-4bec-9401-e939a876d4aa)

we have to check the source of the PMOS is connected to the ground or not. and similarly we can check it for NMOS also.



### Lab steps to create std cell layout and extract spice netlist


using github repo he explained stpes to create a standard cell layout. https://github.com/nickson-jose/vsdstdcelldesign.git

![04 06 2024_10 21 53_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/7e5dfd57-0a7d-4fc3-a64a-a6d15d55859a)

Lets check the DRC. how drcs are comming, if i select part the nwell in the layout and delete that, drcs will occurs. you see that in the image.
![04 06 2024_10 48 30_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/778d3fe8-0c98-49c4-8b60-3cd044a05611)

To extract the file from here, we have to write the command in tckon window. comand is **extract all**

![04 06 2024_10 56 58_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/a13aa5a6-c58f-4c71-83ad-67e68154766b)

Now see weather the file is extracted or not.

![04 06 2024_10 59 01_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/49b4fc2d-5e84-4912-8704-03f4d3326815)

we will use this .ext file to create the spice file to be use with our ngspice tool. for that we have apply the command ext2spice cthresh 0 rthresh 0. this will not create anything new. now again we have to type ext2spice command in tckon window.

![04 06 2024_11 03 45_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/f2fed993-2b66-4c9a-b673-ebfb874095aa)

atfter see file created or not
![04 06 2024_11 09 03_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/de306540-15f9-46c6-bb78-4c47d6992aae)

![04 06 2024_11 10 07_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/02a079af-f2b7-4b85-b9c5-7a179caa968c)

Now, lets see what is there in this file

![04 06 2024_11 12 35_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/60fa3bb5-ac1c-4a9d-8243-1ca9b04add68)



## Sky130 Tech File Labs

### Lab steps to create final SPICE deck using Sky130 tech

we can see the all details about the connectivity of the NMOS and PMOS and about the power supply also.

![04 06 2024_11 12 35_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/889634e5-6d77-495e-8280-daa3bba6c8ec)

![04 06 2024_11 53 40_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/577a30bd-f302-4314-a266-a85f526e8881)

X0 is NMOS and X1 is PMOS and both's connectivity is shown as GATE DRAIN SUBSTATE SOURCE.

![04 06 2024_12 03 12_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/fda7eb34-0ecd-4d12-bbc3-a71036231ee8)

Now we have to include the PMOS and NMOS lib files. it is inside the libs folder in the vsdstdcellsdesign folder.

![04 06 2024_12 12 37_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/fcc1618b-7370-4ae3-afec-9b18c069b794)

now we include this file path in the file by **.include ./libs/pshort.lib** and **.include ./libs/nshort.lib**

set the supply voltage "VDD" to 3.3v by VDD VPWR 0 3.3V command. and similarly set the value of VSS also.

we need to specify the input files. by Va A VGND PULSE(0V 3.3V 0 0.1ns 2ns 4ns)
add the command for the analysis like, .tran 1n 20n, .control , run,.endc,.end.

![04 06 2024_14 33 23_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/9cd158e0-e323-45be-91d1-cedbb46ed77e)

lets run the ngspice command is ngspice sky130.inv.spice

![04 06 2024_14 34 44_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/34aeb6be-966d-4a86-aa58-603c63ee580e)

ploting the graph here by command, plot y vs time a

![04 06 2024_14 35 59_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/0582232d-3509-4ad2-9879-1927bf6bc37f)



### Lab steps to characterize inverter using sky130 model files

we have to find value of 4 parameters.

![04 06 2024_14 35 59_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/0582232d-3509-4ad2-9879-1927bf6bc37f)

![04 06 2024_19 07 44_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/d8272a36-0683-4f0c-8636-4949b97ba4cc)

Rise time = time taken to rise to 80% – time taken to rise 20% = 2.1887 ns – 2.1299 ns = 0.0588ns = 58.8 ps

Fall time = (time taken to fall by 80%) - (time taken to fall by 20%) = 4.0753 – 4.0497 = 0.0266ns = 25.6 ps

Propagation delay for rising output = (time taken to rise to 50%) – (time taken to fall to 50%) = 2.1765 – 2.1436 = 0.03653ns = 32.9 ps

Propagation delay for falling output = (time taken to fall to 50%) – (time taken to rise to 50%) = 4.0552 - 4.0511 = 0.00323 = 4.1 ps


### Lab introduction to Magic tool options and DRC rules

![04 06 2024_15 42 09_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/f9f1b84a-c65e-4107-b917-017b07fccd15)


To know about the Magic DRC we can go to the website:- http://opencircuitdesign.com/magic/Technologyfiles/TheMagicTechnologyFileManual/DrcSection

Link to Google_Skywaters Design Rules: - https://skywater-pdk.readthedocs.io/en/main/rules/periphery.html

For reference , we can use the github repo of Google-Skywater: - https://github.com/google/skywater-pdk




### Lab introduction to Sky130 pdk's and steps to download labs

Follow the below steps:

First go to the home directory.

To download the lab files for performing DRC corrections: **wget http://opencircuitdesign.com/open_pdks/archive/drc_tests.tgz**

To extract the lab files from the downloaded file: **tar xfz drc_tests.tgz**

Then go inside the lab folder **drc_tests**

list all the directories, use command **ls -al**

Lets view the .magicrc file, use the command **gvim .magicrc** 
This file serves as the startup script file for magic tool and tells it where to find the technology file. 
The technology file is already available locally in the same directory, so we can make changes to it if needed.

To start the magic tool with better graphics, we can use the command **magic -d XR &**

![04 06 2024_16 12 22_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/34276964-aac1-4124-a1b7-68e8ef9c2b91)

To view the Content of .magicrc file, open using command **vi .magicrc**

![04 06 2024_16 17 08_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/5ca50efa-ff1d-4fe6-ae79-d5b78bd6b50a)

Use the command magic -d XR
![04 06 2024_16 20 53_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/8d293b7a-1eed-4636-aa51-64a239edd145)


### Lab introduction to Magic and steps to load Sky130 tech-rules

open the magic tool. Open the met3.mag file from the file menu. we will see different layouts with different DRC values

![04 06 2024_19 09 24_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/8e36e4f3-7e4d-41bd-bcd9-faa4321da1d4)

![04 06 2024_19 11 38_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/dde0a6e0-619f-4712-a0d7-560b0fc5a5b9)

Now we will select the any layout area and check drc why in tckon.

![04 06 2024_19 19 06_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/71233f3c-97d9-438d-b094-32f37b353ecb)

![04 06 2024_19 21 07_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/d6eb9be6-06ed-4176-b3c5-3f94a9290eca)

Place the mouse pointer at m3 contact and click on the p to paint it in the box which we have created

![04 06 2024_19 26 35_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/6178c9c3-3637-4b09-8aa6-adc25e880c93)

![04 06 2024_19 41 48_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/ac36467b-4c9f-4a63-b549-b0b6b760b348)

![04 06 2024_19 47 13_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/662a344c-06dd-47a8-aa8e-92f8451ac68d)


### Lab exercise to fix poly.9 error in Sky130 tech-file

Open poly.mag file or type load poly

![04 06 2024_19 53 44_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/8af6c1ad-db43-4e93-bda0-f19571af92d0)

![04 06 2024_19 58 35_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/5e470365-bf0c-4d5b-a05c-a1afea84961e)


![04 06 2024_20 01 06_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/3cee62d8-e6ab-4e2a-80f2-4c13f02ec245)


![04 06 2024_20 05 40_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/ad68f6dc-916f-4249-9ad5-a134b00b325e)
change allpolynonres
![04 06 2024_20 13 50_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/a2839b2b-26de-41e7-b36b-dca5fa70705a)
![04 06 2024_20 19 24_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/5b0bbb18-8f6c-48d1-96bd-5b280427f9b9)
lets load the sky130A.tech file

![04 06 2024_20 23 09_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/fe910f1d-1a4b-4321-a8e0-f4808389d324)

![04 06 2024_20 24 43_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/9a6cd5d2-b300-4300-a97d-1ab2e4e5d6cf)


### Lab exercise to implement poly resistor spacing to diff and tap

![04 06 2024_20 49 29_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/1c51369e-521d-45bb-b1da-f1d279712f0f)


### Lab challenge exercise to describe DRC error as geometrical construct

Load nwell.mag and see for errors after that run the below commands

![04 06 2024_20 58 23_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/3c35b1a0-9f87-4db5-bc88-0d6dfdbaf808)

lets do some changes in sky130A.tech

![04 06 2024_21 06 58_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/4a08a4bb-9152-4436-b3ed-4b23c48a68d7)

![04 06 2024_21 08 43_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/28d43b6b-59a5-482e-9f9e-3d815e1e15f8)

![04 06 2024_21 11 21_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/f895f23e-cf52-41a7-ab9e-f7209bf2a014)

![04 06 2024_21 19 41_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/5d1de6b5-dda0-44a7-b3d3-9a0de54caec7)

### Lab challenge to find missing or incorrect rules and fix them

![04 06 2024_21 37 00_REC](https://github.com/VIJAYAKUMARAHS/Digital_VLSI_SoC_Design_and_Planning_Program/assets/89599199/017de7ae-e294-4f0b-b02f-8ad92855a368)




