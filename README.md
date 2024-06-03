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

When we run the run_placement, first Global placement is happens. main objective of global placement is to reducing the wire length.

Now opening the Magic file to see actual view of standerd cells placement. 













## Cell design and characterization flows

### Inputs for cell design flow


 





